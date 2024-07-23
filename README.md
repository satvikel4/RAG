Here's the revised README file, ensuring accuracy with the provided code:

README
This repository provides a solution for managing and querying document embeddings using Langchain, with support for embedding generation through Bedrock and Ollama models. The code is divided into two main functionalities: embedding documents into a Chroma vector store and querying the vector store using a retrieval-augmented generation (RAG) approach.

Main Components
Embedding Documents: The script processes PDF documents, splits them into manageable chunks, and stores their embeddings in a Chroma vector database.

get_embedding_function(): Configures the embedding model (Bedrock by default, with an option for Ollama).
main(): Handles command-line arguments, loads documents, splits them into chunks, and adds the chunks to the Chroma database.
load_documents(): Loads PDF documents from the specified directory.
split_documents(): Splits the documents into chunks using RecursiveCharacterTextSplitter.
add_to_chroma(): Adds new document chunks to the Chroma database, avoiding duplicates.
calculate_chunk_ids(): Generates unique IDs for each document chunk.
clear_database(): Clears the existing Chroma database if the reset option is specified.
Querying the Database: The script allows querying the Chroma vector store with a given text and retrieves the most relevant document chunks to answer the query.

main(): Handles command-line arguments to accept a query text.
query_rag(): Performs a similarity search on the Chroma database using the query text and generates a response based on the retrieved document context.
ChatPromptTemplate: Formats the retrieved context and query text into a prompt for the Ollama model.
Ollama: Generates a response based on the provided prompt.
Usage
Embedding Documents
To embed documents and store them in the Chroma database, run:

sh
Copy code
python populate_database.py [--reset]
--reset: Optional argument to clear the existing database before adding new documents.
Querying the Database
To query the Chroma database with a specific text, run:

sh
Copy code
python query_data.py "Your query text here"
Ensure that the data directory contains the PDF files to be processed and the necessary AWS credentials are configured for Bedrock embeddings.

This setup allows for efficient document management and retrieval, leveraging state-of-the-art embedding models and a scalable vector database.
