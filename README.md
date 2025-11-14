# Visualizing viewership for TV shows released from 2019-2021

## Update 2025
I have implemented a ETL and ML pipeline with the data collected for The Mandalorian (2019).

The pipeline transforms raw JSON data into an ML-ready format, equipping Natural Language Processing (NLP) with spaCy for efficient cleaning, tokenization, and lemmatization. The cleaned data is represented in a Pandas dataframe with three columns, content (pre-processed tweets), tokens (tweet tokens) and strings (lemmatized tweets). 

<img width="1059" height="273" alt="image" src="https://github.com/user-attachments/assets/8019c835-0ba2-419c-9339-e66fe217f814" />

The cleaned data then feeds into a topic model built with Gensim and visualized through PyLDAVis. Available here: https://tinyurl.com/sheatoo

Further analysis incorporating n-grams, top-n words, and hyperparameter tuning is pending.

Jupyter Notebook: [code/mandalorian-topic-model.ipynb](https://github.com/sheatoo/viewership-analysis/blob/daa3f5c58e1ae509300f3e0619bb1fc11b8f32db/code/mandalorian-topic-model.ipynb)   

# Original Content
## Findings: [Nunn, Alistair_417 project report.pdf](https://github.com/chippedtoe/project417/blob/0e1f77568519b8edd7f3060bda3b89e47efc3a0a/Nunn%2C%20Alistair_417%20project%20report.pdf)

## Scope
Due to Covid-19, people worldwide spend more time in their homes than ever. Quarantine mandates were issued to contain the virus, forcing many people to stay at home, whose impacts can be seen in the decrease in media production over the past year. According to a report by FX, the number of scripted TV shows in 2020 was 496, a 7% decrease from 2019.

The purpose of this project is to understand the impact of these phenomena on the popularity of TV shows released during the pandemic. According to an article published by Forbes, the number of subscribers for streaming services jumped to 308.6 Million in 2020 - a 32% increase from the year before (Agate, 2021). From this, it would be easy to assume that the overall popularity
would increase, but what does this mean for popularity over time?

It’s often been noted that the public eye is always moving, people jump from topic to topic quickly, and what’s popular today won’t necessarily be popular tomorrow. I wondered if this would as much of the population was stuck at home, and in 2021, many people still worked and attended school from home. My hypothesis is that due to production decreases and quarantine measures, tv shows would remain popular for longer, as there were less things to discuss overall.

## Methods
To test my hypothesis, I needed to examine viewer engagement with TV shows during the onset of COVID-19. For this purpose, I set out to examine a set of TV shows produced from 2019 to 2021. To determine which shows to include in my analysis, I referenced articles about the most popular shows released from 2019 and selected those that were referenced the most. The shows I chose to survey were: _Umbrella Academy_(2019), _The Mandalorian_ (2019), and _The Queen’s Gambit_ (2020). To build a timeline of viewer engagement, I used snscraper to collect tweets about each show starting from the month of its original release date. Overall engagement can be seen through the number of tweets about each show per day.

## Results
For analysis purposes, only the columns containing the tweet ID, date created, tweet content, geographical location, and hashtags were included. From this, a time-series plot was created using the content (tweet) counts for each day within the collection timeframe, and the initial release dates were marked. The number of tweets collected for each show was: _The Mandalorian_ (2019): 844,956; _The Queen’s Gambit_ (2020): 357,913; _Umbrella Academy_ (2019): 575,126.

It’s important to note that for Figures 1 and  2, the time series spans up to 5 months after the original release date, while the time span for Figure 2 is up to a year.

As you can see, the shows had varying levels of engagement, demonstrated by the maximum tweets per day for each series. The maximum for The Mandalorian is over 40,000 tweets, while Umbrella Academy and Queen’s Gambit have 20,000 and 7,000, respectively. This means that of the three surveyed, The Mandalorian is by far the most popular and had the greatest amount of engagement.

Figure 1: _The Mandalorian_ (2019) number of tweets per day
<img width="812" height="459" alt="image" src="https://github.com/user-attachments/assets/f984107f-c68d-4373-bdd0-a1101efba4eb" />

As seen in Figure 1, the greatest number of tweets were tweeted on the initial release date, with small spikes in engagement leading up to the last episode, which had a volume of tweets more similar to the release date. However, following the last episode, the number of tweets per day dropped significantly and leveled out just after the end of January.

Taking a closer look, it was found that the average number of tweets per day in February 2020 was just around 36. Though given that the second season of the show was released in late 2020, similar results to those shown leading up to the first season are expected.

Looking at the graph alone, engagement for The Mandalorian seems in line with what would be expected before Covid-19, with most of the engagement occurring during the show run and dropping during the off-seasons.

Figure 2: _Umbrella Academy_(2019) number of tweets per day
<img width="828" height="460" alt="image" src="https://github.com/user-attachments/assets/70d397ac-db33-4df0-b9a0-524ad91cfc8d" />

Similarly to Figure 1, Umbrella Academy had the highest engagement closer to its original release date, but engagement drops exponentially over the next 3 months. This can be explained by the fact that both Umbrella Academy and The Queen’s Gambit are produced by Netflix, which releases the episodes all at once, while The Mandalorian is distributed by Disney, which releases episodes on a weekly schedule. 

Since this show was released pre-COVID, it makes sense that it has less engagement as time goes on, but there is a spike in April 2019, which would be interesting to examine later. Overall, I believe the results from this show would be a good benchmark for normal engagement, and it would be interesting to compare with engagement for the second season, which was released in the summer of 2020.

Figure 3: _The Queen's Gambit_ (2020) number of tweets per day
<img width="845" height="476" alt="image" src="https://github.com/user-attachments/assets/63b47e92-0749-422f-aeb0-1d674a8ebcc8" />

Unlike the other shows surveyed, _The Queen’s Gambit_ (2020) - released in late October of 2020 - had the highest engagement a month after its initial release. It shows similar results to Umbrella Academy in that there is continuous engagement for the first couple of months after its release, with numbers dipping as time goes on.

Two interesting spikes occurred in January and February of 2021. From the data, it was found that during February, many people tweeted using the hashtag _#GoldenGlobes_ for which the show was nominated and won two awards. The spike from January of the same year was found to be attributed to normal viewership.

## Conclusion
From my results, I was unable to determine whether COVID impacted TV show popularity over time. All shows surveyed had high engagement around their initial release, with lower engagement in the following months. Future research would benefit from including subsequent seasons and comparing engagement within and across shows during the height of COVID (spring to summer 2020).

Further analysis in topic modeling would lend more information as to what people are discussing about each show, and using the geo-location of each tweet could give insight into worldwide popularity. 

## References
1. Agate, B. (2021, April 13).The Impact COVID-19 Had On The Entertainment Industry In
2020. Forbes. Retrieved from
https://www.forbes.com/sites/bradadgate/2021/04/13/the-impact-covid-19-had-on-th
e-entertainment-industry-in-2020/
2. Beck, M. (2021, February). How to Scrape Tweets With snscrape. Medium. Retrieved
from
https://betterprogramming.pub/how-to-scrape-tweets-with-snscrape-90124ed006afn
3. Diaz, G. (2019). Stopwords ISO. Github Repository. Retrieved from
https://github.com/stopwords-iso/stopwords-iso
4. Feldman, Dana. (2020, December 8). Here Are The 10 Most-Watched Netflix Original
And Limited Series Of 2020. Forbes. Retrieved from
https://www.forbes.com/sites/danafeldman/2020/12/08/here-are-the-10-most-watche
d-netflix-original-and-limited-series-of-2020/
5. “V. Kindratenko, D. Mu, Y. Zhan, J. Maloney, S. Hashemi, B. Rabe, K. Xu, R. Campbell,
J. Peng, and W. Gropp. (2020, July). HAL: Computer System for Scalable Deep
Learning. In Practice and Experience in Advanced Research Computing (PEARC
’20), July 26–30, 2020. https://doi.org/10.1145/3311790.3396649”.
6. Richwine,L., Coster, H. (2020, October 13). Analysis: Fewer movies in theaters? Big
Media turns focus to streaming video. Reuters. Retrieved from
https://www.reuters.com/article/walt-disney-restructuring-streaming/analysis-fewer-m
ovies-in-theaters-big-media-turns-focus-to-streaming-video-idUSKBN26Z09E
7. Zhu, Z.(2021). Text Analysis in Foreign Languages. Medium. Retrieved from
https://towardsdatascience.com/text-analysis-in-foreign-languages-b952d7de3f41
