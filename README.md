# Taylor Swift Lyrics Explanation Model (Fine-tuned on Davinci-002)

This project involves fine-tuning the OpenAI Davinci-002 model to explain and interpret the lyrics of Taylor Swift's songs. By fine-tuning the model using Taylor Swift's lyrical data, the goal is to generate insightful and meaningful explanations for her lyrics. This project was executed using Python and OpenAI's fine-tuning API.

## Overview
The primary objective of this project is to leverage OpenAI's GPT models to provide interpretations and explanations of Taylor Swift's song lyrics. The model has been fine-tuned to understand the sentiment, themes, and narrative styles prevalent in her music and generate human-like insights based on this understanding.

**Key Features:**

- Uses a fine-tuned GPT-3 Davinci-002 model.  
- Focuses on generating explanations for the lyrics of Taylor Swift’s albums.  
- Provides insights based on the sentiment, themes, and stories embedded in the lyrics.  
- Implements the fine-tuning process in Python using OpenAI's API.

## Data Collection and Preprocessing
**Data Collection:** The data used for fine-tuning consists of Taylor Swift's lyrics from her albums. Specifically, the lyrics were collected from her albums *Midnights, Folklore, Evermore, Lover, Reputation, and 1989,* though this methodology can be extended to her entire discography.

- **Source:** Lyrics were gathered using the Lyrics.ovh API.
- **Format:** The data is stored in JSONL format, where each entry includes a prompt (the lyric or song) and a completion (the generated explanation).

An example entry in the JSONL dataset:
```json
{
    "prompt": "You drew stars around my scars",
    "completion": "This line symbolizes emotional healing. The stars represent hope and beauty, while scars symbolize past pain. The image suggests that someone brought light and beauty to the narrator's painful experiences."
}
```

### Preprocessing
Some initial preprocessing was designed to:

- Remove unnecessary characters (e.g., punctuation, annotations).  
- Normalize text (lowercasing, removing extra spaces).  
- Structure data into a format compatible with OpenAI’s fine-tuning API (JSONL).

## Fine-Tuning Process
The fine-tuning was performed on the Davinci-002 model using OpenAI's API. The process involved feeding the model a series of prompts (lyrics) and completions (pre-written explanations) to teach the model how to generate human-like interpretations of the lyrics.

### Steps:
- Model Selection: We selected OpenAI’s Davinci-002 model, known for its strong language understanding capabilities.  
- Data Upload: The preprocessed JSONL data was uploaded to OpenAI’s servers using the OpenAI CLI.  
- Fine-Tuning Execution: The fine-tuning process was triggered using the OpenAI Python library, specifying the dataset and hyperparameters such as the number of epochs, batch size, and learning rate.

>The *fine_tune_lyrics.ipynb* script also automates this process.

## Results and Outputs
The model successfully generates insightful explanations of Taylor Swift's lyrics. Below are a few examples of the generated outputs:  

- **Input Lyric:** "I knew you’d linger like a tattoo kiss"  
  - **Model Explanation:** This lyric conveys the feeling of a lasting emotional impression, comparing it to the permanence of a tattoo. The 'kiss' adds a sense of tenderness, making the memory both intimate and unshakeable.  
- **Input Lyric:** "August slipped away into a moment in time"
  - **Model Explanation:** This line reflects on the fleeting nature of time and memories, particularly how a single moment or season can feel like it passes too quickly, slipping into the past.

## Challenges and Considerations
- **Data Limitations:** Lyrics often have multiple interpretations, and the model might not capture all possible meanings. The explanations are based on the specific completions provided during fine-tuning.  
- **Model Bias:** The fine-tuned model may sometimes reflect biases present in the training data, particularly in how it interprets specific themes or emotions.  
- **Fine-tuning Costs:** Fine-tuning large language models can be computationally expensive, so it's essential to monitor token usage and optimize the number of epochs and data samples.

## Future Improvements
- **Expand Dataset:** Incorporate lyrics from more Taylor Swift albums or even other artists to diversify the model's capabilities.  
- **Interactive Web Application:** Build a web app that allows users to input any lyric and receive an explanation in real time.  
- **Model Tuning:** Further optimize the fine-tuning process by experimenting with different hyperparameters to improve explanation quality.  
- **Sentiment and Thematic Analysis:** Integrate a sentiment analysis component to generate not just explanations but also the emotional context for each lyric.  

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.
