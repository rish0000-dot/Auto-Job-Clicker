# 🤖 AI Auto Job Applier - LinkedIn

> **Automate Your Job Search:** Apply to 100+ LinkedIn jobs in less than 1 hour with AI-powered resume customization

[![Python Version](https://img.shields.io/badge/Python-3.10%2B-blue?style=flat-square)](https://www.python.org/downloads/)
[![License](https://img.shields.io/github/license/rish0000-dot/Auto-Job-Clicker?style=flat-square)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-Welcome-brightgreen?style=flat-square)](https://github.com/rish0000-dot/Auto-Job-Clicker/pulls)

---

## 📋 Table of Contents

- [Features](#-features)
- [Demo](#-demo)
- [Quick Start](#-quick-start)
- [Installation](#%EF%B8%8F-installation)
- [Configuration](#-configuration)
- [Usage](#-usage)
- [Project Structure](#-project-structure)
- [AI Models Supported](#-ai-models-supported)
- [Troubleshooting](#-troubleshooting)
- [Contributing](#-contributing)
- [License](#-license)
- [Support](#-support)

---

## ✨ Features

✅ **Intelligent Job Search** - Automatically searches LinkedIn for jobs matching your criteria
✅ **AI-Powered Resume Customization** - Tailors your resume for each position using AI
✅ **Form Auto-Fill** - Automatically answers application questions
✅ **Batch Processing** - Apply to 100+ jobs per hour
✅ **Multi-AI Support** - Supports OpenAI ChatGPT, Google Gemini, and DeepSeek
✅ **Application History** - Tracks all applications with a web dashboard
✅ **Skill Extraction** - Automatically extracts required skills from job postings
✅ **Resume Generation** - Dynamically generates customized resumes
✅ **Company Information** - Gathers company details for context-aware applications
✅ **Web Dashboard** - View application history and statistics

---

## 📹 Demo

Watch the bot in action:

[![Auto Job Applier Demo](https://img.youtube.com/vi/gMbB1fWZDHw/maxresdefault.jpg)](https://youtu.be/gMbB1fWZDHw)
**[Click to Watch Full Demo →](https://youtu.be/gMbB1fWZDHw)**

**Setup Tutorial:** [Installation & Configuration Guide](https://youtu.be/f9rdz74e1lM)


---

## 🚀 Quick Start

```bash
# 1. Clone the repository
git clone https://github.com/rish0000-dot/Auto-Job-Clicker.git
cd Auto-Job-Clicker/Auto_job_applier_linkedIn-main

# 2. Install dependencies
pip install -r requirements.txt

# 3. Configure your details
# Edit config/personals.py with your information

# 4. Run the bot
python app.py
```

---

## ⚙️ Installation

### Prerequisites

- **Python 3.10+** - [Download Here](https://www.python.org/downloads/)
- **Google Chrome** - [Download Here](https://www.google.com/chrome)
- **Internet Connection**

### Step-by-Step Installation

#### Step 1: Install Python
```bash
# Verify Python installation
python --version
# Output should be: Python 3.10.x or higher
```
⚠️ **Important:** Add Python to your system PATH during installation

#### Step 2: Install Required Packages
```bash
pip install -r requirements.txt
```

Required packages:
- `undetected-chromedriver` - Prevent LinkedIn detection
- `pyautogui` - GUI automation
- `openai` - ChatGPT integration
- `flask` & `flask-cors` - Web server for dashboard
- `setuptools` - Build tools

#### Step 3: Install ChromeDriver
**For Windows:**
```bash
# Run the automatic setup script
cd setup
windows-setup.bat
```

**For macOS/Linux:**
```bash
bash setup.sh
```

**Manual Installation:**
1. Download [Chrome Driver](https://googlechromelabs.github.io/chrome-for-testing/) matching your Chrome version
2. Place it in your Chrome installation directory

#### Step 4: Clone Repository
```bash
git clone https://github.com/rish0000-dot/Auto-Job-Clicker.git
cd Auto-Job-Clicker/Auto_job_applier_linkedIn-main
```

---

## 🔧 Configuration

### 1. Personal Information (`config/personals.py`)
```python
# Enter your details
FIRST_NAME = "Your Name"
LAST_NAME = "Your Last Name"
EMAIL = "your.email@example.com"
PHONE = "+1 (555) 000-0000"
ADDRESS = "City, State"
COUNTRY = "United States"
```

### 2. Job Search Settings (`config/search.py`)
```python
# Customize your job search
KEYWORDS = ["Python Developer", "Data Scientist", "Full Stack Engineer"]
LOCATION = "United States"
EXPERIENCE_LEVEL = ["Entry level", "Mid-Senior"]
DISTANCE = "50 miles"  # or "anywhere"
JOB_TYPES = ["Full-time", "Contract"]
```

### 3. Application Questions (`config/questions.py`)
```python
# Pre-answer common questions
ANSWERS = {
    "Are you legally authorized to work?": "Yes",
    "Willing to relocate?": "No",
    # Add your custom answers
}
```

### 4. Resume (`config/resume.py`)
```python
# Your base resume data
BASE_RESUME = """
Your resume content in plain text format
"""
```

### 5. AI Provider Settings (`config/settings.py`)
```python
# Choose your AI provider
AI_PROVIDER = "openai"  # Options: "openai", "gemini", "deepseek"
STEALTH_MODE = True  # Avoid LinkedIn detection
MAX_APPLICATIONS = 100
APPLICATION_DELAY = 2  # Seconds between applications
```

### 6. API Keys (`config/secrets.py`)
```python
# Add your API credentials (DO NOT COMMIT THIS FILE)
OPENAI_API_KEY = "sk-xxxxxxxxxxxxxxx"
GEMINI_API_KEY = "xxxxxxxxxxxxxxx"
DEEPSEEK_API_KEY = "xxxxxxxxxxxxxxx"

# LinkedIn credentials
LINKEDIN_EMAIL = "your.email@example.com"
LINKEDIN_PASSWORD = "your_password"
```

⚠️ **Security Warning:** Never commit `secrets.py` to version control. Add it to `.gitignore`.

---

## 🎮 Usage

### Start the Bot
```bash
# Navigate to project directory
cd Auto_job_applier_linkedIn-main

# Run the main application
python app.py
```

### Monitor Applications
Open your browser and go to:
```
http://localhost:5000
```

View your application history, success rate, and statistics.

### Run Background Bot
```bash
# Start bot in the background (applies jobs continuously)
python runAiBot.py
```

---

## 📁 Project Structure

```
Auto-Job-Clicker/
├── Auto_job_applier_linkedIn-main/
│   ├── app.py                          # Flask web server
│   ├── runAiBot.py                    # Main automation script
│   ├── config/                         # Configuration files
│   │   ├── personals.py               # Personal information
│   │   ├── search.py                  # Job search parameters
│   │   ├── questions.py               # Application answers
│   │   ├── resume.py                  # Resume data
│   │   ├── settings.py                # Bot settings
│   │   └── secrets.py                 # API keys (not in repo)
│   ├── modules/                        # Core functionality
│   │   ├── clickers_and_finders.py    # Browser automation
│   │   ├── helpers.py                 # Utility functions
│   │   ├── open_chrome.py             # Chrome driver setup
│   │   ├── validator.py               # Input validation
│   │   ├── ai/                         # AI integrations
│   │   │   ├── openaiConnections.py
│   │   │   ├── geminiConnections.py
│   │   │   ├── deepseekConnections.py
│   │   │   └── prompts.py             # AI prompts
│   │   ├── resumes/                    # Resume handling
│   │   │   ├── extractor.py           # Extract job requirements
│   │   │   └── generator.py           # Generate customized resumes
│   │   └── images/                     # UI images and icons
│   ├── templates/                      # Web dashboard HTML
│   ├── setup/                          # Installation scripts
│   │   ├── windows-setup.bat
│   │   ├── windows-setup.ps1
│   │   └── setup.sh
│   └── README.md
├── LICENSE
└── .gitignore
```

---

## 🤖 AI Models Supported

### 1. OpenAI (ChatGPT)
```python
AI_PROVIDER = "openai"
# Requires: OPENAI_API_KEY
# Models: GPT-4, GPT-3.5 Turbo
```

### 2. Google Gemini
```python
AI_PROVIDER = "gemini"
# Requires: GEMINI_API_KEY
# Models: Gemini Pro, Gemini Ultra
```

### 3. DeepSeek
```python
AI_PROVIDER = "deepseek"
# Requires: DEEPSEEK_API_KEY
# Models: DeepSeek-V2, DeepSeek-Chat
```

**Recommendation:** OpenAI (GPT-4) provides the best resume customization results.

---

## 🐛 Troubleshooting

### Issue: "Chrome Driver Not Found"
```bash
# Solution 1: Run setup script
cd setup
windows-setup.bat  # Windows

# Solution 2: Manual installation
# Download from: https://googlechromelabs.github.io/chrome-for-testing/
```

### Issue: "LinkedIn Detected As Bot"
```python
# Enable stealth mode in config/settings.py
STEALTH_MODE = True

# Increase delay between applications
APPLICATION_DELAY = 3  # seconds
```

### Issue: "API Key Invalid"
```bash
# Check your secrets.py file
# Verify API keys are correct and have active billing
# Use quotes around keys: "sk-xxxxxxx"
```

### Issue: "Port Already in Use (5000)"
```python
# Edit app.py to use different port
app.run(port=5001)
```

### Issue: "No Applications Found"
```python
# Check your search.py settings
# Verify keywords are correct
# Check LinkedIn job search criteria manually
```

### Enable Debug Mode
```python
# Add to settings.py
DEBUG = True
LOG_LEVEL = "DEBUG"
```

---

## 📊 Features in Detail

### 📝 Resume Customization
The bot analyzes job postings and:
- Extracts required skills
- Identifies key responsibilities
- Analyzes company information
- Customizes your resume to match requirements
- Maintains ATS (Applicant Tracking System) compatibility

### 📋 Application Tracking
Track all applications with:
- Job title and company
- Application timestamp
- HR contact information
- Company profile links
- Application success status

### 🎯 Smart Job Matching
- Filter by location, experience level, job type
- Keyword-based matching
- Salary range filtering
- Company exclusion list support

---

## ⚡ Performance Tips

1. **Increase Application Speed**
   ```python
   APPLICATION_DELAY = 1  # Reduce delay (minutes)
   ```

2. **Use CloudFlare DNS**
   - Speeds up LinkedIn connection

3. **Schedule Batch Applications**
   ```bash
   # Run during off-peak hours for better success
   Python app.py &  # Background process
   ```

4. **Monitor Resource Usage**
   - Chrome can use 200-300MB per instance
   - Limit to 1 browser instance

---

## 🔐 Security

- **Never hardcode credentials** - Use environment variables
- **Rotate API keys regularly** - Update secrets.py weekly
- **Keep dependencies updated** - Run `pip install --upgrade -r requirements.txt`
- **Use strong passwords** - LinkedIn account security is crucial
- **Enable 2FA** - On your LinkedIn account
- **Monitor logs** - Check for unusual activity

---

## 📝 License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

```
MIT License

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software...
```

---

## 🤝 Contributing

We welcome contributions! Please follow these steps:

1. **Fork the Repository**
   ```bash
   git clone https://github.com/rish0000-dot/Auto-Job-Clicker.git
   ```

2. **Create Feature Branch**
   ```bash
   git checkout -b feature/your-feature-name
   ```

3. **Commit Changes**
   ```bash
   git commit -m "Add: Brief description of changes"
   ```

4. **Push to Branch**
   ```bash
   git push origin feature/your-feature-name
   ```

5. **Open Pull Request**
   - Describe your changes clearly
   - Reference any related issues

### Contribution Guidelines
- Follow PEP 8 for Python code
- Add tests for new features
- Update README for significant changes
- Keep commits atomic and descriptive

---

## 💬 Support

### Getting Help

- **GitHub Issues** - Report bugs and feature requests
- **Discord Community** - [Join our Discord](https://discord.gg/fFp7uUzWCY)
- **Email Support** - Open an issue and we'll respond
- **FAQ** - Check [Wiki](https://github.com/rish0000-dot/Auto-Job-Clicker/wiki)

### Common Questions

**Q: Is this against LinkedIn's terms?**
A: This tool respects LinkedIn's rate limits and uses official APIs where available. Use responsibly.

**Q: How many jobs can I apply to per day?**
A: Typically 50-100+ depending on your system and the complexity of applications.

**Q: What's the success rate?**
A: Success depends on many factors - your profile, resume match, and application quality.

**Q: Can I use this with LinkedIn Premium?**
A: Yes, LinkedIn Premium may increase visibility in our targeting options.

---

## 📈 Roadmap

- [ ] Browser extension for easy activation
- [ ] Machine learning for better job matching
- [ ] Email notification system
- [ ] Multi-account support
- [ ] Advanced analytics dashboard
- [ ] Mobile app

---

## ⚠️ Disclaimer

This project is provided as-is for educational purposes. Users are responsible for:
- Ensuring compliance with LinkedIn's Terms of Service
- Using the bot ethically and responsibly
- Maintaining accurate and truthful information in applications
- Respecting LinkedIn's rate limits and policies

**The authors are not responsible for:**
- LinkedIn account suspension or bans
- Inaccurate resume information
- Unauthorized use of this tool
- Any damages or losses incurred

---

## 🙏 Acknowledgments

- Built with ❤️ by the community
- Thanks to all contributors
- Special thanks to AI providers: OpenAI, Google Gemini, DeepSeek

---

## 📱 Connect With Us

- **GitHub** - [rish0000-dot/Auto-Job-Clicker](https://github.com/rish0000-dot/Auto-Job-Clicker)
- **Discord** - [Community Server](https://discord.gg/fFp7uUzWCY)
- **Issues** - [Report or Request](https://github.com/rish0000-dot/Auto-Job-Clicker/issues)

---

<div align="center">

**Made with ❤️ for job seekers everywhere**

⭐ Star this repo if it helped you! ⭐

</div>
