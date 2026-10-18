# Research Assistance Tool

A lightweight research assistant built with Python, Streamlit, and LangChain. It helps users quickly understand important AI research papers by generating summaries in different explanation styles and lengths.

## Description

The Research Assistance Tool is designed for students, researchers, and developers who want a simple way to explore major research papers without reading long technical documents from scratch. Users can choose a paper, select an explanation style (beginner-friendly, technical, code-oriented, or mathematical), and choose the summary length. The tool then uses a language model to generate a structured explanation with clear reasoning, analogies, and relevant mathematical context when available.

This project is useful for:
- Learning complex research concepts faster
- Comparing explanations across different styles
- Getting a quick overview before reading the full paper
- Turning dense technical content into digestible summaries

## Features

- Select from a list of important AI research papers
- Choose explanation style:
  - Beginner-Friendly
  - Technical
  - Code-Oriented
  - Mathematical
- Choose summary length:
  - Short
  - Medium
  - Long
- Generate a paper summary using LangChain + OpenAI models
- Display results in a simple Streamlit web interface
- Uses prompt templates to maintain consistency in output

## Tech Stack

- Python
- Streamlit
- LangChain
- LangChain OpenAI
- Python-dotenv

## Project Structure

```text
Research_Assistance_Tool/
├── prompt_ui.py          # Streamlit interface for the research assistant
├── prompt_generator.py   # Generates the prompt template JSON file
├── prompt_template.py     # Example prompt template usage
├── template.json          # Prompt template used by the app
├── .env                  # Environment variables (not committed yet)
└── README.md             # Project documentation
```

## Setup

1. Clone or open the project folder.
2. Create a virtual environment (optional but recommended):

```bash
python -m venv venv
venv\Scripts\activate
```

3. Install the required dependencies:

```bash
pip install streamlit langchain langchain-openai python-dotenv
```

4. Create a `.env` file in the project root and add your OpenAI API key:

```env
OPENAI_API_KEY=your_api_key_here
```

5. Generate the prompt template if needed:

```bash
python prompt_generator.py
```

6. Run the application:

```bash
streamlit run prompt_ui.py
```

## Usage

1. Open the Streamlit app in your browser.
2. Select the research paper you want to summarize.
3. Choose the explanation style.
4. Choose the summary length.
5. Click the "Summarize" button.
6. The model will generate the explanation and show it on the page.

## How It Works

The app loads a prompt template, takes the user-selected paper and formatting preferences, and passes that information to a language model. The model is prompted to summarize the paper in the requested style while keeping the content accurate and easy to understand.

The prompt also instructs the model to say "Insufficient information available" whenever the required information is missing rather than guessing.

## Example Output

The app is designed to produce summaries such as:
- a beginner-friendly overview of a paper's motivation and key ideas
- a technical explanation of the methodology and architecture
- a more mathematical breakdown with equations and intuition
- a code-oriented description that connects concepts to implementation patterns

## Notes

- This project is a simple research summarization demo.
- It works best when used with a valid OpenAI API key.
- The `template.json` file is generated from the prompt template logic and is important for the app to load prompts correctly.

## Future Improvements

Possible enhancements include:
- adding more research papers or custom paper inputs
- supporting document uploads from PDFs or text files
- generating bullet summaries, comparison tables, and key takeaways
- adding chat-based follow-up questions for deeper exploration
- integrating with local or open-source LLMs
