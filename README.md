# CVALIGN
---

# CV Evaluator Website

### Problem Statement

Manual CV screening is time-consuming, inconsistent, and prone to bias. Recruiters struggle to efficiently identify the best candidates among hundreds of applications.

### Goal

Create a web platform that automates CV evaluation against job role descriptions using an AI Retrieval-Augmented Generation (RAG) model. It scores CVs for relevance and generates personalized feedback to assist hiring decisions.

### Features

* Upload job descriptions detailing required skills and qualifications
* Upload and parse CVs in PDF/DOCX formats
* Automated relevance scoring of CVs
* Personalized feedback on strengths, weaknesses, and fit
* Dashboard showing ranked candidates with filtering and comparison
* Role-based access control for different user types (recruiters, managers, admins)
* Cloud storage integration for uploaded CVs

### Tech Stack

* **Backend:** Python (FastAPI, PyTorch, Hugging Face Transformers, LangChain)
* **Vector Database:** Pinecone or FAISS
* **Frontend:** Basic HTML/CSS (React planned for future)
* **Storage:** Cloudinary or similar cloud storage

### Setup Instructions

1. **Clone the repository**

   ```bash
   git clone <repo_url>
   cd AI-Resume-Analyzer
   ```

2. **Create and activate a virtual environment**

   ```bash
   python -m venv venvapp
   # On Windows:
   .\venvapp\Scripts\activate
   # On macOS/Linux:
   source venvapp/bin/activate
   ```

3. **Install dependencies**

   ```bash
   pip install -r requirements.txt
   ```

4. **Set up the database**

   * Create a MySQL database named `cv`
   * Update database credentials in `App/App.py` (Line 95):

     ```python
     connection = pymysql.connect(host='localhost', user='root', password='your_password', db='cv')
     ```

5. **Replace the custom `resume_parser.py`**

   * Copy the provided `resume_parser.py` to `venvapp\Lib\site-packages\pyresparser`

6. **Run the app**

   ```bash
   streamlit run App/App.py
   ```

7. **Access the app**

   Open [http://localhost:8501](http://localhost:8501) in your browser.

---