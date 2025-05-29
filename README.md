# 🧠 Multi-Agent Healthcare Assistant (ADK + Google Cloud)

A multi-agent AI system for chronic disease management, powered by the **Agent Development Kit (ADK)** and **Google Cloud**. This system helps monitor patients, stratify risk, generate personalized advice, and proactively engage with users — all autonomously through intelligent agents.

---

## 🚀 Overview

This project orchestrates multiple agents that handle different aspects of chronic disease care such as diabetes or CKD. Each agent is responsible for a specific task and collaborates using ADK.

**Agents:**

- `DataIngestionAgent`: Fetches patient data (CSV, FHIR API, or wearables)
- `AnalyticsAgent`: Analyzes trends using BigQuery
- `RiskStratificationAgent`: Uses trained models to assess patient risk
- `AdviceGenerationAgent`: Creates personalized health advice
- `SupportAgent`: Chatbot powered by Vertex AI / Dialogflow
- `NotificationAgent`: Sends alerts via email/SMS

---

## 🏗️ Project Structure

```
multi-agent-healthcare-assistant/
├── agents/               # All agent logic scripts
├── orchestration/        # Main agent orchestrator
├── data/                 # Sample input data
├── config/               # Settings and API keys
├── notebooks/            # EDA and model exploration
├── app/                  # Optional web dashboard (Streamlit or Flask)
├── requirements.txt      # Python dependencies
├── Dockerfile            # Container setup
├── README.md             # Project guide
```

---

## 🔧 Technologies Used

- **Agent Development Kit (Python)**
- **Google Cloud Platform**
  - BigQuery (analytics)
  - Vertex AI (model deployment, Gemini APIs)
  - Dialogflow (chat interface)
- **Python Libraries**: `pandas`, `scikit-learn`, `streamlit`, `requests`, `openai`
- **Other**: Firebase or Twilio for alerts, Streamlit for UI

---

## ⚙️ Installation

```bash
git clone https://github.com/your-username/multi-agent-healthcare-assistant.git
cd multi-agent-healthcare-assistant
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

---

## 🧪 Run the System

```bash
python orchestration/orchestrator.py
```

Or run the dashboard:

```bash
streamlit run app/dashboard.py
```

---

## 🧩 Agent Design (TypeScript-style Interface)

```ts
interface Agent {
  run(memory: MemoryStore, tools?: Toolchain): Promise<void>;
}
```

### Example Agent (Pseudo-Python logic in TypeScript syntax)

```ts
class AnalyticsAgent implements Agent {
  async run(memory: MemoryStore) {
    const patientData = memory.get("patient_data");
    const insights = analyzeTrends(patientData);
    memory.set("insights", insights);
  }
}
```

---

## 📊 Example Workflow

1. `DataIngestionAgent` pulls vitals from FHIR API.
2. `AnalyticsAgent` detects abnormal BP/glucose patterns.
3. `RiskStratificationAgent` flags high-risk cases.
4. `AdviceGenerationAgent` creates personalized recommendations.
5. `SupportAgent` responds to user queries.
6. `NotificationAgent` sends alerts via email/SMS.

---

## 📽️ Demo

📹 Watch the [demo video](#) to see the end-to-end pipeline with agents collaborating.

---

## 📦 Deployment (Optional)

Build and run in Docker:

```Dockerfile
# Dockerfile
FROM python:3.11
WORKDIR /app
COPY . .
RUN pip install -r requirements.txt
CMD ["python", "orchestration/orchestrator.py"]
```

---

## 📝 License

Licensed under the MIT License.

---

## 🤝 Contributing

Contributions and feature suggestions are welcome. Please open an issue or pull request.

---

## 📫 Contact

Built for the **Agent Development Kit Hackathon** with Google Cloud.  
Author: [Tarun Roy]  
Email: [roy.uiowa at gmail.com]
