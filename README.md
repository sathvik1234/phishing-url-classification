# Phishing URL Classification Using Machine Learning and Deep Learning

## Project Team

**Course:** IAI600 – Group Project  
**University:** University West

This project was collaboratively developed by the following four team members:

| No. | Name | GitHub Profile |
|---|---|---|
| 1 | Satvik Undi | [@sathvik1234](https://github.com/sathvik1234) |
| 2 | Manoj Kumar Shanmugam | [@manojkumarshanmugam008](https://github.com/manojkumarshanmugam008) |
| 3 | Vighnesh Samitha Nair Sureshkumar | [@Vikky0704](https://github.com/Vikky0704) |
| 4 | Pavan Kumar Souda | [@pavansouda235](https://github.com/pavansouda235) |

## Project Overview

This project focuses on identifying phishing and legitimate URLs using Machine Learning and Deep Learning techniques.

The objective is to develop and compare two classification approaches:

1. **Hybrid Support Vector Machine (SVM):** Combines character-level TF-IDF features with handcrafted URL features.
2. **Character-Level Convolutional Neural Network (CNN):** Uses character-level URL representation to automatically learn patterns associated with phishing and legitimate URLs.

The project explores URL feature extraction, model training, hyperparameter tuning and performance evaluation.

## Dataset

The project uses the prepared dataset:

`phishing_url_dataset_unique.csv`

The dataset contains URL samples with the following target labels:

- `0` – Legitimate URL
- `1` – Malicious URL

**Dataset summary:**
- Total samples: 48,812
- Legitimate URLs: 24,406
- Malicious URLs: 24,406

## Feature Engineering

Handcrafted URL features were extracted to identify potentially suspicious URL characteristics.

Features include:

- URL length
- Number of dots
- Number of digits
- Number of hyphens and underscores
- Number of slashes
- Number of special characters
- HTTPS presence
- IP address presence
- Number of subdomains
- URL entropy

## Models Implemented

### 1. Hybrid Support Vector Machine (SVM)

The hybrid SVM combines two types of features:

- Character-level TF-IDF using character n-grams
- Handcrafted URL features

**Methods used:**
- Feature extraction using TF-IDF
- Feature scaling
- Linear Support Vector Classifier
- Stratified 5-fold cross-validation
- GridSearchCV for hyperparameter tuning

### 2. Character-Level Convolutional Neural Network (CNN)

A deep learning model was developed to classify URLs based on their character sequences.

**Architecture and techniques:**
- Character-level text vectorization
- Embedding layer
- 1D Convolutional layer
- Global Max Pooling
- Dropout regularization
- Dense layers
- Early stopping during training

## Model Performance

The models achieved the following results on the test dataset:

| Evaluation Metric | Hybrid SVM | Character CNN |
|---|---:|---:|
| Accuracy | 99.97% | 99.97% |
| Precision | 100% | 100% |
| Recall | 99.94% | 99.94% |
| F1-score | 99.97% | 99.97% |
| False Negatives | 3 | 3 |
| False Positives | 0 | 0 |

Both models achieved strong classification performance on the selected test split.

## Technologies Used

- Python 3.13
- NumPy
- Pandas
- Scikit-learn
- TensorFlow / Keras
- SciPy
- Matplotlib
- Joblib
- Jupyter Notebook

## Project Structure

```text
phishing-url-classification/
│
├── models/
│   ├── hybrid_svm_model.joblib
│   ├── phishing_url_cnn.keras
│   └── phishing_url_vectorizer.joblib
│
├── phishing_url_project.ipynb
├── phishing_url_dataset_unique.csv
├── requirements.txt
├── README.md
└── .gitignore
```


## Installation and Setup

### 1. Clone the repository

```bash
git clone https://github.com/sathvik1234/phishing-url-classification.git
```

### 2. Navigate to the project folder

```bash
cd phishing-url-classification
```

### 3. Create a virtual environment (optional)

```bash
python -m venv .venv
```

Activate it on Windows PowerShell:

```powershell
.venv\Scripts\Activate.ps1
```

### 4. Install dependencies

```bash
pip install -r requirements.txt
```

### 5. Run the project

Open `phishing_url_project.ipynb` using Visual Studio Code or Jupyter Notebook and execute the notebook cells in sequence.

## Limitations and Future Improvements

The dataset has a strong association between its data sources and target labels. In particular, Tranco samples are legitimate, while URLhaus and OpenPhish samples are malicious in this dataset.

Therefore, the high test scores from a random train/test split should not be interpreted as proof of real-world generalization.

Future improvements could include:

- Testing on independent data sources.
- Evaluating performance on previously unseen domains.
- Collecting more diverse phishing and legitimate URLs.
- Testing model performance on newly emerging phishing URLs.
- Exploring additional machine learning and deep learning architectures.

## Project Objective

The main objective is to explore and compare traditional machine learning and deep learning approaches for detecting potentially malicious URLs.

**Project:** IAI600 – Group Project  
**University:** University West