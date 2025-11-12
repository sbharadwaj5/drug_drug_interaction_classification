# Enhancing Drug–Drug Interaction Prediction with Graph and Transformer Models

## 🧠 Overview
This project explores multimodal deep learning frameworks for predicting **Drug–Drug Interactions (DDIs)** using both **chemical structure** (SMILES) and **biological context** (target/enzyme interactions). By integrating **graph-based similarity** and **transformer-based embeddings**, we aim to improve the prediction of interaction types such as adverse effects, serum concentration changes, and metabolic alterations.

---

## 🔍 Problem Statement
Drug–drug interactions can modify therapeutic outcomes or cause adverse reactions. Given the large number of possible drug combinations, **computational DDI prediction** provides a scalable solution. This project demonstrates how **representation learning** and **multimodal integration** enhance DDI event classification accuracy.

---

## ⚙️ Methods

### Dataset
- **Source:** DrugBank v5.1.3  
- **Samples:** 57K+ interactions among 572 drugs  
- **Labels:** Adverse Effect, Serum Concentration Change, Metabolic Interaction  

### Feature Engineering
- One-hot encoding for **targets** and **enzymes**  
- **ChemBERTa (seyonec/ChemBERTa-zinc-base-v1)** transformer embeddings for SMILES  
- **Gaussian similarity matrices** to represent feature-space proximity  
- Graph construction using **NetworkX** for each modality  

### Models Implemented
- **MLP:** Concatenated multimodal embeddings  
- **BiRNN:** Bidirectional GRU-based sequence model  
- **GAT:** Graph Attention Network leveraging similarity graphs  

---

## 📊 Results

| Model | Accuracy | Precision | Recall | F1 Score |
|:------|:----------|:-----------|:--------|:----------|
| **MLP** | **0.9042** | 0.9042 | 0.9016 | 0.9013 |
| **BiRNN** | 0.65 | 0.62 | 0.60 | 0.61 |
| **GAT** | 0.4771 | 0.0085 | 0.0179 | 0.0115 |

✅ The **MLP model** achieved the best overall performance, showing that **feature-rich embeddings** and **robust preprocessing** can outperform complex models when data is limited.

---

## 💡 Key Insights
- Transformer-based SMILES embeddings yield more meaningful chemical representations.  
- Model complexity should match dataset scale to avoid underfitting.  
- Graph sparsity and class imbalance remain open challenges in biomedical ML.  

---

## 🔬 Future Work
- **Data augmentation** via generative VAEs for minority interaction types.  
- **Multi-view fusion** for unified molecular and biological representations.  
- Exploration of **foundation models** for drug representation learning.  

---

## 💻 Repository
Code and experiments are available at:  
👉 [https://github.com/sbharadwaj5/drug_drug_interaction_classification](https://github.com/sbharadwaj5/drug_drug_interaction_classification)

---


## 📚 References
1. Chithrananda et al. (2020). *ChemBERTa: Large-Scale Self-Supervised Pretraining for Molecular Property Prediction.*  
2. Deng et al. (2020). *A Multimodal Deep Learning Framework for Predicting Drug–Drug Interaction Events.*  
3. Wang et al. (2025). *BiRNN-DDI: A Drug–Drug Interaction Event Type Prediction Model Based on Bidirectional Recurrent Neural Networks and Graph2Seq Representation.*  

---

*Developed as part of a Machine Learning for Biomedicine project at Georgia Tech.*
