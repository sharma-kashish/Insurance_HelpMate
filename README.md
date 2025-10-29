# Mr.HelpMate AI: Generative Search System for Insurance Policies

## 💡 Overview

This project implements **Mr.HelpMate AI**, a smart search tool built with **Retrieval-Augmented Generation (RAG)** technology. Its goal is simple: to quickly and accurately answer questions based on a complex **Group Member Life Insurance Policy** document.

Instead of traditional keyword searching, this system understands your question, finds the exact policy clauses, and generates a concise, verified answer.

**Author:** Kashish Sharma
**Data Source:** `Principal-Sample-Life-Insurance-Policy.pdf`

---

## 🏗️ Architecture: The Three Layers

The system works in three main layers to deliver a reliable answer:

1.  **Embedding (Indexing):** The policy PDF is broken into small chunks and converted into numerical vectors.
2.  **Search (Retrieval):** The system searches these vectors to find the most relevant chunks.
3.  **Generation (Synthesis):** An LLM (like GPT) reads the retrieved chunks and writes the final answer.



### Key Features Implemented

The architecture includes **mandatory components** to ensure high quality and speed:

| Feature | Why it's Important |
| :--- | :--- |
| **Mandatory Re-ranker** | A second, smarter model checks the initial search results to make sure only the absolute **Top 3** most accurate policy snippets are used. |
| **Mandatory Cache** | Stores results from past queries. If you ask a similar question twice, the system answers instantly, saving time and cost. |
| **Citation Prompt** | The final answer *must* include a citation (e.g., `[Page 35, Chunk 1]`). This prevents the AI from guessing or "hallucinating." |
| **Optimal Chunking** | The policy is split into small (512-character) pieces to keep context clear for the AI. |

---

## ⚙️ Setup and Run

### Prerequisites

1.  **Python 3.8+**
2.  A valid **OpenAI API Key** (required for the Generation layer).
3.  The policy PDF file (`Principal-Sample-Life-Insurance-Policy.pdf`) in the project folder.

