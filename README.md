# COVID-19 Hospitalization Challenge

**Please time your work, and try to limit yourself to ~6 hours time! (if more, please report the exact time)**

To use the dataset in this challenge, please read the privacy data usage [here](https://github.com/doaa-altarawy/COVID-Hospitalization-challenge/blob/master/Data_usage_agreement.md).

This dataset includes information about patients admitted to the hospital for COVID-19. Some have recovered and others died. In this challenge, you will explore the data and build a machine learning model to predict the outcome.

There are so many ways you can explore, visualize, engineer your features, and tell a story with this data. It will be interesting to see your approaches! 

Pay particular attention to coding style and how you present your findings - communicate your critical thinking, tell a **data story**. Please code and annotate your analysis in a Jupyter notebook. Your notebook should be well-documented and self-explanatory.

Note, you can search online for **code syntax** but not for solutions to this or similar problems. Copying code from the internet automatically disqualifies the candidate.

## Dataset file:
In this repo:
`data/challenge_data/covid_hospitalization_dataset.csv`

## Challenge Tasks:
  1. Task 1: Exploration:
      1. Explore the data to find any useful and interesting insights and visualizations
      1. Bonus task: Out of the 18 comorbidities present in the patients, what are the top ones associated with death? (Hint: to load the comorbidities as a list rather than a str use: `df['comorbidities'] = df['comorbidities'].apply(eval)`
  2. Task 2: Building the model:
      * Build a machine learning model from this dataset that predicts if a COVID patient is likely to die when admitted to the hospital. Choose features that you see suitable (you don't have to use all columns). Make sure to justify your choices when applicable.
      * You can make reasonable assumptions, but they must be clearly explained in the Notebook.
      * What do you think is the best evaluation metric for this particular problem? explain.
  
## Solution Submission:

Please create a fork of this repo into your GitHub, and create a git branch and push your submissions as a **Jupyter Notebook** in the Submissions sub-folder with the naming convention: firstname_lastname_date.
Email back the link to your GitHub repo.

## More information about columns:

#### 1- 'admission_disposition' : WARD or ICU
When the patient was admitted to the hospital were they in a WARD or ICU? Note that they can move from WARD to ICU later if needed.

  - A WARD is a room in a hospital that has beds for many people, often people who need similar treatment.
  - An ICU is a part of a hospital where patients who are dangerously ill are looked after constantly. ICU is an abbreviation for 'intensive care unit'.
  
#### 2- Blood tests:
The following columns are the test results of blood work of the patient at admission: (if the value is Null, then it's unknown or wasn't measured)

  *  'wbc', 'rbc', 'hemoglobin', 'hematocrit', 'mcv', 'mch', 'mchc', 'rdw', 'platelet_count', 'pt', 'alt', 'ast', 'serum_creatinine', 'sodium', 'potassium', 'total_serum_bilirubin', 'lactate'
  
#### 3- Other tests and patient's vitals:
(if the value is Null, then it's unknown or wasn't measured)
  *  'systolic_blood_pressure', 'diastolic_blood_pressure', 'heart_rate',
       'respiratory_rate', 'oxygen_saturation', 'temperature', 'motor',
       'verbal', 'eye'
  

#### 4- More information about the outcome:
These columns show what happens to the patient later after admission, i.e., they are calculated after the patient's dismissal or death.
   * 'days_in_hospital_prior_to_death' (if died, otherwise null)
   * 'hospital_length_of_stay'
   * 'icu_length_of_stay' (if admitted to ICU), otherwise null
   * 'days_in_hospital_prior_to_icu_admission' (if admitted to ICU), otherwise null
   * 'time_on_mechanical_ventilation' (if intubated, otherwise null)
   * 'days_in_hospital_prior_to_mechanical_ventilation' (if intubated, otherwise null)
   * 'intubated': was the patient initially intubated when admitted? 
   
   Note: Intubation is placing a tube in your throat to help move air in and out of your lungs (can be mechanical or not). Mechanical ventilation is the use of a machine to move air in and out of your lungs. More info here [here](https://www.wnyurology.com/content.aspx?chunkiid=112024)

#### 5- 'Comorbidities':
This column has a list of other diseases or medical conditions in that COVID patient.

#### 6- The outcome column we are measuring:
  * 'did_the_patient_die_in_hospital': Yes or No