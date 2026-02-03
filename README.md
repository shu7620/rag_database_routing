
# 🧭 RAG Database Routing System

[![Python](https://img.shields.io/badge/Python-3.9%2B-blue.svg)](https://www.python.org/)
[![Framework](https://img.shields.io/badge/Framework-LangChain-green.svg)](https://python.langchain.com/)
[![LLM](https://img.shields.io/badge/LLM-OpenAI/Anthropic-red.svg)](https://openai.com/)

## 📖 Project Overview
The **RAG Database Routing** system is an intelligent query orchestration layer designed to optimize information retrieval. Instead of querying every available data source (which is slow and expensive), this system uses an **LLM-based Router** to analyze user intent and direct the query to the most relevant specialized database.

### Why Routing?
* **Efficiency:** Reduces latency by skipping irrelevant data stores.
* **Accuracy:** Ensures structured questions go to SQL and semantic questions go to Vector DBs.
* **Scalability:** Easily plug in new data sources (GraphDB, APIs, etc.) without breaking the pipeline.



---

## 🛠️ System Architecture
The pipeline follows a multi-stage process:
1. **Query Analysis:** The LLM evaluates the user prompt.
2. **Routing Logic:** The router classifies the query into categories (e.g., `structured_data`, `semantic_search`, or `general_knowledge`).
3. **Execution:** * **SQL Route:** Converts natural language to SQL for structured databases.
    * **Vector Route:** Performs similarity search for unstructured documents.
    * **Fallback:** Standard LLM response for general queries.
4. **Synthesis:** Combines retrieved data into a final coherent answer.

---

## 📂 Project Structure
```text
├── agents/             # Routing logic and LLM agent definitions
├── config/             # Connection strings and API configurations
├── data/               # Sample datasets and vector embeddings
├── notebooks/          # Research and experimentation scripts
├── src/                
│   ├── routers/        # Logic for query classification
│   ├── retrievers/     # SQL and Vector search implementations
│   └── main.py         # Application entry point
├── requirements.txt    # Project dependencies
└── .env.example        # Environment variables template
```

---
## Installation & usage
    1. Clone the repository:

       git clone [https://github.com/shu7620/rag_database_routing.git](https://github.com/shu7620/rag_database_routing.git)
       cd rag_database_routing
       cd Spam_Sms_Detection
    
    2. Set up virtual environment:

        python -m venv venv

        source venv/bin/activate  # On Windows: venv\Scripts\activate
    
    3. Install Dependencies:

       pip install -r requirements.txt

    4. Environment Variables: Create a .env file and add your keys:

       OPENAI_API_KEY=your_key_here
       DATABASE_URL=your_sql_connection_string
       VECTOR_STORE_API=your_vector_key

---
