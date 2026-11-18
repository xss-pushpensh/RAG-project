# 📚 RAG-Project: Document Q&A with NVIDIA Nemotron

## 📝 Overview

****RAG**-Project** is an intelligent Retrieval-Augmented Generation (**RAG**) application designed to act as an expert tutor. It ingests a provided **PDF** document (e.g., a Computer Science textbook), breaks it down into searchable chunks, and uses a powerful Large Language Model (**LLM**) to answer user queries *strictly* based on the document's content.

This project uses **Qdrant** for in-memory vector storage, **FastEmbed** for efficient text embeddings, and ****NVIDIA** AI Endpoints** for high-quality, reasoning-based responses.

## ✨ Key Features

- **📄 Smart Document Ingestion:** Automatically loads and parses **PDF** documents using `PyPDFLoader`.
- **✂️ Intelligent Chunking:** Uses `RecursiveCharacterTextSplitter` to split text into overlapping chunks, ensuring context is never lost at the edges.
- **⚡ Fast Vector Search:** Utilizes `FastEmbed` and an in-memory `Qdrant` database for lightning-fast semantic search without needing an external server.
- **🧠 Advanced **LLM** Reasoning:** Integrated with **NVIDIA**'s `nemotron-3.5-lightning-30b-a3b` model, optimized for accurate, context-bound answers.
- **💬 Interactive **CLI**:** A continuous terminal loop allowing users to ask multiple questions without restarting the script.
- **🔒 Security First:** Pre-configured to keep **API** keys and virtual environments safe from accidental exposure.

## 🛠️ Tech Stack

- **Language:** Python 3.10+
- **Framework:** LangChain (Core, Community, Text-Splitters)
- **Vector Database:** Qdrant (In-memory)
- **Embeddings:** FastEmbed
- ****LLM** Provider:** **NVIDIA** AI Endpoints
- **Environment Management:** Python `dotenv`

---

## 🚀 Getting Started

Follow these steps to set up and run the project locally.

### 1. Prerequisites

Ensure you have the following installed:
- [Python 3.10+](https://[www.python.org/downloads/](https://www.python.org/downloads/))
- [Git](https://git-scm.com/)
- An ****NVIDIA** **API** Key** (Get one for free at [**NVIDIA** **NGC**](https://catalog.ngc.nvidia.com/)).

### 2. Clone the Repository

```bash git clone [https://github.com/your-username/**RAG**-project.git](https://github.com/your-username/**RAG**-project.git) cd **RAG**-project ```

### 3. Set Up Virtual Environment

It is highly recommended to use a virtual environment to manage dependencies.

**On Windows:** ```bash python -m venv .venv .venv\Scripts\activate ```

**On macOS/Linux:** ```bash python3 -m venv .venv source .venv/bin/activate ```

### 4. Install Dependencies

```bash pip install -r requirements.txt ```

### 5. Environment Configuration

This project requires an **API** key to function. We use a `.env` file to keep secrets safe.

## Duplicate the example environment file:

    ```bash
    cp .env.example .env
    ```
## Open the `.env` file and replace the placeholder with your actual NVIDIA API key:
    ```env
    # LLM API
    NVIDIA_API_KEY=*nvapi-your-actual-api-key-here*

    # Application
    APP_ENV=development
    ```

### 6. Add Your Document

Place the **PDF** file you want to analyze inside the `document_loader` folder and name it **`**STATS**.pdf`**. *(Note: If you want to use a different filename, update the `pdf_path` variable in `main.py`).*

---

## 💻 Usage

Run the main application script: ```bash python main.py ```

Once the document is loaded and indexed, you will see a prompt: ```text --- **RAG** Chatbot Started --- Type 'quit' or 'exit' to stop.

Ask a question: ```

Type your question (e.g., **What is a variable?** or **Who wrote the foreword?**) and press Enter. The system will: ## Retrieve the most relevant text chunks from the PDF. ## Pass the context and your question to the NVIDIA LLM. ## Print the generated answer to the console.

To stop the application, type `quit` or `exit`.

---


## 📁 Project Structure

```text
RAG-project/
│
├── document_loader/
│   └── STATS.pdf          # Your source PDF document goes here
│
├── .env                   # Your actual API keys (Ignored by Git)
├── .env.example           # Template for environment variables
├── .gitignore             # Git ignore rules (Python, env, venv)
├── main.py                # Main RAG application script
├── requirements.txt       # Python dependencies
└── README.md              # Project documentation (This file)
```

## 🛡️ Security Note

**NEVER** commit your `.env` file to GitHub. This project includes a `.gitignore` file that prevents `.env` from being uploaded. If you accidentally expose your API key, revoke it immediately on the NVIDIA portal and generate a new one.

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to check the [issues page](https://github.com/your-username/RAG-project/issues).

## 📄 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details. 
*(Agar aapne koi license add nahi kiya hai, toh aap is line ko hata sakte hain ya GitHub par jaakar MIT license add kar sakte hain).*

---
*Built with ❤️ using LangChain and NVIDIA AI.*
