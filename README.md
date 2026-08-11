# Aurelius — AI Personal Assistant Suite

A self-hosted AI assistant built on n8n, with a custom luxury-themed web frontend ("Aurelius"). One assistant, five tools, all backed by real automation — not just a chat wrapper.

## Preview

![Dashboard](assets/dashboard.png)
![Normal Chat](assets/chat.png)
![Expense Tracker](assets/expenses.png)

## Tools

- **Dashboard** — single overview across every tool: recent expenses, CV repository, solved question sets, and summarized videos
- **Normal Chat** — talk to the assistant directly: calendar management, email reminders, and expense logging via natural language
- **Expense Tracker** — log, update, delete, and report on expenses (daily/weekly/monthly/all-time)
- **CV Summarizer** — upload CVs and ask questions about them (RAG-based, Supabase + Gemini embeddings)
- **Question Solver** — upload a PDF of mixed questions, get back a fully solved document
- **YouTube Summarizer** — paste a video link, get a summary, key points, and a blog post

## Features

- Dark/light theme toggle, persisted across sessions
- Live status indicator — flags when a tool's backend is unreachable
- Persistent history for Question Solver and YouTube Summarizer (stored in Google Sheets, readable from the dashboard)
- Typing/streaming-style responses in chat and expense logging

## Structure

- `/frontend` — static HTML/CSS/JS frontend (Tailwind CDN, no build step)
- `/n8n-workflows` — importable n8n workflow JSON files

## Setup

1. Import the workflows in `/n8n-workflows` into your n8n instance
2. Replace all placeholder values (marked `YOUR_...`) with your own:
   - n8n webhook domain (in `/frontend/*.html`)
   - Google Sheet/Doc/Drive IDs
   - Supabase project URL
   - Calendar ID and reminder email
3. Reconnect credentials for Groq, Google (Sheets/Docs/Drive/Calendar/Gmail), and Supabase in n8n
4. Serve `/frontend` locally or host it anywhere static files work

## Stack

n8n · Groq (Llama) · Google Workspace APIs · Supabase (pgvector) · Tailwind CSS

## Notes

This is a personal project built for my own workflow, shared as-is for anyone who wants to adapt it. Not actively maintained as a product — expect to do some wiring for your own accounts/credentials.

## License

MIT
