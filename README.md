# Hierarchical Text Summarization
This README provides a complete guide to setting up and executing the Hierarchical Text Summarization model, a data-driven pipeline that analyzes 28,756 public comments from CDC regulations, performs sentiment analysis, and generates hierarchical summaries using extractive and abstractive methods.

## Dataset
The model processes public comments submitted to the CDC Advisory Committee on Immunization Practices, available on the regulations.gov portal:
[Regulations.gov CDC Comment Dataset](https://www.regulations.gov/document/CDC-2025-0454-0001)
Download the dataset by following the bulk download instructions on regulations.gov, or use the API to retrieve all comments related to docket ID CDC-2025-0454. The dataset is provided in CSV format.

## Step-by-Step Execution Instructions

### 1. Install Dependencies
Before running the project, ensure you have Python 3.10 or higher installed. Install all dependencies using:

```bash
pip install -r requirements.txt
```

### 2. Prepare the Dataset
- Download the CDC regulations comment dataset from regulations.gov.
- Place the dataset in your project directory. Dataset name is "combined_comments.csv"
- Ensure the dataset is clean and properly formatted (CSV file).

### 3. Run the Complete Pipeline
To execute the full pipeline, run the provided Jupyter Notebook.

The system will:
- Preprocess the comments using TF-IDF ranking.
- Perform sentiment analysis using the DeBERTa-v3 model.
- Generate individual summaries with LLaMA-3.3-70B via Groq API.
- Produce hierarchical summaries by grouping comments by sentiment and combining extractive and abstractive methods, achieving 82-90% text compression.

## Troubleshooting
- Ensure all dependencies are correctly installed via `requirements.txt`.
- Verify that the dataset is downloaded and paths are set.
- For Groq API, ensure the endpoint is accessible and keys are valid.
- Restart the runtime if the kernel crashes due to high memory usage.
- Validate that preprocessing steps match the dataset format before summarization.
