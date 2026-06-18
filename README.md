# 🤖 AI Calculator — Frontend

A React + TypeScript app where you **draw** mathematical expressions on a canvas and get AI-powered solutions rendered as LaTeX — instantly.

[![Live Demo](https://img.shields.io/badge/Live%20Demo-Visit%20App-2E9EF7?style=for-the-badge&logo=vercel&logoColor=white)](https://ai-calculator-frontend-six.vercel.app)
[![Backend](https://img.shields.io/badge/Backend%20Repo-AiCalculatorBackend-239120?style=for-the-badge&logo=github&logoColor=white)](https://github.com/ramansh18/AiCalculatorBackend)

---

## ✨ Features

- 🖊️ **Freehand canvas drawing** with multiple color options
- 🧠 **AI-powered solving** — sends your drawing to Google Gemini via the backend
- 📐 **LaTeX rendering** — results displayed as formatted math using MathJax
- 🖱️ **Draggable result labels** — reposition answers anywhere on screen
- 🔁 **Variable persistence** — assign `x = 5`, reuse it in the next expression
- 🗂️ **Multi-problem support** — arithmetic, algebra, geometry, logic puzzles & more

---

## 🛠️ Tech Stack

| Tech | Purpose |
|------|---------|
| React 18 + TypeScript | UI framework |
| Vite | Build tool |
| Tailwind CSS | Styling |
| Mantine UI | UI components (color swatches, buttons) |
| Axios | API requests to backend |
| MathJax | LaTeX math rendering |
| react-draggable | Draggable result labels on canvas |

---

## 📁 Project Structure

```
src/
├── screens/
│   └── home/
│       └── index.tsx      # Main canvas UI & calculation logic
├── components/
│   └── ui/
│       └── button.tsx     # Reusable button component
├── constants.ts           # Color swatches for the drawing toolbar
├── App.tsx                # App entry & routing
└── main.tsx               # React initialization
```

---

## 🔄 How It Works

1. **Draw** a math expression on the HTML5 canvas
2. **Click Calculate** — canvas is converted to a Base64 PNG
3. **POST request** sent to the FastAPI backend with the image + any saved variables
4. **Backend** processes the image through Google Gemini AI and returns results
5. **Results rendered** as LaTeX on the canvas via MathJax at the drawn position
6. **Drag results** anywhere for better readability

```
Canvas draw → toDataURL() → POST { image, dict_of_vars }
  → Backend (Gemini AI)
  → [{ expr, result, assign }]
  → MathJax LaTeX rendered on canvas
```

---

## 🚀 Getting Started

### Prerequisites
- Node.js v18+
- Backend running locally or use the deployed backend URL

### Installation

```bash
git clone https://github.com/ramansh18/AiCalculatorFrontend.git
cd AiCalculatorFrontend
npm install
```

### Environment Variables

Create a `.env` file in the root:

```env
VITE_API_URL=YOUR_BACKEND_URL
```

### Run Locally

```bash
npm run dev
```

App runs at `http://localhost:5173`

### Build for Production

```bash
npm run build
npm run preview
```

---

## 🔗 Related

> This is the **frontend only**. Math solving happens in the backend:  
> 👉 [AiCalculatorBackend](https://github.com/ramansh18/AiCalculatorBackend) — FastAPI + Google Gemini

---

## 👨‍💻 Author

**Ramansh**  
[![GitHub](https://img.shields.io/badge/GitHub-ramansh18-100000?style=flat&logo=github)](https://github.com/ramansh18)
[![Portfolio](https://img.shields.io/badge/Portfolio-ramansh.is--a.dev-FF5722?style=flat&logo=google-chrome)](https://ramansh.is-a.dev)
