 README: AI Video Generation & Prompt Pipeline (Langflow)
🧠 Overview
This Langflow workflow is designed to generate cinematic prompts for AI video generation using Google Veo and structured LLM orchestration. The workflow is split into two key sections:

📥 Preprocessing Section (Bottom) – Processes .docx input and builds a FAISS vector store.

🎬 Prompt Generation Section (Top) – Uses context + templates to produce cinematic prompts.

🛠️ Prerequisites
✅ Langflow Installed

✅ Google Gemini API Key

✅ .docx input file (e.g., Sample_BRD_Policy_Management_System.docx)

✅ Internet access for API calls

✅ FAISS setup within Langflow

💡 Important Instruction
⚠️ Make sure to select Gemini 2.0 Flash for all LLM components (Google Generative AI nodes) in both sections of the pipeline. This ensures faster, optimized, and cost-effective generation.

🧩 Pipeline Overview
🔽 STEP 1: Preprocessing Section (Bottom)
Run this section first to extract structured content and build the FAISS index.

Node	Purpose
File Input	Upload your .docx input file
Google Generative AI (LLM)	Extracts structured metadata (title, story, keywords)
Text Splitter	Breaks long story into chunks for indexing
FAISS Index Builder	Embeds and stores the chunks into a FAISS vector store
FAISS Retriever	Validates vector DB search functionality

→ Use Gemini 2.0 Flash for the LLM in story extraction.

🚀 STEP 2: Prompt Generation Section (Top)
After preprocessing is done, run this section to generate the cinematic prompt.

Node	Purpose
FAISS Retriever	Retrieves most relevant story chunk(s)
Prompt Template	Combines chunks into a structured cinematic-style prompt
Google Generative AI (LLM)	Expands into a rich prompt for Veo
Cloud Output	Displays final cinematic prompt
(Optional): Additional prompt logger or reformatter	

→ Use Gemini 2.0 Flash for both LLMs (retrieved chunk expansion + final cinematic prompt).

✅ Workflow Execution Steps
Upload your .docx file using the File Input node.

Run the bottom section to:

Extract content (title, story, keywords)

Chunk and embed text into FAISS

Run the top section to:

Retrieve chunks from FAISS

Generate a cinematic prompt using Gemini 2.0 Flash

Copy the final prompt from the Cloud Output node.

(Optional) Use this prompt in Google Veo's generate-preview API.

🔗 Key Benefits
✅ End-to-end document-to-video prompt pipeline

✅ Uses FAISS for contextual retrieval

✅ Modular and editable in Langflow

✅ Fast response via Gemini 2.0 Flash

