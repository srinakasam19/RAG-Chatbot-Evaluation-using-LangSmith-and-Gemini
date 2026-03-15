# RAG Chatbot Evaluation using LangChain, LangSmith, and Gemini

## Overview

This project demonstrates how to build and evaluate a
**Retrieval-Augmented Generation (RAG) chatbot** using **LangChain,
LangSmith, and Google Gemini models**.

The system retrieves relevant information from web documents, converts
them into embeddings, and stores them in a vector store for semantic
search. When a user asks a question, the retriever fetches the most
relevant document chunks, and the Gemini LLM generates an answer using
the retrieved context.

To measure the quality of the generated responses, the project
integrates **automated evaluation using LangSmith and LLM-based
evaluators**.

------------------------------------------------------------------------

## Features

-   Retrieval-Augmented Generation (RAG)
-   Web document loading and chunking
-   Semantic search using embeddings
-   Gemini-based LLM responses
-   Automated evaluation using LLM-as-a-judge
-   LangSmith tracing for monitoring LLM pipelines

------------------------------------------------------------------------

## Tech Stack

-   Python
-   LangChain
-   LangSmith
-   Google Gemini API
-   Vector embeddings
-   Jupyter Notebook
-   VS Code

------------------------------------------------------------------------

## Project Workflow

1.  **Document Loading**
    -   Web documents are loaded using `WebBaseLoader`.
2.  **Text Splitting**
    -   Documents are split into smaller chunks using
        `RecursiveCharacterTextSplitter`.
3.  **Embeddings**
    -   Gemini embedding model converts text chunks into vector
        representations.
4.  **Vector Store**
    -   Chunks are stored in an **InMemoryVectorStore**.
5.  **Retrieval**
    -   A retriever fetches the most relevant document chunks based on
        the user query.
6.  **Answer Generation**
    -   Gemini LLM generates an answer using the retrieved context.
7.  **Evaluation**
    -   The generated answers are automatically evaluated using
        LangSmith.

------------------------------------------------------------------------

## Evaluation Metrics

### Correctness

Checks whether the generated answer is factually correct compared to the
ground truth.

### Relevance

Determines whether the answer properly addresses the user's question.

### Groundedness

Ensures that the generated answer is based on the retrieved documents
and does not contain hallucinated information.

### Retrieval Relevance

Checks whether the retrieved documents are relevant to the question.

------------------------------------------------------------------------

## Dataset

The evaluation dataset is created using **LangSmith**.

Example dataset format:

Question: What is LangChain?\
Answer: A framework for building LLM applications

Due to **Gemini API quota limits**, only **two questions were included
in the dataset for testing**.\
If needed, more questions can easily be added to expand the evaluation
dataset.

------------------------------------------------------------------------

## Observability with LangSmith

LangSmith is used to track and monitor the RAG pipeline, including: -
Model prompts - Retrieved documents - LLM responses - Evaluation scores

This helps improve debugging, monitoring, and evaluation of LLM
applications.

------------------------------------------------------------------------

## Running the Project

### 1 Install dependencies

pip install langchain langsmith langchain-community
langchain-google-genai python-dotenv

### 2 Add API Key

Create a `.env` file and add your Gemini API key:

GOOGLE_API_KEY=your_api_key_here

### 3 Run the Notebook

Open the Jupyter notebook in **VS Code** and run the cells sequentially.

------------------------------------------------------------------------

## Future Improvements

-   Add a larger evaluation dataset
-   Use a persistent vector database (FAISS, Pinecone, etc.)
-   Add more document sources
-   Implement advanced retrieval techniques

------------------------------------------------------------------------
“Why is this project useful?”

This project shows how to build reliable LLM applications, because evaluation and observability are critical in production AI systems.
Instead of manually checking outputs, we can automatically evaluate model performance using LLM-based grading.

## Author

**Laxmi Srina**

