# steams-of-thoughts

## Structured Journal Analyzer using Groq + LLaMA 3

This Python script takes a stream-of-consciousness journal entry and organizes it into structured JSON output using the LLaMA 3 model via Groq's API. It helps in categorizing thoughts into well-defined mental and emotional areas for personal reflection or journaling insights.

### Requirements
* Python 3.7+

* groq Python package

* A valid Groq API key

###  Installation
* Clone this repository or copy the script

* Install dependencies:
```
pip install groq

```
### Set your Groq API key:

You can either:

* Add your API key directly into the script:
```
GROQ_API_KEY = "your_groq_api_key"
```
* Or use environment variables by uncommenting the following:
```
GROQ_API_KEY = os.getenv("GROQ_API_KEY")

```
And then set the variable:

```
export GROQ_API_KEY="your_groq_api_key"

```
### Usage
Run the script:

```
python main.py
```
When prompted, enter a journal entry. Example
```
I've been feeling anxious. My sleep's been awful, and I skipped dinner last night. I argued with my brother again. Work is just overwhelming lately.
```
You will get structured JSON output like:

json
```
[
  {
    "category": "Health & Well-being",
    "entries": [
      {
        "entry": 1,
        "title": "Physical Health",
        "thoughts": [
          "Skipped dinner.",
          "Awful sleep."
        ]
      }
    ]
  },
  {
    "category": "Family & Relationships",
    "entries": [
      {
        "entry": 1,
        "title": "Brother Conflict",
        "thoughts": [
          "Argued with brother again."
        ]
      }
    ]
  },
  {
    "category": "Work Stress",
    "entries": [
      {
        "entry": 1,
        "title": "Overwhelming Tasks",
        "thoughts": [
          "Work is overwhelming."
        ]
      }
    ]
  }
]
```
### Categories
The assistant may extract your thoughts into these categories:

* Health & Well-being

* Family & Relationships

* Work Stress

* Community & Meaningful Work

* Personal Growth

* Emotional State

* Habits & Patterns

Only relevant categories are included in the output.

###  Troubleshooting
* 401: Invalid API Key
- Make sure your API key is correct.

- Double-check you're using the Groq API key and not a key from another provider.

- Try regenerating your API key from the Groq dashboard.

* JSONDecodeError
- Sometimes the model output may include formatting issues.

- In such cases, the script prints the raw output to help you debug.



