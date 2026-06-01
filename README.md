# Natural Language Processing Assignment 2

This repository contains the implementation report and code for Natural Language Processing Assignment 2.

## Project Overview

This assignment focuses on sequence modeling and neural machine translation. It begins with basic language modeling using a vanilla RNN, then moves to manually implemented LSTM and GRU models, Seq2Seq translation, attention-based translation, and final NMT model comparison.

## Main Topics Covered

- Vanilla RNN language modeling
- Manual LSTM implementation
- Manual GRU implementation
- Next-word prediction
- Gate activation analysis
- Seq2Seq encoder-decoder translation
- Bahdanau attention
- Luong attention
- Scaled dot-product attention
- Neural machine translation model comparison
- BLEU, BERTScore, METEOR, perplexity, and accuracy evaluation

## Part 1: Vanilla RNN Sequence Modeling

The WikiText-2-v1 corpus was used for next-word language modeling.

### Dataset Statistics

- Vocabulary Size: 25,000
- Total Tokens: 2,007,146
- Training Sentences: 17,556
- Validation Sentences: 1,841
- Test Sentences: 2,183

### RNN Results

| Metric | Value |
|---|---:|
| Final Validation Loss | 5.46 |
| Final Validation Perplexity | 236.12 |
| Test Loss | 5.40 |
| Test Perplexity | 221.53 |
| Training Time | 441.74 sec |

## Part 2: Manual LSTM and GRU Models

Custom LSTM and GRU models were implemented using tensor operations and compared against the vanilla RNN baseline.

| Model | Validation Perplexity | Test Perplexity | Training Time |
|---|---:|---:|---:|
| RNN | 236.12 | 221.53 | 441.74 sec |
| LSTM | 201.12 | 188.04 | 776.89 sec |
| GRU | 199.57 | 186.97 | 758.39 sec |

The GRU achieved the best validation and test perplexity among the sequence models.

## Part 3: Basic Seq2Seq Translation

A basic encoder-decoder Seq2Seq model was implemented for English-to-German translation using the Multi30k dataset.

### Results

- Train pairs: 29,000
- Validation pairs: 1,000
- Test pairs: 1,000
- BLEU Score: 21.34
- Token Accuracy: 0.31

## Part 4: Attention Mechanisms

Three attention mechanisms were implemented and compared:

1. Bahdanau Attention
2. Luong Attention
3. Scaled Dot-Product Attention

| Model | BLEU Score | Validation Perplexity | Training Time |
|---|---:|---:|---:|
| Seq2Seq without Attention | 18.45 | 264.18 | 10.06 min |
| Seq2Seq + Bahdanau Attention | 22.45 | 193.42 | 15.47 min |
| Seq2Seq + Luong Attention | 19.26 | 207.79 | 14.28 min |
| Seq2Seq + Scaled Dot Attention | 22.02 | 222.12 | 14.05 min |

Bahdanau attention achieved the best BLEU score and lowest validation perplexity in this section.

## Part 5: Final Neural Machine Translation Comparison

The final experiment compared five models using a larger 300K WMT14 configuration.

| Model | BLEU | BERTScore F1 | METEOR | Training Time |
|---|---:|---:|---:|---:|
| Seq2Seq RNN | 0.18 | 0.5785 | 0.0891 | 76.65 min |
| Seq2Seq LSTM | 0.60 | 0.5988 | 0.1144 | 81.36 min |
| Seq2Seq GRU | 0.82 | 0.6075 | 0.1271 | 79.97 min |
| Seq2Seq LSTM + Bahdanau Attention | 1.79 | 0.6438 | 0.1769 | 131.79 min |
| Seq2Seq GRU + Bahdanau Attention | 1.68 | 0.6453 | 0.1723 | 129.24 min |

## Key Finding

Attention-based models performed better than non-attention models. The Seq2Seq LSTM + Bahdanau Attention model achieved the best BLEU, METEOR, and sentence accuracy, while the Seq2Seq GRU + Bahdanau Attention model achieved the best BERTScore F1.

## Repository Structure

```text
.
├── README.md
├── NLP_Assignment2.pdf
├── notebooks/
│   └── nlp_assignment_2.ipynb
├── results/
│   ├── model_comparison.csv
│   ├── translation_examples.csv
│   └── error_analysis.csv
├── images/
│   ├── loss_curves.png
│   └── attention_heatmaps.png
└── requirements.txt
