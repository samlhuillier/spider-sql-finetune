# Fine-tune GPT 3.5 and CodeLlama 34B on the spider-sql-finetune dataset
This code uses a modified and slightly smaller version of the spider dataset. Using SQL create commands as context instead of the weird other schema spider uses.

### Code Llama fine-tune:
- Inside the llama directory that is the notebook that will fine-tune Code Llama 34B on the  dataset
- It uses Huggingface transformers to pull the model and dataset from the huggingface hub

This is a Lora fine-tune quantising the model to 8 bits. Therefore, you'll need just over 40GB of GPU memory. I used an A40. But you could use an 80GB A100 or A6000 too.

### OpenAI fine-tune:
Inside the openai folder there are two notebooks and the two dataset files (formatted for OpenAI):
- openai_train.ipynb loads the datasets and sends them to OpenAI to fine-tune GPT 3.5
- openai_dataset_analytics.ipynb reads an OpenAI dataset jsonl file and works out whether there are any errors in the file and the total number of tokens in the dataset.

My full post on the results of this is [here](https://ragntune.com/blog/gpt3.5-vs-llama2-finetuning)!
