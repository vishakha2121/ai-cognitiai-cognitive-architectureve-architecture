<div align="center">
  <h1>🧠 Cogni-Mesh</h1>
  <p><strong>Multi-Agent AI Cognitive Architecture inspired by DeepMind</strong></p>
  
  ![Python](https://img.shields.io/badge/Python-3.10+-blue?style=for-the-badge&logo=python)
  ![FastAPI](https://img.shields.io/badge/FastAPI-005571?style=for-the-badge&logo=fastapi)
  ![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)
  ![SQLite](https://img.shields.io/badge/SQLite-003B57?style=for-the-badge&logo=sqlite)
  ![Google Gemini](https://img.shields.io/badge/Google_Gemini-8E75B2?style=for-the-badge&logo=google)
  
  <p><em>A modular, self-improving AI ecosystem where specialized agents collaborate to perceive, plan, reason, and learn.</em></p>
</div>

---

## 📖 Table of Contents
1. [Introduction & Vision](#1-introduction--vision)
2. [System Architecture](#2-system-architecture)
3. [The Six Cognitive Agents](#3-the-six-cognitive-agents)
4. [Database Schema](#4-database-schema)
5. [API Endpoints (Backend)](#5-api-endpoints-backend)
6. [Frontend UI Overview](#6-frontend-ui-overview)
7. [Tech Stack](#7-tech-stack)
8. [Local Setup & Installation](#8-local-setup--installation)
9. [Environment Variables](#9-environment-variables)
10. [Future Scope](#10-future-scope)

---

## 1. Introduction & Vision

Most AI chatbots are simple wrappers around a Large Language Model (LLM) prompt. They suffer from the "Goldfish Memory" problem—they forget context instantly, they don't plan, and they don't learn from their mistakes.

**Cogni-Mesh** is an experimental artificial cognitive system built to solve this. Inspired by DeepMind's research on Artificial General Intelligence (AGI), this project breaks down the AI response generation into a **multi-agent orchestration pipeline**. 

When you send a message, it doesn't just hit the Gemini API. It flows through a brain-like system where **Six Specialized Agents** collaborate to produce a highly contextual, logical, and refined answer.

---

## 2. System Architecture

The core of Cogni-Mesh is the **Orchestrator** (the brain stem) which routes the user's query through a deterministic pipeline of agents.

```text
                      ┌─────────────────┐
                      │   User Input    │
                      └────────┬────────┘
                               ▼
┌──────────────────────────────────────────────────────────────┐
│                    FASTAPI ORCHESTRATOR                      │
│                                                              │
│  Step 1: 👁️ PERCEPTION AGENT (Intent Classification)        │
│            - Is it a question, command, or casual chat?      │
│                               ▼                              │
│  Step 2: 🧠 MEMORY AGENT (Context Retrieval)                │
│            - Fetch past interactions from SQLite.            │
│                               ▼                              │
│  Step 3: 📋 PLANNING AGENT (Strategy Formulation)           │
│            - Break the query into logical steps.             │
│                               ▼                              │
│  Step 4: 🔍 REASONING AGENT (Core Generation)               │
│            - Query Gemini API with plan + context.           │
│                               ▼                              │
│  Step 5: ✨ SELF-IMPROVEMENT AGENT (Refinement)             │
│            - Review the generated answer for hallucinations. │
│                               ▼                              │
│  Step 6: 📚 LEARNING AGENT (Feedback Loop)                  │
│            - Store final interaction for future learning.    │
│                                                              │
└──────────────────────────────┬───────────────────────────────┘
                               ▼
                      ┌─────────────────┐
                      │ Final Response  │
                      └─────────────────┘