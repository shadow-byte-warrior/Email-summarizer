# 📧 AI Email Summarizer Workflow (n8n)

This workflow automates **email extraction, summarization using a local LLM, and storage in Google Sheets** using **n8n**.

---

## 🚀 What This Workflow Does

1. 📥 Fetches latest emails from Gmail
2. 📄 Extracts subject + email body
3. 🤖 Sends content to a local AI model (TinyLlama via Ollama)
4. ✨ Generates a short 2-line summary
5. 📊 Stores results in Google Sheets

---

## ⚙️ Workflow Architecture

<img width="1657" height="751" alt="Screenshot 2026-04-03 152207" src="https://github.com/user-attachments/assets/52b19f40-751e-4021-964a-7b6d4d336949" />


## 🧠 AI Model Used

* Model: `tinyllama`

* Runs locally via:

  ```id="flow2"
  http://127.0.0.1:11434/api/generate
  ```

* Prompt:

  ```
  Summarize this email in 2 lines only
  ```

---

## 📁 Output Format (Google Sheets)

| subject     | summary                    |
| ----------- | -------------------------- |
| Email Title | AI-generated short summary |

---

## 🔌 Required Integrations

* Gmail OAuth2
* Google Sheets API
* Local LLM (Ollama running TinyLlama)

---

## 🛠 Setup Instructions

### 1. Import Workflow

* Open n8n
* Click **Import**
* Upload this JSON file

---

### 2. Configure Gmail

* Connect your Gmail account
* Ensure read access enabled

---

### 3. Setup Ollama (Local AI)

Install Ollama and run:

```id="flow3"
ollama run tinyllama
```

Make sure API is running at:

```
http://127.0.0.1:11434
```

---

### 4. Configure Google Sheets

* Connect your Google account
* Ensure sheet has columns:

  * `subject`
  * `summary`

---

### 5. Run Workflow

* Click **Execute Workflow**
* Check results in Google Sheets

---

## ⚠️ Important Notes

* Workflow runs manually (can be automated later)
* Works only if Ollama is running locally
* Gmail API limits may apply

---

## 🔐 Security

Do NOT expose:

* Gmail credentials
* Google Sheets API
* Local endpoints

---

## 🚀 Future Improvements

* [ ] Auto trigger on new emails
* [ ] Use GPT / OpenAI instead of TinyLlama
* [ ] Add spam filtering
* [ ] Store full email + summary
* [ ] Dashboard for analytics

---

## 👨‍💻 Author

Arun Pandian
AI & Data Science 🚀

---

## ⭐ Support

If you like this project:

* Star ⭐ the repo
* Share with others

---
