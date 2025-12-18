# microplastic.detection
# MICRONYX × NYXPERT

**IoT–ML System for Rapid Microplastic Detection in Water**
Smart India Hackathon – **Problem Statement ID: 25036**

---

## 📌 Project Status

This repository contains the **working MVP source code** developed for the **Smart India Hackathon (SIH)**. Although the project did not advance to the SIH finals, the MVP demonstrates a complete **end-to-end pipeline** for low-cost microplastic detection using IoT hardware and machine learning.

---

## 🧠 Project Overview

**MICRONYX × NYXPERT** is a hybrid **hardware–software system** designed to detect microplastics in water samples within minutes, avoiding conventional laboratory analysis.

The system consists of:

* **MICRONYX (Hardware MVP):** Water filtration, fluorescent staining, and image acquisition
* **NYXPERT (Software MVP):** Image processing, ML-based object detection, analytics, and reporting

The core goal is to make microplastic detection **accessible, affordable, and scalable**.

---

## 🔧 Hardware (MVP Summary)

The MVP hardware pipeline includes:

* Sample chamber for controlled water flow
* **ESP32-CAM** for image capture
* Nylon blended spandex filter (carbon filter analog)
* Blue LED excitation source
* Fluorescent staining using **highlighter ink + sanitizer** (Nile Red alternative)

### Detection Workflow

1. Water sample passed through the chamber
2. Microplastics trapped by filter
3. Fluorescent dye added
4. Sample rested for **3–8 minutes**
5. Images captured under blue light

These images are sent to the software pipeline for analysis.

---

## 💻 Software Architecture (NYXPERT)

### 1. Image Processing

* **OpenCV** used for MVP-level preprocessing
* Noise reduction, contrast enhancement, and segmentation

### 2. Dataset Creation & Annotation

* **LabelImg** for bounding box annotation
* **Roboflow** for:

  * Dataset management
  * Augmentation
  * Train/validation/test splits

### 3. Machine Learning Model

* **YOLOv8** (Object Detection)
* Chosen for real-time inference and small-object detection capability

**Training Environment:**

* Google Colab (GPU enabled)

### 4. Backend & API

* **Flask** server
* REST APIs for real-time detection and response handling

### 5. Data Handling & Visualization

* **NumPy:** image arrays and numerical operations
* **Pandas:** result storage, CSV export

NYXPERT provides:

* Annotated detection images
* Statistical summaries
* Charts and graphs
* Downloadable **PDF reports** for record keeping

---

## 📂 Repository Structure

This repository currently contains **only the Flask backend application code** used in the MVP. Model training, dataset preparation, and hardware-side scripts were handled separately during development and are **not included** in this repository.

## 🚀 Getting Started

### Prerequisites

- Python 3.8+
- pip
- Virtual environment (recommended)

### Installation

```bash
pip install -r requirements.txt
````

### Running the Flask App

```bash
python app.py
```

The Flask server starts locally and exposes APIs for:

* Receiving image inputs
* Triggering ML inference (model loading assumed)
* Returning detection results and analytics

---

## 📊 Output

* Real-time detection results
* Bounding boxes around detected microplastics
* Quantitative summaries
* Exportable **PDF reports**

---

## 🔬 MVP Limitations

* ESP32-CAM resolution limits fine-grain particle differentiation
* Detection focuses on **presence**, not polymer type
* Fluorescent surrogate dye lacks spectral specificity

These limitations are addressed in the proposed post-MVP architecture.

---

## 🔮 Future Scope

Planned extensions include:

* Raspberry Pi–based edge deployment
* High-resolution USB microscope camera
* Fluorescence spectral analysis using photodiode array detectors
* Polymer type identification using **spectral phasor mapping**
* Expected polymer classification accuracy: **85–90%**

---


## 🤝 Contributing

This repository is shared for educational and research purposes. Contributions, optimizations, and extensions are welcome.

---


## ✨ Acknowledgement

This project represents a collaborative effort integrating IoT, machine learning, image processing, and environmental science to address a real-world problem.

*Even without reaching the SIH finals, the learning and system design experience remain invaluable.*
