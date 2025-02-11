# Text-Summarizer-Project
In this project, we implemented the **PEGASUS** model to extract semantic features for generating **high-quality abstractive summaries**. **PEGASUS** is specifically designed for text summarization through its innovative pre-training technique known as _"gap-sentences generation"_.

## Implementation Details
 In this approach, the most informative sentences of a document are masked, and the model is trained to predict these sentences based on the surrounding context. This pre-training strategy is directly aligned with the requirements of summarization tasks, enabling **PEGASUS** to generate **concise** and **contextually relevant** summaries.

### Key Features of the Implementation
- **Zero-shot Efficiency:** Our implementation of **PEGASUS** demonstrated its superiority over other models, particularly in **zero-shot** settings where the model efficiently produces coherent summaries without the need for task-specific fine-tuning.
- **Flexibility and Adaptability:** This makes **PEGASUS** highly flexible and adaptable to various domains and languages, while also being efficient due to its lower training data requirements.
- **Consistency Across Text Lengths:** Our results showed that the model maintains consistent performance across texts of varying lengths, highlighting its potential utility in real-world applications where document lengths can vary significantly.

## Project Overview
This repository contains code, it's output and analysis for Natural Language Processing (NLP).  
🔹 **Main Implementation:** [NLP.ipynb](NLP.ipynb)  
🔹 Includes data preprocessing, model training, and evaluation.

### Hugging Face Components Used in This Project

| **Component**       | **Hugging Face Feature Used**                          |
|---------------------|--------------------------------------------------------|
| **Model Used**      | `google/pegasus-cnn_dailymail`                         |
| **Model Loading**   | `AutoModelForSeq2SeqLM.from_pretrained()`              |
| **Tokenizer**       | `AutoTokenizer.from_pretrained()`                      |
| **Dataset Used**    | `samsum` dataset                                       |
| **Dataset Handling** | `load_dataset("samsum")`, `load_from_disk()`          |
| **Preprocessing**   | Tokenization using `tokenizer()`                       |
| **Training**        | `Trainer` API with `TrainingArguments`                 |
| **Trainer API**     | `Trainer(model, args, train_dataset, eval_dataset)`    |
| **Evaluation**      | `load_metric('rouge')` for ROUGE scores                |
| **Text Generation** | `pipeline("summarization")`                            |  

## Practical Applications
The ability of **PEGASUS** to generate **high-quality summaries** makes it a valuable tool for applications in areas such as:

- **News Aggregation**
- **Content Creation**
- **Legal and Medical Document Summarization**
