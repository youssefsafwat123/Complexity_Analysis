# 🦉 Strivora

> *See the flaws others miss.*

Strivora is an AI-powered code quality analysis tool that detects **SOLID principle violations**, **code complexity**, and **clean code issues** in real-time — then suggests how to fix them.

Built as a graduation project using Python, FastAPI, and React.

---

## 🚀 Features

- ⚡ **Real-time analysis** as you type — no submit button needed
- 🔍 **SOLID Principles Detector** — detects violations in all 5 principles (SRP, OCP, LSP, ISP, DIP)
- 📊 **Complexity Analyzer** — Time and Space complexity estimation (O(1) to O(2^n))
- 🧹 **Clean Code Analyzer** — naming conventions, maintainability index, pylint integration
- 🛠️ **Optimization Report** — suggestions to fix detected violations
- 🐍 Supports **Python** and **Java**

---

## 🏗️ Tech Stack

**Frontend**
- React + TypeScript
- Tailwind CSS
- WebSocket (live connection to backend)

**Backend**
- FastAPI (Python)
- WebSocket endpoint
- AST-based detectors for SOLID, Complexity, and Clean Code
- Radon (maintainability metrics)
- Pylint (code style)

---

## 📁 Project Structure

```
Owlint/
│
├── main.py                          # FastAPI backend — WebSocket orchestration
├── requirements.txt                 # Python dependencies
│
├── Complexity/
│   ├── __init__.py
│   └── Complexity_Code.py           # Time & Space complexity analyzer
│
├── Clean_code/
│   ├── __init__.py
│   └── clean_code.py                # Naming, Radon, Pylint analysis
│
├── SOLID/
│   ├── __init__.py
│   ├── SRP_Detection_Final.py       # Single Responsibility Principle
│   ├── OCP_Detection_Final.py       # Open-Closed Principle
│   ├── Liskov_Substitution_Principle.py  # Liskov Substitution Principle
│   ├── ISP_detect.py                # Interface Segregation Principle
│   └── dependancy_principle.py      # Dependency Inversion Principle
│
└── frontend/                        # React frontend
```

---

## ⚙️ How to Run Locally

### 1. Clone the repository

```bash
git clone https://github.com/your-username/owlint.git
cd owlint
```

### 2. Install Python dependencies

```bash
pip install -r requirements.txt
```

### 3. Make sure Pylint is installed

```bash
pip install pylint
pylint --version  # verify it works
```

### 4. Run the backend

```bash
uvicorn main:app --reload
```

Backend will be running at `ws://localhost:8000/ws/analyze`

### 5. Run the frontend

```bash
cd frontend
npm install
npm start
```

Frontend will be running at `http://localhost:3000`

---

## 🔌 How It Works

```
User types code in the editor
        ↓
React frontend (debounced 500ms)
        ↓
WebSocket → FastAPI backend
        ↓
Runs all detectors in parallel
        ↓
Returns JSON report
        ↓
React displays results in real-time
```

---

## 📦 Requirements

```
fastapi
uvicorn
radon
pylint
lodash (frontend)
```

---

## 👥 Team

Built with ❤️ as a graduation project.

---

## 📄 License

MIT License
