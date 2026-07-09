\# Retrieval-Augmented Generation (RAG) Question Answering System



\## Overview



This project implements a Retrieval-Augmented Generation (RAG) pipeline that enables a language model to answer questions using information retrieved from custom documents.



Instead of relying only on the model's existing knowledge, the system retrieves relevant document content and provides it as context to generate more accurate and context-aware responses.

\## RAG Pipeline Architecture



```text

Documents

&#x20;   |

&#x20;   ↓

Document Loading

(PyPDFLoader + Docx2txtLoader)

&#x20;   |

&#x20;   ↓

Text Splitting

(CharacterTextSplitter)

&#x20;   |

&#x20;   ↓

Document Embeddings

&#x20;   |

&#x20;   ↓

Vector Database

&#x20;   |

&#x20;   ↓

Retriever

(Similarity Search + Maximum Marginal Relevance)

&#x20;   |

&#x20;   ↓

Context Stuffing

&#x20;   |

&#x20;   ↓

LLM Generation

&#x20;   |

&#x20;   ↓

Final Response

```

\## Features



\* Load PDF and DOCX documents

\* Extract and process document text

\* Split large documents into smaller chunks

\* Create embeddings for document chunks

\* Retrieve relevant information using vector similarity

\* Use Maximum Marginal Relevance (MMR) to improve retrieval diversity

\* Generate answers using retrieved document context

\* Implement an end-to-end RAG workflow



\## Technologies Used



\* Python

\* Jupyter Notebook

\* LangChain

\* Hugging Face API

\* ChromaDB

\* PyPDFLoader

\* Docx2txtLoader

\* CharacterTextSplitter

\* Vector Embeddings

\* Large Language Models (LLMs)



\## Project Workflow



\### 1. Indexing



The indexing phase prepares documents for retrieval.



Steps:



1\. Documents are loaded using:



&#x20;  \* `PyPDFLoader` for PDF documents

&#x20;  \* `Docx2txtLoader` for DOCX documents



2\. Documents are split into smaller chunks using:



&#x20;  \* `CharacterTextSplitter`



3\. Text chunks are converted into embeddings.



4\. The embeddings are stored in a vector database for efficient retrieval.



\---



\### 2. Retrieval



The retrieval phase finds relevant information based on the user's query.



This project implements two retrieval methods:



\### Similarity Search



Retrieves document chunks that are most similar to the user's query based on embedding similarity.



\### Maximum Marginal Relevance (MMR) Search



Retrieves relevant documents while reducing redundancy between retrieved chunks, providing more diverse context to the language model.



\---



\### 3. Generation



The generation phase creates the final answer.



The retrieved documents are combined using a \*\*stuff documents chain\*\*, where the relevant document chunks are inserted into the prompt context.



The language model then generates a response based on:



\* User question

\* Retrieved document context



\## Project Structure



```

RAG/

│

├── Indexing.ipynb

│   └── Document loading, splitting, embeddings, and vector database creation

│

├── Retrieval.ipynb

│   └── Similarity search and MMR retrieval

│

├── Generation.ipynb

│   └── Context stuffing and response generation

│

├── requirements.txt

│

└── README.md

```



\## Setup Instructions



\### Clone Repository



```bash

git clone https://github.com/suruchidhakal/rag-project.git

cd rag-project

```



\### Install Dependencies



```bash

pip install -r requirements.txt

```



\### Environment Variables



Create a `.env` file:



```

HUGGINGFACEHUB\_API\_TOKEN=your\_token\_here

```



\### Run the Project



Open Jupyter Notebook:



```bash

jupyter notebook

```



Run notebooks in order:



1\. `Indexing.ipynb`

2\. `Retrieval.ipynb`

3\. `Generation.ipynb`



\## Future Improvements



\* Add a user interface using Streamlit

\* Support more document formats

\* Add conversational memory

\* Experiment with advanced retrieval techniques

\* Deploy as an API service



\## Author



\*\*Suruchi Dhakal\*\*



