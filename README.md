# Pneumonia-Detection-through-Chest-X-rays-using-Deep-Learning

This project leverages **Deep Learning** technologies to detect pneumonia from chest X-ray images. Using models like **CNN, ResNet50, InceptionV3, CheXNet**, and **ensemble learning**, the system provides a reliable diagnostic tool for healthcare professionals. With **Explainable AI (XAI)** methods such as **SHAP** and **LIME**, the project ensures interpretability and transparency in predictions, making it highly suitable for clinical applications.

---

## Table of Contents
- [Introduction](#introduction)
- [Dataset](#dataset)
- [Methodology](#methodology)
- [Deep Learning Models](#deep-learning-models)
- [Explainable AI](#explainable-ai)
- [Results and Performance](#results-and-performance)
- [Applications](#applications)
- [Setup and Installation](#setup-and-installation)
- [Usage](#usage)
- [Future Work](#future-work)

---

## Introduction
Pneumonia, a leading cause of mortality worldwide, particularly among children under five, demands timely and accurate diagnosis. Chest X-rays play a vital role, but challenges like overlapping features and inconsistent image quality complicate detection. This project automates pneumonia detection through **deep learning** techniques, aiding radiologists in making faster, more accurate decisions.

---

## Dataset
The dataset is sourced from the **Guangzhou Women and Children's Medical Center** and comprises **5,863 pediatric chest X-ray images** categorized into:
- **Normal**
- **Pneumonia**

### Dataset Distribution:
| Set           | Normal | Pneumonia |
|---------------|--------|-----------|
| Training Set  | 1,341  | 3,875     |
| Validation Set| 8      | 8         |
| Test Set      | 234    | 390       |

To address class imbalance, data redistribution and weight adjustments were applied during preprocessing.

---

## Methodology
The implementation involves:
1. **Data Preprocessing:**
   - Resizing images to 256x256 pixels.
   - Converting grayscale images to RGB for compatibility with pre-trained models.
   - Normalizing pixel intensity to [-1, 1].

2. **Deep Learning Models:** 
   - Implemented architectures like **CNN**, **ResNet50**, **CheXNet**, and **InceptionV3**.  
   - Ensemble methods were employed for robustness.

3. **Explainable AI:** 
   - Used **SHAP** and **LIME** for interpretability.

4. **Evaluation Metrics:** 
   - Accuracy, Precision, Recall, F1-Score, and AUC-ROC were used to evaluate performance.

---

## Deep Learning Models
### 1. **Convolutional Neural Networks (CNN):**
The baseline model, featuring three convolutional layers, achieved high accuracy for spatial feature extraction.

### 2. **ResNet50:**
Fine-tuned ResNet50 excelled with **residual connections**, achieving a robust accuracy of 97%.

### 3. **CheXNet:**
Based on DenseNet-121, this model achieved an AUC of 1.00, ensuring accurate classification.

### 4. **InceptionV3:**
The modular architecture captured multi-scale features, achieving an AUC of 0.9945.

### 5. **Ensemble Models:**
Combined predictions from **CNN** and **ResNet50** using weighted voting, improving robustness and achieving an AUC of 0.988.

---

## Explainable AI
Transparency is essential in medical AI. This project uses:
- **SHAP (SHapley Additive exPlanations):** Highlights image regions influencing the model’s decision (red for pneumonia, blue for normal).
- **LIME (Local Interpretable Model-agnostic Explanations):** Highlights critical regions responsible for predictions using interpretable superpixels.

These tools provide interpretability and build trust in AI systems.

---

## Results and Performance
| Model        | Accuracy | Precision (Pneumonia) | Recall (Pneumonia) | F1-Score (Pneumonia) | AUC   |
|--------------|----------|-----------------------|--------------------|----------------------|-------|
| CNN          | 94%      | 0.98                  | 0.98               | 0.98                 | 0.93  |
| ResNet50     | 97%      | 0.97                  | 0.99               | 0.98                 | 0.991 |
| CheXNet      | 97%      | 0.99                  | 0.97               | 0.98                 | 1.00  |
| InceptionV3  | 97%      | 0.97                  | 0.98               | 0.98                 | 0.994 |
| Ensemble     | 97%      | 0.98                  | 0.98               | 0.98                 | 0.988 |

---

## Applications
1. **Clinical Decision Support:**
   - Acts as a "second opinion" for radiologists.  
   - Highlights suspicious regions for quicker diagnosis.

2. **Medical Training:**
   - Assists new radiologists in identifying critical areas in X-rays.

3. **Emergency Diagnostics:**
   - Facilitates triage in resource-constrained or pandemic scenarios.

---

## Setup and Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/pneumonia-detection.git
