#  AutoMate AI

**AI-powered personal automation platform** - Create custom AI agents that can send emails, schedule calendar events, publish to Instagram, analyze images, and more - all through natural conversation.

![AutoMate AI](frontend/src/assets/hero.png)

---

## ✨ Features

### Custom AI Agents
- Create personalized AI agents with custom instructions, names, and descriptions
- Choose between multiple LLM models (GPT-OSS 120B / 20B via Groq)
- Configure temperature and tool access per agent
- Each agent maintains its own conversation thread with memory

### Gmail Integration
- **Send Emails** - Compose and send emails through natural language commands
- **Read Emails** - Search and read inbox emails using Gmail search syntax
- **Smart Approval** - Every outgoing email requires explicit user approval before sending

### Google Calendar
- **Create Events** - Schedule meetings and events with natural language ("Schedule a meeting tomorrow at 3 PM")
- **List Events** - View upcoming calendar events for any date range
- **Smart Date Resolution** - Automatically resolves "today", "tomorrow", weekday references

### Instagram Publishing
- **Image Upload** - Upload images via Cloudinary CDN
- **AI-Generated Captions** - Automatically generates captions and hashtags using AI
- **Post Preview** - Review image, caption, and hashtags before publishing
- **Approval Workflow** - Approve or reject posts before they go live

### Image Analysis
- **Vision AI** - Analyze uploaded images using vision models
- **Image Q&A** - Ask questions about image contents

### Credits & Payments
- **Credit System** - Users start with 100 free credits
- **Razorpay Integration** - Purchase additional credits with multiple pricing tiers
- **Usage Tracking** - Automatic credit deduction per AI interaction

### Authentication & Security
- **Firebase Auth** - Google Sign-In via Firebase Authentication
- **JWT Sessions** - Secure HTTP-only cookie-based sessions
- **OAuth2 Integrations** - Encrypted token storage for connected services
- **AES-256-GCM Encryption** - All integration tokens encrypted at rest
- **MCP Auth** - Signed JWT tokens for backend ↔ MCP server communication

---

## 🏗️ Architecture

```
┌─────────────────────────────────────────────────────────┐
│                    Frontend (React)                      │
│  React 19 · Vite · Tailwind CSS v4 · shadcn/ui · Redux │
└──────────────────────┬──────────────────────────────────┘
                       │ REST API
┌──────────────────────▼──────────────────────────────────┐
│                 Backend (Express.js)                     │
│  Firebase Admin · JWT · Mongoose · Razorpay · OAuth2    │
└──────────────────────┬──────────────────────────────────┘
                       │ MCP Protocol (stdio)
┌──────────────────────▼──────────────────────────────────┐
│               MCP Server (Tool Server)                   │
│  Gmail API · Calendar API · Instagram Graph API          │
│  Gemini Vision · Cloudinary                              │
└──────────────────────┬──────────────────────────────────┘
                       │
┌──────────────────────▼──────────────────────────────────┐
│              LangGraph (Agent Runtime)                    │
│  StateGraph · Tool Nodes · Human-in-the-Loop Interrupts │
│  MongoDB Checkpointer · Groq LLM                        │
└─────────────────────────────────────────────────────────┘
```

---

## 🛠️ Tech Stack

### Frontend
| Technology | Purpose |
|---|---|
| **React 19** | UI framework |
| **Vite 8** | Build tool & dev server |
| **Tailwind CSS v4** | Utility-first styling |
| **shadcn/ui** | Pre-built UI components |
| **Redux Toolkit** | Global state management |
| **React Router v7** | Client-side routing |
| **Firebase Auth** | Google Sign-In |
| **Axios** | HTTP client |
| **Lucide React** | Icon library |
| **Sonner** | Toast notifications |

### Backend
| Technology | Purpose |
|---|---|
| **Express 5** | REST API server |
| **MongoDB + Mongoose** | Database & ODM |
| **LangGraph** | Agentic AI runtime with state graphs |
| **LangChain** | LLM tools & chain orchestration |
| **Groq** | LLM inference provider |
| **MCP (Model Context Protocol)** | Standardized tool server protocol |
| **Firebase Admin** | Server-side auth verification |
| **Google APIs** | Gmail, Calendar, OAuth2 |
| **Razorpay** | Payment processing |
| **Zod v4** | Schema validation |
| **Cloudinary** | Image CDN & upload |
| **Gemini API** | Vision / image analysis |

---



<p align="center">
  Built with ❤️ using React, LangGraph, and MCP
</p>
