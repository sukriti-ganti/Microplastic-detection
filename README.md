# MicroSense Pi: Microplastic-detection
### Portable Microplastic Detection System using Raspberry Pi 2 Model B and AI-based Image Processing

---

## Overview
**MicroSense Pi** is a lightweight, low-cost prototype designed to detect microplastic contamination in water samples using a **Raspberry Pi 2 Model B** and a **USB webcam**.  
The system captures real-time images of the sample, analyzes them using **computer vision** and a **lightweight ML model**, and provides **visual (LED)** and **audio (buzzer)** alerts when microplastic-like particles are detected.  

It is designed for **hackathon demonstrations**, **field deployment**, and **R&D prototyping**, combining core ECE and AI-ML skills into one integrated solution.

---

## System Architecture
Water Sample → USB Webcam → Raspberry Pi 2 (Image Processing + ML)
↓
Stepper Motor (Sample Positioning)
↓
LED / Buzzer (Visual & Audio Alerts)

## Workflow

1. **Image Capture:** USB webcam captures water sample frames.  
2. **Preprocessing:** Images converted to grayscale, filtered, and thresholded.  
3. **Detection:** Contours & brightness variations analyzed via ML model (SVM/logistic regression).  
4. **Actuation:**  
   - If contamination detected → Red LED + buzzer alert  
   - If clean → Green LED on  
5. **Automation:** Stepper motor moves sample to scan multiple regions.  
6. **Visualization:** Optional Flask dashboard shows particle count and detection confidence.

---

## Features
- Real-time detection of visible microplastic-like particles (≥80 µm)  
- Portable and standalone (powered by Raspberry Pi)  
- AI-assisted classification (lightweight SVM/TinyML)  
- Multi-modal feedback: LEDs + buzzer + dashboard  
- Affordable and reproducible for academic or field use

---

## Team Roles

| Member | Role | Responsibilities |
|---------|------|------------------|
| **Sukriti (Lead)** | System Integration | Raspberry Pi setup, overall workflow, final testing |
| **Harini** | Documentation & UI | Flask dashboard, presentation, project documentation |
| **Akshaj** | ML & Image Processing | AI model, dataset prep, feature extraction |
| **Bhuvanesh** | Hardware Automation | Stepper motor, LED, and buzzer control |

---

## Setup Instructions

1. **Flash OS:**  
   - Raspberry Pi OS (Legacy, 32-bit) to microSD card via Raspberry Pi Imager.  

2. **Install Dependencies on Pi:**
   ```bash
   sudo apt update
   sudo apt install python3-opencv python3-numpy python3-flask python3-sklearn python3-rpi.gpio python3-pigpio -y
