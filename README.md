# 💬 Conversational Chatbot

> A conversational AI chatbot powered by Facebook's BlenderBot-400M via the Hugging Face Inference API — built with LangChain and Streamlit, with full session-based chat history.

---

## 📌 Project Overview

This project demonstrates how to integrate an **open-source conversational model** (BlenderBot-400M-Distill) into a production-style chat application using LangChain's `HuggingFaceHub` connector and a Streamlit frontend.

It serves as a foundational exploration of **LLM chaining**, **prompt templating**, and **stateful chat UI** — core building blocks used in more complex AI applications.

---

## ✨ Key Features

| Feature | Description |
|---------|-------------|
| 🤗 Hugging Face integration | Connects to `facebook/blenderbot-400M-distill` via Inference API |
| 🔗 LangChain chaining | Uses `PromptTemplate` + `HuggingFaceHub` + `StrOutputParser` |
| 💬 Chat history | Full conversation stored in Streamlit session state |
| 🔐 Secure config | API token managed via `.env` and `python-dotenv` |
| 🖥️ Interactive UI | Clean Streamlit chat interface with role-based message display |
| 🛡️ Error handling | Graceful fallback response on API or model failures |

---

## 🚀 Tech Stack

| Category | Tools |
|----------|-------|
| Language | Python 3.8+ |
| Model | BlenderBot-400M-Distill (`facebook/blenderbot-400M-distill`) |
| LLM Framework | LangChain (`HuggingFaceHub`, `PromptTemplate`, `StrOutputParser`) |
| Model Hosting | Hugging Face Inference API |
| Frontend | Streamlit |
| Config | python-dotenv |

---

## 🏗️ How It Works

```
User types a message in Streamlit chat input
        ↓
PromptTemplate formats the input
        ↓
LangChain HuggingFaceHub connector
  └── Model: facebook/blenderbot-400M-distill
  └── Params: temperature=0.7, max_length=100
        ↓
StrOutputParser extracts response text
        ↓
Response displayed in chat UI
  └── Both user + assistant messages saved to session state
```

---

## ⚙️ Getting Started

### 1. Clone the repository
```bash
git clone https://github.com/<your-username>/conversational-chatbot.git
cd conversational-chatbot
```

### 2. Create a virtual environment
```bash
python -m venv venv
source venv/bin/activate        # macOS/Linux
venv\Scripts\activate           # Windows
```

### 3. Install dependencies
```bash
pip install -r requirements.txt
```

### 4. Configure environment variables

Create a `.env` file in the project root:
```bash
HUGGINGFACEAPI=your_hugging_face_api_token
```
> Get your free token at [huggingface.co/settings/tokens](https://huggingface.co/settings/tokens)

### 5. Run the app
```bash
streamlit run app.py
```
Visit `http://localhost:8501` in your browser.

---

## 📂 Project Structure

```
conversational-chatbot/
│
├── app.py              # Streamlit UI — chat interface, session state management
├── backend.py          # LangChain chain — model init, prompt template, chatbot function
├── requirements.txt    # Python dependencies
├── .env                # API token (not committed to version control)
└── README.md           # Project documentation
```

---

## 💡 Key Learnings & Takeaways

- Integrated an **open-source Hugging Face model** via LangChain's `HuggingFaceHub` connector — no OpenAI dependency
- Built a **stateful chat UI** using Streamlit's session state for multi-turn conversation tracking
- Applied **LangChain prompt templating** as a foundation for more complex chain architectures
- Implemented **graceful error handling** to ensure the app recovers cleanly from API failures

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

---

*A foundational project exploring open-source LLM integration, LangChain chaining, and conversational UI design patterns.*
