# Fake-News-Detector

A misinformation detector that combines a text classifier (DistilBERT) with
evidence retrieval from trusted news sources, and explains each verdict in plain language.

## Project structure
```
Fake-News-Detector/
├── notebooks/        
├── backend/      
├── frontend/       
└── docs/
```

## Dataset
The LIAR dataset: 12.8k short political statements rated by PolitiFact on six levels
(pants-fire to true). Split into 10,240 train, 1,284 validation and 1,267 test statements.
For classification the labels are merged into two classes: pants-fire, false and
barely-true as misinformation; half-true, mostly-true and true as real.

## Progress

### Phase 1: Data exploration and TF-IDF baseline (done)
Notebook: `notebooks/fake-news-detector-phase1`

The earlier stages of any project are related the exploration of data one have. That's exactly what i had been doing in this stage. We set up a binary classification baseline on the LIAR dataset, but our TF-IDF model saturated at ~62% accuracy. A further analysis of the remaining 38% shows the model struggles with true statements that are emotional and misinformation that is deadpan and flat. Hyperparameter tuning makes little difference, so we are moving to BERT for actual semantic context and will integrate an external search mechanism for fact-checking.
