# DATA 266 - Lab 2 - Team 2

Due to file size issue in github. I've uploaded stable diffusion weights (Part 2) in google drive. please find those in the below link.
https://drive.google.com/drive/folders/1c81-djby0-gZxd0g1WupHQ9Kl9NM47mv?usp=sharing

This repository contains the code, documentation, and outputs for Lab 2 of the DATA 266 course, completed by Team 2. The lab involved implementing three tasks:

1.  A MultiModal Retrieval-Augmented Generation (RAG) System
2.  Fine-Tuning Stable Diffusion using Low-Rank Adaptation (LoRA)
3.  An Agentic AI Travel Assistant

---

## Part 1: MultiModal Retrieval-Augmented Generation (RAG) System

* **Objective:** Developed a system to extract text and images (figures/tables) from a PDF (`document.pdf`) related to economics. The system retrieves relevant text/image pairs based on economic queries and uses a generative model (Gemini 1.5 Pro) to answer the questions, referencing the most relevant image.
* **Methodology:** Used PyMuPDF for data extraction, Sentence Transformers (BAAI/bge-large-en-v1.5) for text embeddings, FAISS for vector similarity search, and Google Generative AI for response generation. Response quality was evaluated using BERTScore.
* **Outcome:** Successfully answered 11 economic questions, producing a `submission.csv` file containing the question ID, generated text answer, and the ID of the most relevant image (or 0 if none). High semantic similarity confirmed by BERTScore (F1: 0.9120 on a sample).

---

## Part 2: Fine-Tuning Stable Diffusion for Image Generation

* **Objective:** Customized the pre-trained Stable Diffusion v1.5 model (`runwayml/stable-diffusion-v1-5`) to generate images reflecting a specific visual style from a custom dataset, using parameter-efficient fine-tuning.
* **Methodology:** Employed Low-Rank Adaptation (LoRA) via the `peft` library to fine-tune the UNet component of the Stable Diffusion model on a Kaggle dataset. Trained for 3 epochs using AdamW optimizer. Evaluated generated images using Inception Score (IS) and CLIP Similarity Score.
* **Outcome:** A LoRA-adapted Stable Diffusion model capable of generating images aligned with the fine-tuning dataset's style and input text prompts.

---

## Part 3: Developing an Agentic AI Travel Assistant

* **Objective:** Built an AI assistant composed of multiple agents (Flight, Weather, Hotel, Itinerary Planner) to automatically generate detailed travel itineraries by fetching data from external APIs.
* **Methodology:** Implemented in Python using `requests` for API calls and `datetime` for date handling. Agents fetched flight options, weather forecasts, and hotel availability based on user-specified origin, destination, and travel date.
* **Outcome:** A system that successfully generates formatted travel itineraries for various test scenarios (e.g., San Francisco to New York, Los Angeles to Miami, Chicago to London), including multiple flight options, destination weather forecasts, and available hotel suggestions with prices and ratings.

---

