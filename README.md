# Clinical Consensus System - Powered by Qwen3-32B

Multi-agent AI system where specialized medical agents independently analyze clinical cases and reach diagnostic consensus.

[![Python 3.8+](https://img.shields.io/badge/python-3.8+-blue.svg)](https://www.python.org/downloads/)
[![Gradio](https://img.shields.io/badge/gradio-latest-orange.svg)](https://gradio.app/)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Qwen3-32B](https://img.shields.io/badge/Model-Qwen3--32B-purple.svg)](https://huggingface.co/Qwen/Qwen3-32B)

---

## Overview

Clinical Consensus System is a multi-agent artificial intelligence platform designed to replicate collaborative diagnostic processes used in complex medical cases. Instead of relying on a single AI model, this system orchestrates multiple specialized medical agents that independently analyze cases and synthesize findings into unified diagnostic recommendations.

This approach reduces AI hallucinations and diagnostic errors by leveraging collective intelligence of domain-specific agents, mimicking real-world medical panel reviews.

### Why Multi-Agent?

Traditional single-model AI systems face critical challenges:
- Hallucinations and incorrect medical information
- Missing diagnoses outside primary focus area
- Inconsistent quality across medical domains

Multi-agent approach addresses these through:
- Independent analysis from each specialist
- Cross-validation to reduce individual errors
- Domain-specific expertise for each specialty

---

## System Architecture

```
Clinical Case Input
        ↓
Triage Agent (selects 5 relevant specialists)
        ↓
Parallel Specialist Analysis
  Cardiology | Neurology | Pulmonology | Endocrinology | Nephrology
        ↓
Consensus Synthesis (senior physician agent)
        ↓
Final Diagnostic Recommendation
```

---

## Medical Domains Covered

The system includes specialized agents for 10+ medical domains:

**Cardiology** - Cardiovascular diseases, heart failure, arrhythmias  
**Neurology** - Stroke, seizures, neurodegenerative disorders  
**Pulmonology** - Respiratory diseases, COPD, pneumonia  
**Gastroenterology** - Digestive disorders, liver disease  
**Endocrinology** - Diabetes, thyroid disorders, metabolic conditions  
**Nephrology** - Kidney disease, electrolyte imbalances  
**Hematology** - Blood disorders, anemia, coagulation issues  
**Infectious Disease** - Sepsis, antimicrobial management  
**Rheumatology** - Autoimmune conditions, arthritis  
**Oncology** - Cancer diagnosis and management  

Each agent provides: key findings, differential diagnoses, recommended tests, treatment considerations, and critical red flags.

---

## Installation

### Prerequisites

- Python 3.8 or higher
- HuggingFace API token

### Quick Install

```bash
pip install gradio openai
```

---

## Quick Start

**1. Clone the repository**
```bash
git clone [https://github.com/yourusername/clinical-consensus-system.git](https://github.com/sufirumii/Medical-Panel-Analyzer---Powered-by-Qwen3-32B)
cd clinical-consensus-system
```

**2. Configure API token**

Open the main file and add your HuggingFace API token on line 9.

**3. Run the application**

**4. Access the interface**

Local: `http://127.0.0.1:7860`  
Colab: Public shareable link generated automatically

---

## How It Works

### Three-Stage Process

**Stage 1: Triage**  
Initial agent analyzes the case and selects 5 most relevant specialists based on symptoms, vital signs, labs, and patient history.

**Stage 2: Parallel Analysis**  
Selected specialists independently evaluate the case from their domain perspective. Each provides findings, differential diagnoses, recommended tests, and treatment considerations.

**Stage 3: Consensus Synthesis**  
Senior physician agent reviews all opinions, identifies agreements/conflicts, ranks diagnoses by likelihood, and provides unified recommendations with confidence levels.

### Agent Prompting

Each specialist receives domain-specific prompts:
```
You are a highly experienced {SPECIALTY} specialist.
Analyze this case from your specialty's perspective.
Provide: key findings, differential diagnoses, 
recommended tests, treatment considerations.
Be concise, evidence-based, flag red flags.
```

---

## Example Use Case

**Input:**
```
58 year old man with chest pain for 2 hours. Started while mowing lawn.
Sharp pain in center of chest going to left arm. Sweating heavily.

Past history: High blood pressure. Smokes 1 pack/day for 30 years.
Father died of heart attack at age 60.

Exam: BP 170/100, pulse 95. Pale and sweaty.
Labs: Troponin 2.1 (elevated). Glucose 180.
```

**Output:**
- Triage: Cardiology, Pulmonology, Endocrinology, Nephrology, Internal Medicine
- Cardiology: STEMI likely, immediate catheterization needed
- Consensus: Acute Myocardial Infarction, High confidence
- Actions: Activate cath lab, aspirin, beta-blocker, heparin

---

## Technical Details

**Technology Stack**
- Language: Python 3.8+
- UI Framework: Gradio
- Model: Qwen3-32B via HuggingFace API
- API Client: OpenAI-compatible

**Model Configuration**
- Temperature: 0.3-0.7 (varies by agent role)
- Max tokens: 800-1500
- Top-p: 0.8-0.95

**Performance**
- Triage: 3-5 seconds
- Per-specialist: 5-8 seconds
- Total processing: 40-60 seconds for 5 specialists
- API calls: 7 total (1 triage + 5 specialists + 1 consensus)

---

## Limitations

**This system is for research and educational purposes only.**

Key limitations:
- Not for clinical use or real patient care
- Can generate incorrect medical information
- May miss critical diagnoses
- Based on training data with January 2025 cutoff
- Do not input real patient data or PHI
- All outputs require validation by healthcare professionals

---

## Contributing

Contributions welcome. Fork the repository, create a feature branch, commit changes, and open a pull request.

**Areas for improvement:**
- Additional medical specialties
- Medical imaging analysis
- Evaluation benchmarks
- Multilingual support
- API endpoint for programmatic access

---

## License

MIT License - see LICENSE file for details.

---

## Acknowledgments

Qwen Team at Alibaba for Qwen3-32B  
HuggingFace for model hosting and API  
Gradio for web interface framework  

---

## Citation

```bibtex
@software{clinical_consensus_system_2025,
  title={Clinical Consensus System: Multi-Agent AI for Medical Diagnosis},
  author={Rumi Sufi},
  year={2025},
  url={https://github.com/sufirumii/Medical-Panel-Analyzer---Powered-by-Qwen3-32B}
}
```

---

## Contact

GitHub Issues: [Create an issue]([https://github.com/yourusername/clinical-consensus-system](https://github.com/sufirumii/Medical-Panel-Analyzer---Powered-by-Qwen3-32B)/issues)  
Email: sufirumii@gmail.com
LinkedIn: [Your Profile](https://www.linkedin.com/in/rumi-sufi-6323a5265/)

---

## Disclaimer

FOR RESEARCH AND EDUCATIONAL PURPOSES ONLY. This software is provided "as is" without warranty. Authors are not liable for any medical decisions based on system outputs. Always consult qualified healthcare professionals for medical advice.

---

Made for advancing medical AI research. Star this repo if you find it helpful.
