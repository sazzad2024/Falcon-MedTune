# Falcon-MD: Fine-Tuned Medical LLM

This repository contains a specialized version of the **Falcon3-7B-Base** model, fine-tuned specifically for generating medical diagnoses and action plans from patient symptom descriptions.

## 🌟 Key Features
- **Project Goal**: Transform a general-purpose LLM into a medical-aware assistant.
- **Included Weights**: This repo includes the pre-trained **LoRA Adapters** in the `fine_tuned_parameter/` directory.
- **Eficiency**: Uses 4-bit quantization (QLoRA) for high performance with low memory usage.

## 🧬 Model Details
- **Base Model**: [tiiuae/Falcon3-7B-Base](https://huggingface.co/tiiuae/Falcon3-7B-Base)
- **Fine-Tuning Method**: PEFT/LoRA (Low-Rank Adaptation)
- **Dataset**: BI55/MedText (Clinical symptoms & diagnoses)
- **Parameters**: 42MB Adapter (included in this repo)

## 📁 Project Structure
- `Falcon_Finetuning_Project.ipynb`: The primary interactive notebook for running inference and further training.
- `fine_tuned_parameter/`: 
  - `adapter_model.safetensors`: The core trained weights.
  - `adapter_config.json`: Configuration for the PEFT model.
  - `template_falcon.jinja`: Template for prompting.
- `requirements.txt`: Necessary Python libraries.

## 🚀 Quick Start (Inference)
To use the included parameters:
1. Clone the repo: `git clone <your-repo-url>`
2. Install requirements: `pip install -r requirements.txt`
3. Load the model in the notebook using:
   ```python
   from peft import PeftModel
   model = PeftModel.from_pretrained(base_model, "./fine_tuned_parameter")
   ```

## 🛠️ How to Fine-Tune Further
Instructions for additional training are provided inside the `Falcon_Finetuning_Project.ipynb` notebook. The project is pre-configured to save new checkpoints to a local directory ignored by Git.
