# 🤖 Local AI Chatbot with Ollama

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Ollama](https://img.shields.io/badge/Ollama-Powered-blue)](https://ollama.ai)
[![HTML5](https://img.shields.io/badge/HTML5-E34F26?logo=html5&logoColor=white)](https://developer.mozilla.org/en-US/docs/Web/HTML)
[![JavaScript](https://img.shields.io/badge/JavaScript-F7DF1E?logo=javascript&logoColor=black)](https://developer.mozilla.org/en-US/docs/Web/JavaScript)

> Build your own AI chatbot in 10 minutes - no API fees, no complex setups, complete control over your project.

![AI Chatbot Demo](https://img.shields.io/badge/Status-Production%20Ready-success)

## 📋 Table of Contents

- [About the Project](#-about-the-project)
- [Features](#-features)
- [Prerequisites](#-prerequisites)
- [Installation](#-installation)
- [Usage](#-usage)
- [CORS Configuration](#-cors-configuration)
- [Available Models](#-available-models)
- [Customization](#-customization)
- [Troubleshooting](#-troubleshooting)
- [Contributing](#-contributing)
- [License](#-license)
- [Author](#-author)

## 🎯 About the Project

This project demonstrates how to create a fully functional AI chatbot that runs **completely locally** on your machine, leveraging the power of Large Language Models (LLMs) through Ollama. No API keys required, no recurring costs, and complete data privacy.

### Why this project?

- ✅ **100% Local**: Your data never leaves your machine
- ✅ **Zero Cost**: No API fees or subscriptions
- ✅ **Privacy First**: Complete control over your conversations
- ✅ **Educational**: Perfect for understanding how LLMs work
- ✅ **Customizable**: Simple, easy-to-modify code

## ✨ Features

- 🚀 Modern and responsive web interface
- 💬 Real-time chat with streaming responses
- 🎨 Clean and intuitive design
- ⚡ Fast responses with local models
- 🔄 Conversation history
- 📱 Mobile-friendly
- 🌐 Works offline after initial setup

## 🔧 Prerequisites

Before you begin, make sure you have:

- **Operating System**: Windows, macOS, or Linux
- **Disk Space**: Minimum 4GB free (for the model)
- **RAM**: 8GB or more recommended
- **Web Browser**: Chrome, Firefox, Safari, or Edge (recent versions)

## 📥 Installation

### Step 1: Install Ollama

Ollama is the core engine for our chatbot.

1. Visit [ollama.ai/download](https://ollama.ai/download)
2. Download the appropriate version for your operating system
3. Run the installer and follow the prompts

**Verify installation:**

```bash
ollama --version
```

### Step 2: Download an AI Language Model

For this project, we'll use the `gemma:2b` model (efficient and fast):

```bash
ollama run gemma:2b
```

> **Note**: The download may take a few minutes the first time. After downloading, you'll enter interactive chat mode. Type `/bye` to exit.

### Step 3: Clone the Project

```bash
git clone https://github.com/wwwwaterson/arquivos.git
cd arquivos
```

Or simply download the `index.html` file from this repository.

## 🚀 Usage

### Start the Ollama Server

Open a terminal and run:

```bash
ollama serve
```

> **Important**: Keep this terminal open while using the chatbot.

### Open the Web Interface

1. Locate the `index.html` file in your file explorer
2. Double-click to open it in your browser
3. Start chatting with the AI!

**Or use a local server (optional):**

```bash
# Python 3
python -m http.server 8000

# Access: http://localhost:8000
```

## 🔐 CORS Configuration

If you encounter a **"Cross-Origin Request Blocked"** error in your browser console, configure CORS:

### Windows (PowerShell)

```powershell
$env:OLLAMA_ORIGINS='*'
ollama serve
```

### macOS / Linux (Terminal)

```bash
OLLAMA_ORIGINS='*' ollama serve
```

> **Security Tip**: In production, replace `*` with the specific URL (e.g., `http://localhost:8000`), but `*` works for direct file access.

## 🤖 Available Models

Try different models for various use cases:

| Model | Size | Best For | Command |
|-------|------|----------|---------|
| `gemma:2b` | ~1.4GB | General use, fast | `ollama run gemma:2b` |
| `llama3` | ~4.7GB | Complex conversations | `ollama run llama3` |
| `codellama` | ~3.8GB | Programming | `ollama run codellama` |
| `mistral` | ~4.1GB | Text analysis | `ollama run mistral` |
| `phi3` | ~2.3GB | Specific tasks | `ollama run phi3` |

**Switch models**: Edit the line in `index.html`:

```javascript
model: 'gemma:2b'  // Change to your desired model
```

## 🎨 Customization

### Modify Visual Style

Edit the CSS variables in `index.html`:

```css
:root {
    --primary-color: #667eea;      /* Primary color */
    --secondary-color: #764ba2;    /* Secondary color */
    --background: #0f172a;         /* Background */
    --chat-bg: #1e293b;           /* Chat background */
}
```

### Adjust Model Parameters

Modify generation options:

```javascript
temperature: 0.7,    // Creativity (0.0 - 1.0)
top_p: 0.9,         // Response diversity
top_k: 40,          // Number of tokens considered
```

### Add System Prompt

Customize AI behavior:

```javascript
messages: [
    {
        role: 'system',
        content: 'You are a helpful and friendly assistant.'
    },
    ...messages
]
```

## 🐛 Troubleshooting

### Error: "Failed to fetch"

**Cause**: Ollama is not running or CORS is not configured.

**Solution**:
1. Verify that `ollama serve` is active
2. Configure CORS as per [section above](#-cors-configuration)

### Slow Responses

**Cause**: Model too large for your hardware.

**Solution**:
- Use smaller models (`gemma:2b`, `phi3`)
- Close other heavy applications
- Consider upgrading RAM

### Model Not Found

**Cause**: Model was not downloaded.

**Solution**:
```bash
ollama pull gemma:2b
```

### Port 11434 in Use

**Cause**: Another Ollama instance is running.

**Solution**:
```bash
# Windows
taskkill /F /IM ollama.exe

# macOS/Linux
pkill ollama
```

## 🤝 Contributing

Contributions are welcome! To contribute:

1. Fork the project
2. Create a feature branch (`git checkout -b feature/AmazingFeature`)
3. Commit your changes (`git commit -m 'Add some AmazingFeature'`)
4. Push to the branch (`git push origin feature/AmazingFeature`)
5. Open a Pull Request

### Guidelines

- Keep code simple and readable
- Add comments when necessary
- Test your changes before submitting
- Update documentation if applicable

## 📄 License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## 👨‍💻 Author

**Anderson Magalhães**

- LinkedIn: [Anderson Magalhães](https://www.linkedin.com/in/andersonmagalhaes-fullstack)
- GitHub: [@wwwwaterson](https://github.com/wwwwaterson)
- Expertise: AI Engineer | Full Stack Developer & LLM Integration

---

## 🌟 Next Steps

Now that you have your chatbot running, explore:

1. **Framework Integration**: Migrate to React, Vue, or Next.js
2. **Persistence**: Add database to save conversations
3. **RAG (Retrieval-Augmented Generation)**: Connect with your documents
4. **Fine-tuning**: Train custom models
5. **Deployment**: Put into production with Docker

## 💡 Additional Resources

- [Official Ollama Documentation](https://github.com/ollama/ollama)
- [Available Models List](https://ollama.ai/library)
- [Ollama Community on Discord](https://discord.gg/ollama)
- [Prompt Examples](https://github.com/ollama/ollama/blob/main/docs/api.md)

---

<div align="center">

**The power of artificial intelligence is at your fingertips. What will you create next?**

⭐ If this project was helpful, consider giving it a star!

</div>
