# EHR Transfer Learning for CRD Diagnosis

This project studies **Chronic Respiratory Disease (CRD)** diagnosis by combining  
**chest X-ray (CXR) features** and **Electronic Health Records (EHR)** using machine learning.

---

## Overview
- Transfer learning (DenseNet) for CXR feature extraction
- Multimodal learning: CXR + structured EHR
- Focus on **class imbalance handling** for rare diseases

---

## Data
- **MIMIC-IV**: EHR + ICD labels  
- **MIMIC-CXR**: chest X-ray images  
- **CheXpert**: pre-training for DenseNet  

⚠️ Data not publicly released (PhysioNet access required).

---

## Pipeline (Baseline – Instructor)
- Cohort selection & EDA  
- CXR feature extraction (18 features)
- EHR feature extraction (12 features)
- Disease labels from ICD codes (8 CRDs)

Notebooks:
- `EDA.ipynb`
- `cohortselection.ipynb`
- `cxrretrieval.ipynb`
- `finalisedcohortdata.ipynb`

---

## Data Augmentation (Student Work)

### Model 1 – SMOTE + XGBoost  
**Contributor:** Trần Thành Trọng  
- SMOTE on image features  
- XGBClassifier / XGBRegressor for EHR reconstruction  

### Model 2 – ROS + XGBClassifier  
**Contributor:** Bùi Đăng Khoa
- Random Over-Sampling on training set only  
- Evaluated with:
  - Image features only
  - Image + EHR features  

---

## Results (Key Findings)
- Image-only models suffer from severe class imbalance
- SMOTE combined with XGBClassifier/XGBRegressor helps rare diseases overcome near-zero Recall, while simultaneously optimizing the F1-score and enhancing disease detection capability.
- **ROS + XGBClassifier + EHR gives the best Precision–Recall trade-off**
- EHR features significantly improve detection of rare CRDs

Metrics: Accuracy, Precision, Recall, F1-score

---

## Repository Structure
```text
code/
├── EDA.ipynb
├── cohortselection.ipynb
├── cxrretrieval.ipynb
├── SMOTE+XGB.ipynb
├── Model_1.ipynb
├── Model_2.ipynb
└── finalisedcohortdata.ipynb

```
---

## Authors
- Trần Thành Trọng – SMOTE + XGBoost (Model 1)
- Bùi Đăng Khoa – ROS + XGBClassifier (Model 2)

Instructor: Nguyễn Tuấn Khôi, Ngô Hoàng Anh

---

## Reference
See `EHR_Transfer_Learning.pdf` for full details.
