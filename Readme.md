# 🧙 Harry Potter Knowledge QA System

This project is a question-answering (QA) system that leverages modern large language models (LLMs) to extract knowledge from the *Harry Potter* book series and answer user queries intelligently.


![Gradio UI Screenshot](./user%20interface%20demo.png)
*Type in your magical Harry Potter question and watch two LLMs duel it out. 🧙‍♂️⚡  (So far, DeepSeek is winning most wand fights😉)*

## 💡 How It Works

1. **Input Text Loading**: The system reads a `.txt` file containing the full text of *Harry Potter and the Sorcerer's Stone*.
2. **Text Chunking**: The text is split into chunks of 300 characters to preserve local context.
3. **Text Embedding**: Each chunk is embedded using `all-mpnet-base-v2` from the SentenceTransformers library.
4. **Similarity Search**: FAISS is used to build a vector index. Given a user question, the system embeds the query and retrieves the top 5 most semantically similar text chunks from the index.
5. **Prompt Construction**: These relevant chunks are concatenated with the user’s question to form a prompt.
6. **Answer Generation**:
    - 🧠 **Hugging Face model (`google/flan-t5-base`)** is used for fast, local text2text generation.
    - 🔮 **DeepSeek model (`deepseek-chat`)** provides high-quality answers from an API-based large language model.
7. **Gradio UI**: A simple Gradio interface allows users to input questions and view answers from both models side by side.

## 🧰 Technologies Used

- Python
- SentenceTransformers (`all-mpnet-base-v2`)
- Hugging Face Transformers (`flan-t5-base`)
- DeepSeek Chat API
- FAISS for vector search
- Gradio for UI

## ❓ What I learned from This Project

This project shows how we can use domain-specific text files (like books or manuals) to improve the performance of large language models (LLMs). It’s a great starting point for building smart assistants that understand custom content.

However, there are some limitations. We found that the system’s performance depends a lot on which embedding model and language model you choose. In our case, DeepSeek performed noticeably better than the others.


## 🚀 Getting Started
1. Make sure your Hugging Face and DeepSeek API tokens are set up in google colab (e.g., using `google.colab.userdata` or environment variables).

2. Upload your `.txt` file (e.g., `Harry Potter and the Sorcerer's Stone`) and start asking questions through the Gradio interface.

## 📄 License
🧙‍♂️⚡️ **All hail J.K. Rowling!** 🧹🦉  
 *We solemnly swear we are up to only academic good. 😇*

