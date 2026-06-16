# 🎓 BEC BillDesk - AI-Powered College Fee Payment Portal

A modern, **macOS-inspired** college fee payment portal with an **AI voice assistant (ARIA)** for  Engineering College.

![Next.js](https://img.shields.io/badge/Next.js-14-black?logo=next.js)
![React](https://img.shields.io/badge/React-18-blue?logo=react)
![TypeScript](https://img.shields.io/badge/TypeScript-5-blue?logo=typescript)
![MongoDB](https://img.shields.io/badge/MongoDB-green?logo=mongodb)
![LiveKit](https://img.shields.io/badge/LiveKit-Voice-purple)

## ✨ Features

- 🖥️ **macOS Desktop Environment** - Dock, windows, launchpad, control center
- 🎤 **AI Voice Assistant (ARIA)** - Friendly guide powered by Cerebras AI
- 💳 **Multiple Payment Methods** - Crypto (Sepolia ETH), UPI, Net Banking, Cash
- 🔐 **JWT Authentication** - Secure student login
- 📄 **PDF Receipts** - Bank of Baroda style receipt generation
- 💬 **Real-time Chat** - Socket.IO powered live chat
- 🌙 **Dark/Light Mode** - Dynamic theming

---

## 📦 Installation Guide

### Prerequisites

- **Node.js** 18+ (LTS recommended)
- **Python** 3.10+ (for voice agent)
- **MongoDB** (Atlas or local)
- **Git**

### Step 1: Download & Extract

```bash
# Clone the repository (or download ZIP and extract)
git clone https://github.com/sangam-gaddi/BECBILLDESK-voice-agent-includes-.git
cd BECBILLDESK-voice-agent-includes-
```

### Step 2: Install Node.js Dependencies

```bash
npm install
```

### Step 3: Install Python Dependencies (for Voice Agent)

**Option A: Using pip (standard)**
```bash
cd voice-agent
pip install -r requirements.txt
cd ..
```

**Option B: Using uv (faster - recommended if you have it)**
```bash
cd voice-agent
uv pip install -r requirements.txt
cd ..
```

> 💡 Don't have `uv`? Install it: `pip install uv` or see [uv docs](https://github.com/astral-sh/uv)

### Step 4: Environment Variables

The `.env.local` file is already included with API keys. If you need to update them:

```env
# MongoDB
MONGODB_URI=your_mongodb_connection_string

# JWT Secret (generate a random string)
JWT_SECRET=your_secret_key

# LiveKit (get from https://livekit.io)
LIVEKIT_API_KEY=your_key
LIVEKIT_API_SECRET=your_secret
LIVEKIT_URL=wss://your-project.livekit.cloud

# Deepgram - Speech-to-Text (get from https://deepgram.com)
DEEPGRAM_API_KEY=your_key

# Cerebras - LLM (get from https://cerebras.ai)
CEREBRAS_API_KEY=your_key

# Cartesia - Text-to-Speech (get from https://cartesia.ai)
CARTESIA_API_KEY=your_key
```

### Step 5: Seed the Database (Optional)

If you need sample student data, create students in MongoDB with this schema:
```json
{
  "usn": "2BA23IS001",
  "studentName": "John Doe",
  "email": "john@example.com",
  "password": "hashed_password",
  "department": "ISE",
  "semester": "5",
  "paidFees": [],
  "isRegistered": true
}
```

---

## 🚀 Running the Application

### Terminal 1: Start Next.js (Frontend + Backend)

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000)

### Terminal 2: Start Voice Agent (ARIA)

```bash
cd voice-agent
python agent.py dev
```

---

## 🎤 Using the Voice Assistant (ARIA)

1. Login as a student
2. Click the **microphone button** (bottom-right corner)
3. ARIA will greet you and can help with:
   - Explaining your pending fees
   - Guiding you through payments
   - Answering questions about the platform
   - Telling occasional college jokes! 😄

---

## 💳 Payment Methods

| Method | Description |
|--------|-------------|
| **Crypto** | Pay with Sepolia ETH (testnet) via MetaMask |
| **UPI** | Manual UPI transfer with verification |
| **Net Banking** | Bank transfer flow |
| **Cash** | Counter payment with challan system |

---

## 🛠️ Tech Stack

### Frontend
- Next.js 14 (App Router)
- React 18 + TypeScript
- Tailwind CSS + Framer Motion
- macOS-style UI components

### Backend
- Next.js API Routes
- MongoDB + Mongoose
- JWT Authentication
- Socket.IO (real-time chat)

### Voice Agent
- **LiveKit** - Real-time audio
- **Deepgram** - Speech-to-Text
- **Cerebras AI** - LLM (Llama 3.1)
- **Cartesia** - Text-to-Speech

### Web3
- RainbowKit + wagmi
- Sepolia Testnet

---

## 📁 Project Structure

```
├── app/                    # Next.js App Router
│   ├── api/               # API routes
│   ├── dashboard/         # Main dashboard
│   └── payment/           # Payment page
├── components/
│   ├── macos/             # macOS UI components
│   ├── payment/           # Payment components
│   └── voice/             # Voice assistant UI
├── voice-agent/           # Python voice agent
│   ├── agent.py           # Main agent file
│   └── requirements.txt   # Python dependencies
├── database/              # MongoDB models
├── hooks/                 # React hooks
├── lib/                   # Utilities & actions
└── public/                # Static assets
```

---

## 🔧 Troubleshooting

### Voice agent not connecting?
- Ensure all API keys are set in `.env.local`
- Check if LiveKit worker is registered (look for "registered worker" in terminal)

### MongoDB connection issues?
- Verify `MONGODB_URI` in `.env.local`
- Check if your IP is whitelisted in MongoDB Atlas

### Payment not working?
- For crypto: Ensure MetaMask is on Sepolia testnet
- Get test ETH from [Sepolia Faucet](https://sepoliafaucet.com)

---

## 📜 License

MIT License - Feel free to use and modify!

---

## 👨‍💻 Author

**Sharvatanay Patil**
BCA Department NHCK
