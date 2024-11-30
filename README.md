# **COS801 Project: Style Change Detection in Multi-Authored Documents**

This repository contains the implementation, analysis, and results for the **Style Change Detection** project, developed as part of the COS801 course. The project leverages the **PAN CLEF 2023 dataset** to evaluate the performance of two primary approaches:
1. **Transformer-Based Models**: Lightweight implementations (Small BERT, ALBERT, and Small Electra).
2. **Hybrid BiLSTM Models**: Architectures combining neural embeddings and traditional features with attention mechanisms.

The goal of this project is to balance computational efficiency and accuracy in detecting stylistic transitions in multi-authored documents, with real-world applications such as plagiarism detection, collaborative writing, and forensic analysis.

---

## **Table of Contents**
- [Project Overview](#project-overview)
- [Features](#features)
- [Repository Structure](#repository-structure)
- [Getting Started](#getting-started)
- [Usage](#usage)
- [Results](#results)
- [Future Work](#future-work)
- [Contributing](#contributing)
- [License](#license)

---

## **Project Overview**
Style change detection is a critical task in natural language processing (NLP), aiming to identify transitions in authorship within a single document. This project explores:
- The performance of **lightweight transformer-based models** for computational efficiency.
- The integration of **traditional features** with neural models in **hybrid BiLSTM-based architectures** for nuanced stylistic detection.

The evaluation focuses on **three datasets** (Easy, Medium, and Hard) from the PAN CLEF 2023 challenge, designed to test varying levels of complexity in detecting stylistic transitions.

---

## **Features**
1. **Dataset Preprocessing**:
   - Cleaning, tokenization, and paragraph-level segmentation.
   - Label assignment for stylistic transitions.
   
2. **Transformer-Based Models**:
   - Lightweight models: Small BERT, ALBERT, Small Electra.
   - Implementation of difference vector computation for style detection.

3. **Hybrid BiLSTM Models**:
   - Basic BiLSTM.
   - BiLSTM with attention mechanisms.
   - Enhanced BiLSTM with traditional features (e.g., cosine similarity, punctuation density).

4. **Evaluation**:
   - Performance comparison using precision, recall, and F1 scores.
   - Visualization of results with bar graphs and performance heatmaps.

---

## **Getting Started**

### Prerequisites
- Python 3.8 or higher
- Recommended: Create a virtual environment using `venv` or `conda`.

### Installation
1. Clone the repository:
   ```bash
   git clone https://github.com/reolingovender/cos801_project.git
   cd cos801_project
   ```
2. Install required dependencies:
   ```bash
   pip install -r requirements.txt
   ```

3. Download and place the **PAN CLEF 2023 dataset** in the `data/` folder.

---

## **Usage**

### Data Preprocessing
Run the preprocessing script to prepare the dataset:
```bash
python preprocess.py --input data/raw --output data/processed
```

### Train Models
To train a transformer-based model:
```bash
python train_transformer.py --model small_bert --data data/processed
```

To train a hybrid BiLSTM model:
```bash
python train_bilstm.py --model enhanced --data data/processed
```

### Evaluate Models
Evaluate a trained model and generate results:
```bash
python evaluate.py --model small_bert --task hard
```

---

## **Results**
- **Transformer-Based Models**:
  - Lightweight models achieved moderate performance (F1 scores: 0.50–0.53).
  - Efficiency optimized but struggled with nuanced tasks (e.g., Dataset 3).
  
- **Hybrid BiLSTM Models**:
  - Achieved higher accuracy (F1 scores up to 0.8684) on simpler tasks.
  - Performance dropped in harder tasks due to subtle stylistic shifts.

---

## **Future Work**
- Incorporate **hierarchical transformers** to address token truncation issues.
- Expand analysis to **multilingual datasets** for broader applicability.
- Optimize hybrid models for **scalability** and reduced computational overhead.

---

## **Contributing**
Contributions are welcome! Please fork the repository, create a feature branch, and submit a pull request. For major changes, open an issue to discuss your proposed changes.

---

## **License**
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

---

This `README.md` provides a clear and organized overview of the project, making it easy for collaborators and users to understand and work with your repository.
