# 🫀 Deep ECG Mining for Arrhythmia Detection

**Interactive research dashboard** presenting findings from my M.S. thesis at Purdue University on deep learning approaches for ECG-based arrhythmia classification under varying noise conditions.

![Python](https://img.shields.io/badge/Python-3776AB?style=flat&logo=python&logoColor=white)
![PyTorch](https://img.shields.io/badge/PyTorch-EE4C2C?style=flat&logo=pytorch&logoColor=white)
![Purdue](https://img.shields.io/badge/Purdue_University-CFB991?style=flat&logoColor=black)

## 🔬 Live Dashboard

**[→ View Interactive Results](https://shreepatnaik.github.io/ecg-arrhythmia-detection/)**

The dashboard includes:
- Animated ECG waveform monitor
- Interactive beat class visualization (Normal, Supraventricular, Ventricular, Fusion)
- Noise degradation demo (Clean → 20dB → 10dB → 5dB SNR)
- Model comparison charts (LSTM vs MLP vs Fine-tuned LSTM)
- Interactive confusion matrices per noise condition
- Per-class F1 radar chart
- Fine-tuning impact analysis

## 📊 Key Results

| Model | Clean | High SNR (20dB) | Low SNR (10dB) |
|-------|-------|-----------------|----------------|
| MLP | 95.2% | 90.1% | 79.5% |
| **LSTM** | **99.0%** | **96.8%** | 89.4% |
| LSTM + Fine-tune | 99.0% | 97.1% | **93.7%** |

## 🔑 Key Findings

1. **LSTM captures temporal ECG dynamics** that MLP cannot — the accuracy gap widens from 3.8% (clean) to 9.9% (low SNR)
2. **Fine-tuning on noisy data is critical** — recovers 4.3% accuracy at 10dB SNR, making deployment viable in noisy clinical environments
3. **Fusion beats are the hardest class** — lowest per-class F1 due to hybrid morphology and limited training samples
4. **SNR threshold for clinical use** — above 20dB both models work; below 10dB only fine-tuned LSTM remains reliable

## 🏗️ Research Details

- **Lab:** UBIEI Lab, Purdue University
- **Thesis:** *High Performance Distributed Deep Learning on LLMs for Prediction Analysis*
- **Degree:** M.S. Computer Engineering — Machine Learning Focus (2022–2024)
- **Dataset:** MIT-BIH Arrhythmia Database (PhysioNet) — 48 records, ~110K annotated heartbeats
- **Models:** Bidirectional LSTM (primary), MLP (baseline), evaluated under Clean/High-SNR/Low-SNR conditions

## 📁 Repository Structure

```
ecg-arrhythmia-detection/
├── index.html          # Interactive research dashboard (GitHub Pages)
└── README.md           # This file
```

> **Note:** Source code for model training and evaluation is maintained in a private repository. This public repo contains the research dashboard and results only.

## 🛠️ Tech Stack

- **Training:** Python, PyTorch, scikit-learn, wfdb
- **Data:** MIT-BIH Arrhythmia Database (PhysioNet)
- **Dashboard:** HTML, Chart.js, Canvas API
- **Compute:** Multi-GPU distributed training

## 📄 License

Dashboard code: MIT. Research findings are from original thesis work.

---

*Built by [Shree Patnaik](https://linkedin.com/in/shree-patnaik-pu) — Purdue University, UBIEI Lab*
