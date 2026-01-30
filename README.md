# Falcon 9 Landing Success Prediction 🚀

## Overview
This project analyzes historical SpaceX Falcon 9 launch data to predict the probability of successful first-stage landings. Using public SpaceX API data, I built a complete end-to-end machine learning pipeline covering data collection, cleaning, exploratory analysis, feature engineering, and model evaluation.

The goal is to understand which factors most strongly influence landing success and compare baseline and ensemble models under class imbalance.

---

## Data Source
- **SpaceX REST API (v4)**
  - `/v4/launches/past`
  - `/v4/rockets/{id}`

Only **Falcon 9 launches** were retained for analysis.

---

## Project Structure

├── 01_API_Data_Collection.ipynb
├── 02_Data_Wrangling.ipynb
├── data/
│ ├── falcon9_step1_api_data.csv
│ ├── falcon9_step2_cleaned.csv


---

## Features Used
- `core_flight` — Number of flights for the booster
- `core_reused` — Whether the booster was reused
- `landing_type` — ASDS, RTLS, Ocean
- `landpad` — Landing pad identifier (one-hot encoded)

**Target variable**
- `Class` → `1 = successful landing`, `0 = failed landing`

---

## Models Trained
- **Logistic Regression** (baseline)
- **Random Forest Classifier** (balanced class weights)

---

## Results Summary
| Model | Accuracy | Strengths | Limitations |
|------|----------|-----------|-------------|
| Logistic Regression | ~94% | High recall for successful landings | Misses most failures |
| Random Forest | ~77% | Detects failed landings | Lower overall accuracy |

**Key Insight:**  
Random Forest provides more balanced performance and is better suited for risk-sensitive decision-making despite lower accuracy.

---

## Key Findings
- Reused boosters have higher landing success rates
- Success rate increases with booster flight number
- RTLS landings outperform ocean landings
- Landing success depends on multiple interacting factors

---

## Tools & Libraries
- Python
- Pandas, NumPy
- Scikit-learn
- Matplotlib

---

## Author
**Shaida**  
IBM Data Science Professional Certificate
