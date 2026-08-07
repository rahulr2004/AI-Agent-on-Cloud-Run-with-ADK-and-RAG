# ☕ Coffee Barista AI Agent on Cloud Run (ADK + RAG)

[![Google Cloud](https://img.shields.io/badge/Google_Cloud-Cloud_Run-4285F4?logo=googlecloud&logoColor=white)](https://cloud.google.com/run)
[![Python](https://img.shields.io/badge/Python-3.10+-3776AB?logo=python&logoColor=white)](https://www.python.org/)
[![License](https://img.shields.io/badge/License-MIT-green.svg)](LICENSE)

An intelligent, interactive Coffee Barista AI Agent deployed on **Google Cloud Run**. Built using the **Agent Development Kit (ADK)** and powered by **Retrieval-Augmented Generation (RAG)**, this agent can process natural language customer orders, query menu items dynamically, and assist with personalized recommendations.

---

## 🏗 Architecture Overview

```
                  +-------------------------+
                  |   User / Web Client     |
                  +------------+------------+
                               |
                               v
                  +-------------------------+
                  |   Google Cloud Run      |
                  |   (FastAPI / Flask App) |
                  +------------+------------+
                               |
             +-----------------+-----------------+
             |                                   |
             v                                   v
+-------------------------+         +-------------------------+
|   Agent Development     |         |     RAG Engine          |
|   Kit (ADK) Core        |         |   (Menu Knowledge Base) |
+-------------------------+         +-------------------------+
```

---

## ✨ Features

- **Natural Language Ordering**: Understands complex customer requests and preferences.
- **Retrieval-Augmented Generation (RAG)**: Dynamically fetches item availability, ingredients, and prices from `menu.json`.
- **Serverless Deployment**: Built for high availability and low latency on Google Cloud Run.
- **Extensible Agent Architecture**: Scalable setup using Google's Agent Development Kit patterns.

---

## 📁 Repository Structure

```
.
├── coffee-barista-agent/
│   ├── agent.py          # Core AI Agent logic and prompt templates
│   ├── app.py             # Web application interface / API entry point
│   ├── menu.json          # Knowledge base for RAG (menu items & details)
│   ├── seed.py             # Database / Vector index initialization script
│   └── requirements.txt   # Python dependencies
└── README.md
```

---

## 🚀 Getting Started

### Prerequisites

- Google Cloud SDK installed and configured
- Python 3.10 or higher
- Active GCP Project (`august-jigsaw-504810-r8`)

### Local Setup

Clone the repository:

```bash
git clone https://github.com/rahulr2004/AI-Agent-on-Cloud-Run-with-ADK-and-RAG.git
cd AI-Agent-on-Cloud-Run-with-ADK-and-RAG/coffee-barista-agent
```

Create a virtual environment:

```bash
python3 -m venv venv
source venv/bin/activate
```

Install dependencies:

```bash
pip install -r requirements.txt
```

Seed the knowledge base:

```bash
python3 seed.py
```

Run the local application:

```bash
python3 app.py
```

---

## ☁️ Deployment to Google Cloud Run

Deploy directly from Google Cloud Shell or your local terminal using `gcloud`:

```bash
# Set your active GCP project
gcloud config set project august-jigsaw-504810-r8

# Deploy to Cloud Run
gcloud run deploy coffee-barista-agent \
  --source . \
  --region us-central1 \
  --allow-unauthenticated
```

---

## 🤝 Contributing

Contributions, issues, and feature requests are welcome! Feel free to check the issues page.

---

## 👤 Author

**Rahul R**
GitHub: [@rahulr2004](https://github.com/rahulr2004)
