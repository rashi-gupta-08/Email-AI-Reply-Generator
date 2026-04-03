# 📧 Email AI Reply Generator

An AI-powered full-stack application that generates professional email replies using **Google Gemini API**. The project consists of three components: a **Spring Boot** backend, a **React** frontend, and a **Chrome Extension** for seamless Gmail integration.

---

## 🏗️ Project Structure

```
Email-AI-Reply-Generator/
├── email-writter-sb/       # Spring Boot backend (REST API)
├── email-writer-react/     # React frontend (Vite + Material UI)
└── hello-world-ext/        # Chrome Extension for Gmail
```

---

## ✨ Features

- 🤖 **AI-Powered Replies** — Generate context-aware email responses using Google Gemini API
- 🎭 **Tone Selection** — Choose from tones like Professional, Friendly, Casual, and more
- 🌐 **Web Interface** — Clean React UI to paste emails and generate replies instantly
- 🔌 **Chrome Extension** — Adds an "AI Reply" button directly inside Gmail
- ⚡ **Fast REST API** — Spring Boot backend handles AI communication efficiently

---

## 🛠️ Tech Stack

| Layer | Technology |
|---|---|
| Backend | Java 17, Spring Boot, Maven |
| Frontend | React (Vite), Material UI, Axios |
| Chrome Extension | JavaScript, Chrome Extension API, Gmail DOM |
| AI Model | Google Gemini API |

---

## 📋 Prerequisites

Before getting started, make sure you have:

- Java JDK 17+
- Maven
- Node.js 16+
- npm
- A [Google Gemini API Key](https://aistudio.google.com/app/apikey)
- Google Chrome (for the extension)

---

## 🚀 Getting Started

### 1. Clone the Repository

```bash
git clone https://github.com/navdeep03-03/Email-AI-Reply-Generator.git
cd Email-AI-Reply-Generator
```

---

### 2. Backend Setup (Spring Boot)

```bash
cd email-writter-sb
```

Create an `application.properties` file (or update the existing one) inside `src/main/resources/`:

```properties
gemini.api.key=your-gemini-api-key
gemini.api.url=https://generativelanguage.googleapis.com/v1beta/models/gemini-pro:generateContent
server.port=8080
```

Build and run the backend:

```bash
mvn clean install
mvn spring-boot:run
```

The API will be available at `http://localhost:8080`.

#### API Endpoint

```
POST /api/email/generate
Content-Type: application/json

{
  "emailContent": "Original email text here...",
  "tone": "professional"
}
```

---

### 3. Frontend Setup (React)

```bash
cd ../email-writer-react
npm install
npm run dev
```

The app will be available at `http://localhost:5173`.

> **Note:** Ensure the backend is running before using the frontend. Update the API base URL in the frontend config if needed.

---

### 4. Chrome Extension Setup

```bash
cd ../hello-world-ext
```

**Load the extension in Chrome:**

1. Open Chrome and navigate to `chrome://extensions/`
2. Enable **Developer mode** (toggle in the top-right corner)
3. Click **"Load unpacked"**
4. Select the `hello-world-ext` folder
5. The extension is now installed ✅

**Using the extension:**

1. Open [Gmail](https://mail.google.com) in Chrome
2. Open any email and click **Reply**
3. An **"AI Reply"** button will appear in the reply toolbar
4. Click it — the AI-generated reply will be inserted automatically

---

## 📁 Key Files

```
email-writter-sb/
└── src/main/java/com/email/emailWritter/
    ├── EmailGeneratorController.java   # REST controller
    └── EmailGeneratorService.java      # Gemini API integration

email-writer-react/
└── src/
    ├── App.jsx                         # Main UI component
    └── main.jsx                        # React entry point

hello-world-ext/
├── manifest.json                       # Extension configuration
└── content.js                          # Gmail DOM injection script
```

---

## 🧩 How It Works

```
User pastes email (React UI or Gmail Extension)
        ↓
React/Extension sends POST request to Spring Boot API
        ↓
Spring Boot calls Google Gemini API with email + tone
        ↓
Gemini generates a context-aware reply
        ↓
Reply is returned and displayed to the user
```

---

## 🌐 Deployment

| Component | Recommended Platform |
|---|---|
| Spring Boot Backend | Render / Railway / AWS |
| React Frontend | Netlify / Vercel |
| Chrome Extension | Chrome Web Store (or load unpacked locally) |

> Remember to update the API endpoint in the frontend and extension to point to your deployed backend URL.

---

## 🤝 Contributing

Contributions are welcome! Feel free to:

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/your-feature`)
3. Commit your changes (`git commit -m 'Add your feature'`)
4. Push to the branch (`git push origin feature/your-feature`)
5. Open a Pull Request

---

## 📄 License

This project is open source. See the [LICENSE](LICENSE) file for details.

---

## 👤 Author

**Navdeep** — [@navdeep03-03](https://github.com/navdeep03-03)
**Rashi** -[@rashi-gupta-08](https://github.com/rashi-gupta-08)
