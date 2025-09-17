# 🎶 Music Source Separation using Deep U-Net Architectures  
**Selected Topics for Music and Acoustic Engineering — 2024/2025**  
*Stefano Polimeno, Riccardo Corà, Riccardo Moschen*  

---

## 📌 Overview  
This project explores **music source separation**, the task of isolating individual instruments (vocals, drums, bass, other) from a mixture audio signal. We investigate both **traditional signal processing approaches** and **deep learning models**, with a focus on **U-Net-based architectures** enhanced with:  
- **BiLSTM bottlenecks** for temporal modeling  
- **Attention-gated skip connections**  
- **Instance Normalization** for improved training stability  

Our models are trained and evaluated on the **MUSDB18 dataset**, the standard benchmark for music source separation.  

---

## ⚡ Key Contributions  
- ✅ Implementation of classical separation methods: Wiener filtering, Binary Masking, HPSS, NMF, Spectral Subtraction  
- ✅ Design of a **BiLSTM-enhanced U-Net** with attention and normalization strategies  
- ✅ Evaluation using standard separation metrics:  
  - **SDR (Signal-to-Distortion Ratio)**  
  - **SIR (Signal-to-Interference Ratio)**  
  - **SAR (Signal-to-Artifacts Ratio)**  
- ✅ Comprehensive analysis of strengths, limitations, and trade-offs between traditional methods and deep neural models  

---

## 📂 Dataset  
We use the [MUSDB18](https://sigsep.github.io/datasets/musdb.html) dataset:  
- 150 full-length stereo tracks (~10 hours of audio)  
- 4 isolated stems: **vocals, drums, bass, other**  
- Provided at 44.1 kHz, split into training (100) and test (50) tracks  

---

## 🏗️ Methodology  
1. **Baselines:** Spectral masking, HPSS, NMF, spectral subtraction  
2. **Deep U-Net:** Encoder–decoder with skip connections  
3. **Enhancements:**  
   - BiLSTM at bottleneck  
   - Attention-gated skip connections  
   - InstanceNorm + dropout for regularization  
4. **Output:** Multi-source mask prediction (vocals, drums, bass, other)  

---

## 📊 Results  
- **SDR:** 3.22 ± 2.91 dB → moderate separation quality  
- **SIR:** 6.42 ± 6.33 dB → reasonable suppression of interfering sources  
- **SAR:** 0.31 ± 4.65 dB → artifacts introduced by recurrent layers  

**Key Insight:**  
BiLSTM enhances temporal modeling but introduces artifacts, highlighting the trade-off between **temporal understanding** and **signal fidelity**.  

---

## 🔮 Future Work  
- Reduce processing artifacts via alternative temporal modeling strategies  
- Improve phase consistency in reconstruction  
- Explore genre-adaptive models and attention refinements  

---

## 📚 References  
- Ronneberger et al. (2015) — U-Net  
- Jansson et al. (2017) — Singing voice separation with deep U-Nets  
- Rafii et al. (2017) — MUSDB18 dataset  
- Défossez et al. (2019) — Demucs  
- Driedger & Müller (2014) — HPSS  
