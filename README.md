# Preprocessing and Analyzing Text Sentiment with NLTK and TextBlob

## Preprocessing Data with NLTK

This repository demonstrates how to preprocess textual data using Python libraries such as NLTK, TextBlob, and Newspaper3k. It covers how to scrape articles, clean and process text data, and analyze its sentiment.

## Required Libraries
- NLTK: The Natural Language Toolkit (NLTK) is used for text preprocessing tasks like tokenization and downloading necessary language resources.
- TextBlob: A simple Python library for processing textual data. It is used here to perform sentiment analysis on the extracted article.
- Newspaper3k: A Python library used for extracting and parsing articles from the web.
- lxml: An XML and HTML processing library used in conjunction with the newspaper3k for efficient content extraction.
Once installed, NLTK will automatically download the necessary data packages (e.g., tokenizers) to process the text data.

## Usage
The example script processes an article from the web, performs text extraction, and analyzes sentiment using TextBlob.

### 1. Install the dependencies
  ```bash
pip install nltk textblob newspaper3k
pip install lxml[html_clean]
```
### 2. Download necessary NLTK data
The script starts by downloading NLTK's tokenizer for text processing:

  ```bash
import nltk
nltk.download('punkt_tab')
```
### 3. Extract article content
Next, the script uses newspaper3k to download and parse an article:

  ```bash
from newspaper import Article

url = 'https://blog.reedsy.com/short-story/8z78f4/'

article = Article(url)
article.download()
article.parse()
article.nlp()

text = article.text
print(text)
```

The article text is printed and can be processed further.

### 4. Analyze sentiment with TextBlob
Sentiment analysis is performed on the extracted text using TextBlob:

  ```bash
from textblob import TextBlob

blob = TextBlob(text)
sentiment = blob.sentiment.polarity
print(f"Sentiment: {'positive' if sentiment > 0 else 'negative' if sentiment < 0 else 'neutral'}")
```
This outputs whether the sentiment of the article is positive, negative, or neutral based on its polarity score.

### Example Output
After running the code, you'll see the extracted text printed, followed by the sentiment analysis result:

  ```bash
Sentiment: positive
```

## License
This code is licensed under the MIT License. See the LICENSE file for more details.

## Contributions
Feel free to open issues or submit pull requests if you want to contribute to this project!
