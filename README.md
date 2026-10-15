# Introduction to LangChain: Chains, Retrieval and RAG — Workshop

This repository organizes learning materials and a hands-on Retrieval-Augmented Generation (RAG) assignment completed during the IIT Madras BS Degree workshop.

## Workshop details

- **Workshop:** Introduction to LangChain: Chains, Retrieval and RAG
- **Organizer:** IIT Madras BS Degree Team
- **Dates:** 10–11 October 2026
- **Time:** 7:00 PM–9:00 PM IST
- **Time zone:** Asia/Kolkata
- **Format:** Online workshop (Google Meet details are intentionally not published here)

## Project: TechNova Solutions Policy Q&A

A document-grounded RAG system that answers questions from a fictional company policy document. The implementation uses LangChain, Hugging Face sentence-transformer embeddings, FAISS similarity search, and a Groq-hosted LLM.

### RAG workflow

1. Load the policy `.txt` file with LangChain `TextLoader`.
2. Split the document into overlapping chunks.
3. Generate embeddings using `sentence-transformers/all-MiniLM-L6-v2`.
4. Store vectors in FAISS.
5. Retrieve the three most relevant chunks.
6. Pass retrieved context and the question to the LLM through a prompt template.
7. If the policy does not contain an answer, instruct the model to say that the document does not specify it.

### Assignment questions

1. How many paid annual leave days does a full-time employee receive per year?
2. An employee wants to work remotely on Wednesday and take leave on Friday. What do the company policies say?
3. What is the company's parental leave policy?

### Expected behavior

- Q1: 18 paid annual leave days per year.
- Q2: Remote work requires emailing the manager at least one working day in advance and manager approval. Annual leave requires a request at least three calendar days before the leave date and manager confirmation.
- Q3: If the provided policy does not mention parental leave, the system should state that the document does not specify this information.

## Setup

Install dependencies:

```bash
pip install -r requirements.txt
```

Place the provided policy text file beside the Python script and name it `technova_policy.txt`, or set the `POLICY_FILE` environment variable to its path. Do not publish the policy source file unless you have permission to redistribute it.

Set `GROQ_API_KEY` as an environment variable. Never hardcode or commit API keys. Then run:

```bash
python assignment/23f1000204.py
```

On Windows PowerShell, set the key for the current terminal session with:

```powershell
$env:GROQ_API_KEY="your_api_key_here"
python assignment/23f1000204.py
```

## Repository structure

```text
.
├── README.md
├── requirements.txt
├── .gitignore
├── notebooks/
│   ├── Day_1_LangChain_Workshop.ipynb
│   └── Day_2_LangChain_Workshop.ipynb
├── notes/
│   ├── Lecture_1_LangChain_RAG_Notes.ipynb
│   └── Day_1_LangChain_RAG_Visual_Notes_Hinglish.pdf
└── assignment/
    ├── 23f1000204.py
    ├── 23f1000204_RAG_Assignment.ipynb
    └── 23f1000204_Complete_Colab.ipynb
```

## Security and attribution

- Keep API keys and credentials out of GitHub.
- Do not upload private meeting links, personal email addresses, or source documents you do not have permission to share.
- Workshop details above are based on the workshop announcement shared by the student.
- This is a learning repository; model outputs can vary slightly.

