# Natural Language Queries in Egocentric Videos

This repository contains a Machine Learning and Deep Learning project focused on **Natural Language Queries (NLQ) in egocentric videos**.

The project addresses the Ego4D NLQ benchmark, where the goal is to localize the temporal segment in a first-person video that answers a natural language query.

---

## 📌 Project Overview

Egocentric vision captures videos from a first-person point of view, usually using head-mounted or wearable cameras.  
This perspective provides a unique way to study human interactions, daily activities, and visual understanding from the user's viewpoint.

In this project, we explore **Natural Language Queries (NLQs)** in egocentric videos.  
Given a video clip and a free-form textual query, the model must predict the start and end timestamps of the video segment where the answer can be found.

Example task:

> Query: "Where did I put the scissors?"  
> Output: The temporal segment in the video where the answer is visible.

---

## 🎯 Objective

The main objectives of this project are:

- Study the Ego4D Natural Language Queries benchmark.
- Train and evaluate baseline models for temporal video-language localization.
- Compare different visual feature representations.
- Evaluate the impact of model architecture on NLQ performance.
- Implement an extension using a Large Language Model for NLQ generation.

---

## 🧠 Dataset

The project is based on the **Ego4D dataset**, a large-scale egocentric video dataset containing daily-life activities captured from a first-person perspective.

The focus is on the **Natural Language Queries (NLQ)** benchmark, where each sample includes:

- A video clip
- A natural language query
- Ground-truth start and end timestamps
- Query templates related to objects, places, people, and activities

---

## 🛠️ Methodology

The project follows a video-language learning pipeline:

1. **Dataset Understanding**
   - Studied the Ego4D NLQ benchmark
   - Analyzed the role of egocentric videos in video understanding
   - Explored query templates and temporal annotations

2. **Feature Extraction**
   - Used pre-extracted video features from:
     - **Omnivore**
     - **EgoVLP**

3. **Model Training**
   - Trained and evaluated:
     - **VSLBase**
     - **VSLNet**

4. **Model Comparison**
   - Compared the effect of different feature sets
   - Compared shared and non-shared encoder configurations
   - Evaluated model performance using temporal localization metrics

5. **Extension**
   - Implemented a Natural Language Query generation system using **Gemma 2B**
   - Fine-tuned the model to generate NLQ-style questions from descriptive sentences

---

## 🧩 Models and Features

### Models

| Model | Description |
|---|---|
| VSLBase | Baseline video-language model for temporal localization |
| VSLNet | Extended model with a Query Guided Highlighter module |
| Gemma 2B | LLM used for generating natural language queries as an extension |

### Feature Representations

| Feature | Description |
|---|---|
| Omnivore | General-purpose visual feature extractor |
| EgoVLP | Egocentric video-language pre-trained feature extractor |

---

## 📊 Evaluation Metrics

The models were evaluated using:

| Metric | Description |
|---|---|
| Rank@k | Measures whether the correct segment is found among the top-k predictions |
| tIoU | Temporal Intersection over Union between predicted and ground-truth segments |
| mIoU | Mean temporal IoU across predictions |

---

## 🏆 Results

The best-performing configuration was:

| Configuration | Overall mIoU |
|---|---:|
| EgoVLP + VSLNet Shared Encoder | **7.63** |
| EgoVLP + VSLNet Non-Shared Encoder | 7.34 |
| EgoVLP + VSLBase | 6.67 |
| Omnivore + VSLNet Shared Encoder | 4.76 |
| Omnivore + VSLNet Non-Shared Encoder | 4.77 |
| Omnivore + VSLBase | 4.52 |

The results show that **EgoVLP features combined with VSLNet using a shared encoder** achieved the best overall performance.

---

## 📈 Key Insights

- EgoVLP features performed better than Omnivore features for the NLQ task.
- VSLNet improved temporal localization compared to VSLBase.
- Shared encoder configurations provided better video-text alignment in the best-performing setup.
- Feature selection and architecture design strongly affect performance in video-language localization tasks.
- LLMs can be used to generate additional natural language queries and support dataset augmentation.

---

## 💻 Technologies Used

- Python
- Machine Learning
- Deep Learning
- Computer Vision
- Natural Language Processing
- Egocentric Vision
- Video-Language Modeling
- VSLNet
- Ego4D
- EgoVLP
- Omnivore
- Gemma 2B
- JAX
- LoRA Fine-Tuning

---

## 📄 Report

The full project report is included in this repository.

**Title:**  
Natural Language Queries in Egocentric Videos

**Course:**  
Machine Learning and Deep Learning

**Institution:**  
Politecnico di Torino

**Authors:**  
- Yasaman Noshirvanbaboli  
- Seyed Mohammad Sheikh Ahmadi  
- Amirhossein Lotf Ranaei

---

## ⚠️ Note

This project was developed as part of a university Machine Learning and Deep Learning course.  
The repository is intended for educational, research, and portfolio purposes.

---

## 📬 Contact

**Yasaman Noshirvanbaboli**  
GitHub: [YasiNoshirvan](https://github.com/YasiNoshirvan)
