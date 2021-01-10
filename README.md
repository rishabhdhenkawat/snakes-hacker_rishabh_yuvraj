# Digital Human For Anti Depression with Verbal Games

Must watch link :https://youtu.be/kGU-k4RVA2w
---
We have made a digital human to make the life of people easy to deal with bad times, even when they are alone. We have made an AI to which will talk to you and help to deal with the mood swings and many more mental issues with the use of a digital human. Even u can play verbal games with this digital human. We tried our best at the weekend to make this society a better place.

This effort addresses an automated device for detecting depression from acoustic features in speech. The tool is aimed at lowering the barrier of entry in seeking help for potential mental illness and supporting medical professionals' diagnoses.

Early detection and treatment of depression is essential in promoting remission, preventing relapse, and reducing the emotional burden of the disease. Current diagnoses are primarily subjective, inconsistent across professionals, and expensive for the individual who may be in dire need of help. Additionally, early signs of depression are difficult to detect and quantify. These early signs have a promising potential to be quantified by machine learning algorithms that could be implemented in a wearable artificial intelligence (AI) or home device.

Automatic Depression Detection (ADD) is a relatively nascent topic that first appeared in 2009. DepressionDetect presents a novel approach focusing on two aspects that receive scant research attention: class imbalance and data representation (feature extraction).

It can also play verbal games like “Sing along” in the English language


## Dataset
All audio recordings and associated depression metrics were provided by the [DAIC-WOZ Database](http://dcapswoz.ict.usc.edu/), which was compiled by USC's Institute of Creative Technologies and released as part of the 2016 Audio/Visual Emotional Challenge and Workshop ([AVEC 2016](http://sspnet.eu/avec2016/)). The dataset consists of 189 sessions, averaging 16 minutes, between a participant and virtual interviewer called Ellie, controlled by a human interviewer in another room via a "[Wizard of Oz](https://en.wikipedia.org/wiki/Wizard_of_Oz_experiment)" approach. Prior to the interview, each participant completed a psychiatric questionnaire ([PHQ-8](http://patienteducation.stanford.edu/research/phq.pdf)), from which a binary "truth" classification (depressed, not depressed) was derived.

A representative transcribed interview excerpt is seen below:

> **Ellie:** Who’s someone that’s been a positive influence in your life?

> **Participant:** Uh my father.

> **Ellie:** Can you tell me about that?

> **Participant:** Yeah, he is a uh. He’s a very he’s a man of few words. And uh he's very calm. Slow to anger. And um very warm very loving man. Responsible. And uh he’s a gentleman has a great sense of style and he’s a great cook.


## Acoustic Features of Speech
While some emotion detection research focuses on the semantic content of audio signals in predicting depression, I decided to focus on the [prosodic](http://clas.mq.edu.au/speech/phonetics/phonology/intonation/prosody.html)  features, which have also been found to be promising predictors of depression. Prosodic features can be generally characterized by a listener as pitch, tone, rhythm, stress, voice quality, articulation, intonation, etc. Encouraging features in research include sentence length and rhythm, intonation, fundamental frequency, and Mel-frequency cepstral coefficients ([MFCCs](https://en.wikipedia.org/wiki/Mel-frequency_cepstrum)).<sup>[2](#references)</sup>


## Inspiration
Inspired by the present Covid Pandemic and some true incidents.

## What it does
This effort addresses an automated device for detecting depression from acoustic features in speech. The tool is aimed at lowering the barrier of entry in seeking help for potential mental illness and supporting medical professionals' diagnoses.

Early detection and treatment of depression is essential in promoting remission, preventing relapse, and reducing the emotional burden of the disease. Current diagnoses are primarily subjective, inconsistent across professionals, and expensive for the individual who may be in dire need of help. Additionally, early signs of depression are difficult to detect and quantify. These early signs have a promising potential to be quantified by machine learning algorithms that could be implemented in a wearable artificial intelligence (AI) or home device.

Automatic Depression Detection (ADD) is a relatively nascent topic that first appeared in 2009. Depression Detect presents a novel approach focusing on two aspects that receive scant research attention: class imbalance and data representation (feature extraction).

It can also play verbal games like “Sing along” in the English language

## How I built it

It is built with an amazon seminarian for the  3d rendering of the digital human. Using python depression dataset was trained convolution neural net.  For audio speech we have used amazon polly and made the chatbot using amazon lex . We have coded on amazon services using AWS LAMDA in python language.

### Segmentation

The first step in analyzing a person's prosodic features of speech is segmenting the person's speech from silence, other speakers, and noise. Fortunately, the participants in the DAIC-WOZ study were wearing close proximity microphones in low noise environments, which allowed for fairly complete segmentation in 84% of interviews using pyAudioAnanlysis' segmentation module. When implementing the algorithm in a wearable device, speaker diarization (speaker identification) and background noise removal would require further development for a more robust product. However, in the interest of quickly establishing a minimum viable product, this desired further development was not addressed in the current effort.

### Feature Extraction 

There are several ways to approach acoustic feature extraction, which is the most critical component to building a successful approach. One method includes extracting short-term and mid-term audio features such as MFCCs, chroma vectors, zero crossing rate, etc. and feeding them as inputs to a Support Vector Machine (SVM) or Random Forest. Since pyAudioAnalysis makes short-term feature extraction fairly streamlined, my first approach to this classification problem involved building short-term feature matrices from 50ms audio segments of the 34 short-term features available from pyAudioAnalysis. Since these features are lower level representations of audio, the concern arises that subtle speech characteristics displayed by depressed individuals would go undetected.

### Running a Random Forest 

on the 34 short-term features yielded an encouraging F1 score of 0.59, with minimal tuning. This approach has been previously employed by others, so I treated this as "baseline" comparative data for which to develop and evaluate a completely new approach involving convolutional neural networks (CNNs) with spectrograms, which I felt could be quite promising and powerful.

### CNNs require a visual image

In this effort, speech stimuli is represented via a spectrogram. A spectrogram is a visual representation of sound, displaying the amplitude of the frequency components of a signal over time. Unlike MFCCs and other transformations that represent lower level features of sound, spectrograms maintain a high level of detail (including the noise, which can present challenges to neural network learning).

## Challenges I ran into
Interfacing Voice recognition along with training gestures and fetching interfacing 3 different services 
was a major issue with the deployment.

## Accomplishments that I'm proud of
Its completeness and innovation.
Overcoming the challenges and deploying successfully is the first thing I am proud of.
Had a great weekend and learned a lot many new things, learning and exploring new stuff for every next second is what I am proud of.

## What I learned

We have burned our nights  to make it successful, we have learned to innovate for the society with the tech we have, 
we learned to build things complete with aws and flask framework.
So finally thanks to snakes and hack we grabbed the following:
Build digital humans
Build human-like digital assistants
Build 3D Chatbots
Amazon Lex
Amazon Polly
Amazon Sumerian
Virtual Personal Assistant Development

## What's next for Digital Human For Anti Depression with Verbal Games
We are thinking to make it more robust and user-friendly so that anyone can use it in their daily life, whose aim was to build an assistant which can help people in their hard times when no one is there for them. We have burned our nights  to make it successful
