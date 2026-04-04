## Setup Instructions

1. Clone the repo
```bash
git clone https://github.com/shreya0119/Alzheimer-Detection.git
cd Alzheimer-Detection
```

2. Create and activate virtual environment
```bash
python -m venv .venv
.venv\Scripts\activate  # Windows
```

3. Install dependencies
```bash
pip install -r requirements.txt
```

4. Download the weights file from Google Drive and place it in the 
`models/` folder as `alzheimer_pro_weights.weights.h5`

https://drive.google.com/file/d/1b3vrvXOXgelaJb9SRXQnuGrAQEpWJrgv/view?usp=drive_link 

5. Run the app
```bash
python app.py
```
App opens automatically at http://127.0.0.1:5000

## Model Details
- Base: MobileNetV2 pretrained on ImageNet (frozen)
- Training: 2 phases × 10 epochs each
- Validation Accuracy: ~80%
- Class weights applied to handle dataset imbalance
- Clinical sensitivity override for Moderate Dementia detection

## Limitations
- Optimized for OASIS-protocol T1 axial MRI scans
- Cross-scanner generalization is an open problem in medical imaging AI
- Performance varies on images from different scanners or protocols
