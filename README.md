# Dementia Risk Profiling from Clinical Narratives Using LLMs

This project addresses the challenge of identifying dementia risk within unstructured clinical narratives by implementing a multimodal machine learning pipeline. By bridging the gap between "locked" narrative data and structured clinical decision support, this study evaluates a scalable framework for identifying at-risk populations within Electronic Health Records (EHR).


The specific objective of this project is to perform a binary classification task to distinguish between Control and Dementia cohorts using patient summaries from the PMC-Patients dataset. The pipeline is designed to:

1. Extract clinical markers and risk factors from unstructured text using a Large Language Model (LLM) and Regex patterns.

2. Represent patient summaries using high-dimensional dense text embeddings.

3. Classify and Stratify patients through an ablation study using an XGBoost model, evaluating the marginal benefit of explicit clinical features versus latent semantic representations.

## Results Summary
The results of the ablation are summarized below.

| Data                                              |  AUC  |   F1  | Recall | Accuracy |
|---------------------------------------------------|:-----:|:-----:|:------:|:--------:|
| Demographics only                                 | 0.551 | 0.549 |  0.629 |   0.543  |
| Demographics + Text embeddings                    | 0.880 | 0.794 |  0.839 |   0.807  |
| Demographics + Text Embeddings + LLM   features   | 0.875 | 0.797 |  0.823 |   0.814  |
| Demographics + Text Embeddings + Regex   features | 0.894 | 0.769 |  0.806 |   0.786  |
| Demographics + LLM features                       | 0.659 | 0.619 |  0.774 |   0.579  |
| Demographics + regex features                     | 0.640 | 0.596 |  0.677 |   0.593  |

The results demonstrate a clear hierarchy in feature efficacy for dementia prediction. While demographics alone
provided a negligible predictive signal, the integration of dense text embeddings elevated the predictive performance.
This suggests that high-dimensional semantic representations are uniquely capable of capturing the subtle, non-linear
linguistic markers of cognitive decline that traditional structured data misses.

## Reproducing results
<!-- 
### Requirements
The following packages were used in the experiments.
```

```
They can also be found in the requirements.txt -->

### Files
The experiments were performed in notebooks, the notebooks can be found in the `notebooks/` folder.

