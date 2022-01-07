# Hired
A job matching and auto-applying website

## Inspiration

As a result of the COVID-19 pandemic, millions of people lost their jobs and the US unemployment rate reached an all-time-high of nearly 15% in April of 2020. Job hunting has never been easy. It's time consuming, repetitive, and draining.

As students, we've spent countless hours applying to internships and filling in the same details over and over again.

Hired is here to change that.

## What it does

Hired is broken into two main features:

First, it parses your resume to automatically fill out as many fields as it can (if you wrote it on your resume once, why should you have to also enter it into a form a million times?). It then will let you modify any of the fields it gathered, and then update your information.

Second, our extensive bot network will be constantly adding new jobs to our database of jobs and will automatically pick a few that best suit you, using fuzzy matching and cosine similarity. These jobs will be displayed to you all in one place at one time, and you can select as many as you would like and click apply once. 

## Implementation

The frontend is built with HTML, CSS, JS, and Bootstrap. We use Javascript's Fetch API to communicate with the backend. The frontend is hosted on Firebase.

The backend is a Ubuntu server configured with Nginx serving files. It is built using python and flask, which then communicates with a Firebase Realtime Database and a Google Cloud Storage Bucket to store resumes.

This project also has a cronjob running on our Ubuntu server. This cronjob is constantly indexing many job sites to pull as much useful info as it can, and continues to train our ML model as it goes. This ensures that even with a limited number of jobs on the market, our algorithms will always be able to provide you with the best job recommendations out there.

## Implrovements for future

We really hope to improve on our resume parser. Currently, that is definitely a bottleneck.

Lastly, our bots have trouble applying to many websites where you need to create an account, or there is an "I'm not a robot" functionality. We are thinking of perhaps packaging this as a chrome extension, and when it detects job fields it will fill them out for you.
