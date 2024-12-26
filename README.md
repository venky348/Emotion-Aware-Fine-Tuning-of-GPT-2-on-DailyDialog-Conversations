# Emotion-Aware Fine-Tuning of GPT-2 on DailyDialog Conversations

This project focuses on fine-tuning the GPT-2 language model on the DailyDialog dataset to improve its ability to generate contextually relevant and emotionally aligned responses for conversational text.

## Features
- **Dataset**: Utilizes the DailyDialog dataset containing 9,624 dialogues labeled with emotions such as `neutral`, `joy`, `sadness`, and `anger`.
- **Fine-Tuning**: Tailors the GPT-2 model to understand and respond to conversational prompts with improved coherence and relevance.
- **Pre-Training vs Fine-Tuning Analysis**: Highlights the improvement in response quality after fine-tuning the model on dialogue-specific data.
- **Emotion Detection**: Enhances the ability to generate text that aligns with the emotional context of the input.

## Dataset Description
- **Source**: [DailyDialog Dataset on Kaggle](https://www.kaggle.com/datasets/va6573/dailydialog)
- **File Structure**:
  - `daily_dialog_train_cleaned.csv`: Training set with dialogues and emotion labels.
  - `daily_dialog_val_cleaned.csv`: Validation set for intermediate evaluation.
  - `daily_dialog_test_cleaned.csv`: Test set for final evaluation.
- **Emotion Distribution**:
  - Neutral: 83%
  - Joy: 13%
  - Other emotions: 4%
- **Example Dialogues**:
  - Neutral: “Where else have not I been to yet?”
  - Joy: “Um well actually we had a fantastic time last night, he was amazing.”

## Methodology
### 1. Preprocessing
- **Text Cleaning**: Handles missing values in dialogue text.
- **Label Encoding**: Converts emotion labels into numerical values for training.

### 2. Tokenization
- **Tokenizer**: Uses the GPT-2 tokenizer with padding and truncation.
- **Max Length**: Limits sequences to 128 tokens for consistency.

### 3. Fine-Tuning
- **Model**: GPT-2 pretrained on general language tasks, fine-tuned on DailyDialog.
- **Training Details**:
  - Learning Rate: 2e-5
  - Epochs: 3
  - Batch Size: 16
  - Optimizer: AdamW
  - Loss Function: Cross-Entropy
- **Implementation**: Utilizes Hugging Face's `Trainer` API for streamlined fine-tuning.

### 4. Evaluation
- **Metrics**:
  - Training Loss: 0.374
  - Evaluation Loss: 0.336
  - Evaluation Accuracy: 95.89 samples/second
- **Pre-Fine-Tuning Observations**:
  - Responses were disjointed and lacked contextual relevance.
- **Post-Fine-Tuning Observations**:
  - Responses aligned with input prompts, e.g.:
    - Input: “Congratulations” → Output: “Congratulations to you sir.”
    - Input: “Good afternoon madam” → Output: “Good afternoon madam, I am sorry for the delay.”

## Results and Analysis
- Fine-tuning significantly improved the quality of responses:
  - Generated text became more coherent, polite, and contextually relevant.
  - Emotionally aligned text responses were observed in conversational contexts.
- **Comparison**:
  - Pre-Fine-Tuning: Generated random and often irrelevant text.
  - Post-Fine-Tuning: Generated text became appropriate and conversationally engaging.

## Conclusion
This project demonstrates the effectiveness of fine-tuning GPT-2 on dialogue datasets like DailyDialog. The model learned to generate context-aware and emotionally relevant responses, enhancing its suitability for conversational AI applications.


