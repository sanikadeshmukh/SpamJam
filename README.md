# SpamJam 🚫✉️

A simple Flask web app that classifies messages as **spam** or **jam** using a Naive Bayes classifier.

## 📌 Features

- Trained on a labeled dataset (`spam.csv`)
- Uses `CountVectorizer` for text feature extraction
- Predicts message type (Spam or Not Spam)
- Web interface using HTML templates

## 🗂️ Project Structure

```
.
├── app.py              # Main Flask app
├── spam.csv            # Labeled SMS dataset
├── home.html       # Input form
└── result.html     # Output prediction
└── README.md           # Project info
```

## ⚙️ How to Run

1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/SpamJam.git
   cd SpamJam
   ```

2. Install required packages:
   ```bash
   pip install flask pandas scikit-learn joblib
   ```

3. Run the app:
   ```bash
   python app.py
   ```

## 🧠 How It Works

- Loads `spam.csv`, removes unnecessary columns.
- Converts `class` column: `'jam'` = 0, `'spam'` = 1.
- Applies `CountVectorizer` to transform text to features.
- Trains `MultinomialNB` on the data.
- Takes input message and predicts whether it's spam.

## ⚠️ Note

🔁 The model is retrained on every prediction. For optimization:
- Train and save the model once.
- Load the model using `joblib.load()` during inference.

## 📊 Example

**Input:**  
> "Congratulations! You've won a $1000 Walmart gift card. Click here to claim now!"

**Output:**  
> `Spam`

---

⭐ Star the repo if you find it useful!
