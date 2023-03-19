# Text Classification Prompt Model for ChatGPT and OpenAi
This repository contains a language model prompt trained by OpenAI that can classify text inputs based on emotions, personality traits, and clinical psychological traits. The model provides classifications for a range of emotions and personality traits, as well as indications of clinical traits such as anxiety and depression. The repository includes a primary prompt for calling the model, as well as sample JavaScript code and a curl command for calling the OpenAI API directly. Please note that this is a language model and not a clinical tool, and the classifications provided should not be considered as professional psychological assessments.

## Introduction
This language model prompt can be useful for a range of applications, such as analyzing customer feedback, identifying potential psychological issues in written communications, categorizing social media posts or comments, developing chatbots or virtual assistants that can respond appropriately to user emotions, providing personalized content or recommendations based on user personality traits and preferences, and supporting research in psychology, linguistics, or related fields by providing large-scale data analysis.

* Analyzing customer feedback to identify common emotions and personality traits
* Identifying potential psychological issues in written communications such as emails or chat logs
* Categorizing social media posts or comments based on emotional content or personality traits
* Developing chatbots or virtual assistants that can respond appropriately to user emotions
* Providing personalized content or recommendations based on user personality traits and preferences
* Supporting research in psychology, linguistics, or related fields by providing large-scale data analysis

## Prompt
```
Initialized: Text Classification Model for Emotions, Personality Traits, and Clinical Psychological Traits

Instructions: This model classifies text inputs based on emotions, personality traits, and clinical psychological traits. 
Provide the text you want to classify.

Examples:
Input: "I love my new job, it's fantastic!" {"emotion":"joy", "confidence_emotion":0.95, "intensity_emotion":0.90, "personality_trait":"optimistic", "confidence_trait":0.92, "clinical_trait":"non-depressive", "confidence_clinical":0.97}
Input: "I can't believe they messed up my order again!" {"emotion":"anger", "confidence_emotion":0.92, "intensity_emotion":0.85, "personality_trait":"impatient", "confidence_trait":0.90, "clinical_trait":"non-anxious", "confidence_clinical":0.95}
Input: "The food was great, but the service was terrible." {"emotion":"mixed", "confidence_emotion":0.88, "intensity_emotion":0.75, "personality_trait":"critical_thinker", "confidence_trait":0.87, "clinical_trait":"non-anxious", "confidence_clinical":0.94}
Input: "This product exceeded my expectations!" {"emotion":"surprise", "confidence_emotion":0.97, "intensity_emotion":0.80, "personality_trait":"open-minded", "confidence_trait":0.95, "clinical_trait":"non-depressive", "confidence_clinical":0.98}
Input: "I'm so frustrated with the slow internet connection!" {"emotion":"frustration", "confidence_emotion":0.93, "intensity_emotion":0.88, "personality_trait":"impatient", "confidence_trait":0.89, "clinical_trait":"non-anxious", "confidence_clinical":0.96}

Input: "Your text here"
```

## Usage
To use the model, simply provide the text you want to classify and the model will respond with the appropriate classification. The classification response includes the following parameters:

* Emotion: The primary emotion detected in the text (e.g., joy, anger, mixed, surprise, frustration, etc.)
* Confidence_emotion: A value between 0 and 1 representing the model's confidence in its emotion classification.
* Intensity_emotion: A value between 0 and 1 indicating the intensity of the primary emotion detected in the text.
* Personality_trait: The primary personality trait detected in the text (e.g., optimistic, impatient, critical_thinker, open-minded, etc.)
* Confidence_trait: A value between 0 and 1 representing the model's confidence in its personality trait classification.
* Clinical_trait: The primary clinical psychological trait detected in the text (e.g., non-depressive, non-anxious, etc.)
* Confidence_clinical: A value between 0 and 1 representing the model's confidence in its clinical psychological trait classification.

## Input Examples
Here are some examples of text inputs and their corresponding classification responses:

```
Input: "I love my new job, it's fantastic!" 
Output: {"emotion":"joy", "confidence_emotion":0.95, "intensity_emotion":0.90, "personality_trait":"optimistic", "confidence_trait":0.92, "clinical_trait":"non-depressive", "confidence_clinical":0.97}

Input: "I can't believe they messed up my order again!"
Output: {"emotion":"anger", "confidence_emotion":0.92, "intensity_emotion":0.85, "personality_trait":"impatient", "confidence_trait":0.90, "clinical_trait":"non-anxious", "confidence_clinical":0.95}

Input: "The food was great, but the service was terrible."
Output: {"emotion":"mixed", "confidence_emotion":0.88, "intensity_emotion":0.75, "personality_trait":"critical_thinker", "confidence_trait":0.87, "clinical_trait":"non-anxious", "confidence_clinical":0.94}

Input: "This product exceeded my expectations!"
Output: {"emotion":"surprise", "confidence_emotion":0.97, "intensity_emotion":0.80, "personality_trait":"open-minded", "confidence_trait":0.95, "clinical_trait":"non-depressive", "confidence_clinical":0.98}

Input: "I'm so frustrated with the slow internet connection!"
Output: {"emotion":"frustration", "confidence_emotion":0.93, "intensity_emotion":0.88, "personality_trait":"impatient", "confidence_trait":0.89, "clinical_trait":"non-anxious", "confidence_clinical":0.96}
```

## Curl Example

```
curl -X POST \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer YOUR_API_KEY_HERE" \
  -d '{"prompt":"Initialized: Text Classification Model for Emotions, Personality Traits, and Clinical Psychological Traits\n\nInstructions: This model classifies text inputs based on emotions, personality traits, and clinical psychological traits. Provide the text you want to classify.\n\nExamples:\nInput: \"I love my new job, it'\''s fantastic!\" {\"emotion\":\"joy\", \"confidence_emotion\":0.95, \"intensity_emotion\":0.90, \"personality_trait\":\"optimistic\", \"confidence_trait\":0.92, \"clinical_trait\":\"non-depressive\", \"confidence_clinical\":0.97}\nInput: \"I can'\''t believe they messed up my order again!\" {\"emotion\":\"anger\", \"confidence_emotion\":0.92, \"intensity_emotion\":0.85, \"personality_trait\":\"impatient\", \"confidence_trait\":0.90, \"clinical_trait\":\"non-anxious\", \"confidence_clinical\":0.95}\nInput: \"The food was great, but the service was terrible.\" {\"emotion\":\"mixed\", \"confidence_emotion\":0.88, \"intensity_emotion\":0.75, \"personality_trait\":\"critical_thinker\", \"confidence_trait\":0.87, \"clinical_trait\":\"non-anxious\", \"confidence_clinical\":0.94}\nInput: \"This product exceeded my expectations!\" {\"emotion\":\"surprise\", \"confidence_emotion\":0.97, \"intensity_emotion\":0.80, \"personality_trait\":\"open-minded\", \"confidence_trait\":0.95, \"clinical_trait\":\"non-depressive\", \"confidence_clinical\":0.98}\nInput: \"I'\''m so frustrated with the slow internet connection!\" {\"emotion\":\"frustration\", \"confidence_emotion\":0.93, \"intensity_emotion\":0.88, \"personality_trait\":\"impatient\", \"confidence_trait\":0.89, \"clinical_trait\":\"non-anxious\", \"confidence_clinical\":0.96}\n\nInput: ","max_tokens":1024,"n":1,"stop":"\n"}' \
  https://api.openai.com/v1/completions

```
## Javascript Example.
```
const prompt = "Initialized: Text Classification Model for Emotions, Personality Traits, and Clinical Psychological Traits\n\nInstructions: This model classifies text inputs based on emotions, personality traits, and clinical psychological traits. Provide the text you want to classify.\n\nExamples:\nInput: \"I love my new job, it's fantastic!\" {\"emotion\":\"joy\", \"confidence_emotion\":0.95, \"intensity_emotion\":0.90, \"personality_trait\":\"optimistic\", \"confidence_trait\":0.92, \"clinical_trait\":\"non-depressive\", \"confidence_clinical\":0.97}\nInput: \"I can't believe they messed up my order again!\" {\"emotion\":\"anger\", \"confidence_emotion\":0.92, \"intensity_emotion\":0.85, \"personality_trait\":\"impatient\", \"confidence_trait\":0.90, \"clinical_trait\":\"non-anxious\", \"confidence_clinical\":0.95}\nInput: \"The food was great, but the service was terrible.\" {\"emotion\":\"mixed\", \"confidence_emotion\":0.88, \"intensity_emotion\":0.75, \"personality_trait\":\"critical_thinker\", \"confidence_trait\":0.87, \"clinical_trait\":\"non-anxious\", \"confidence_clinical\":0.94}\nInput: \"This product exceeded my expectations!\" {\"emotion\":\"surprise\", \"confidence_emotion\":0.97, \"intensity_emotion\":0.80, \"personality_trait\":\"open-minded\", \"confidence_trait\":0.95, \"clinical_trait\":\"non-depressive\", \"confidence_clinical\":0.98}\nInput: \"I'm so frustrated with the slow internet connection!\" {\"emotion\":\"frustration\", \"confidence_emotion\":0.93, \"intensity_emotion\":0.88, \"personality_trait\":\"impatient\", \"confidence_trait\":0.89, \"clinical_trait\":\"non-anxious\", \"confidence_clinical\":0.96}\n\nInput: ";
const apiKey = "YOUR_API_KEY_HERE";

// Define the endpoint and parameters for the OpenAI API
const endpoint = "https://api.openai.com/v1/completions";
const headers = { "Content-Type": "application/json", "Authorization": `Bearer ${apiKey}` };
const data = { prompt: prompt, max_tokens: 1024, n: 1, stop: "\n" };

// Call the OpenAI API to classify the input text
fetch(endpoint, {
  method: "POST",
  headers: headers,
  body: JSON.stringify(data)
})
  .then(response => response.json())
  .then(response => {
    const output = response.choices[0].text.trim();
    console.log(output);
  })
  .catch(error => {
    console.error(error);
  });
```

## Advanced Usage
### Few Shot Prompts
A few-shot prompt is a prompt that allows a language model to generalize to new tasks by providing a small number of examples (usually less than 10) of what the task looks like. The model then uses those examples to learn how to perform the task on new inputs.

This prompt for the Text Classification Model for Emotions, Personality Traits, and Clinical Psychological Traits is a few-shot prompt because it includes examples of text inputs and their corresponding classifications for emotions, personality traits, and clinical psychological traits. The model uses these examples to learn how to classify new inputs based on their similarity to the provided examples.

To modify this prompt for more accurate results, you can add more examples of text inputs and their corresponding classifications, especially for more nuanced or specific emotions and personality traits. You can also adjust the parameters of the OpenAI API call, such as the temperature parameter which controls the creativity or randomness of the model's responses, or the max_tokens parameter which limits the maximum number of tokens (words or symbols) in the model's output.
