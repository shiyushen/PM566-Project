Midterm-Report
================

## 1 Introduction

### 1.1 Backgroud

When talking about 2020, “COVID-19”, a novel coronavirus firstly found
in Wuhan, China, in the end of 2019 (Mclntosh, 2020), must be the most
popular word that appears on the Internet, newspapers and daily
conversations. Since COVID-19 has been discovered and claimed as human
pandemic by Chinese government, there are more than 36 millions of
people being confirmed with COVID-19 and about 1 million deaths by now
(2020). COVID-19 is definitely raising a huge concern of public health
around the world.

### 1.2 Problem Statement

There are many opinions about the origin of COVID-19. Some suggests that
the sequence of COVID-19 is similar to bat virus (Shin, 2020), while
others do not support that idea. There are also many unclear
characteristics about this new virus. Therefore, this report will mainly
focus on discovering main and critical characteristics of COVID-19,
including incubation period, COVID-19 distribution of age, gender.

### 1.3 Data Discription

This data is obtained from Kaggle: Novel Corona Virus 2019 Data set.
These COVID-19 case data are collected from 20th January to 28th
February, 2020, which is the early pandemic period of COVID-19. This
data set consists of 10 qualitative attributes, 7 quantitative
attributes and 3 other attributes (Table1.1).

<table>

<caption>

Table1.1 Description of COVID-19 data set

</caption>

<thead>

<tr>

<th style="text-align:left;">

Variable Name

</th>

<th style="text-align:left;">

Discription

</th>

</tr>

</thead>

<tbody>

<tr>

<td style="text-align:left;">

id

</td>

<td style="text-align:left;">

Patient ID

</td>

</tr>

<tr>

<td style="text-align:left;">

case\_in\_county

</td>

<td style="text-align:left;">

Number of case in county

</td>

</tr>

<tr>

<td style="text-align:left;">

reporting date

</td>

<td style="text-align:left;">

Case reporting date

</td>

</tr>

<tr>

<td style="text-align:left;">

summary

</td>

<td style="text-align:left;">

Patient summary discription

</td>

</tr>

<tr>

<td style="text-align:left;">

location

</td>

<td style="text-align:left;">

Location

</td>

</tr>

<tr>

<td style="text-align:left;">

country

</td>

<td style="text-align:left;">

Country

</td>

</tr>

<tr>

<td style="text-align:left;">

gender

</td>

<td style="text-align:left;">

Gender

</td>

</tr>

<tr>

<td style="text-align:left;">

age

</td>

<td style="text-align:left;">

Age

</td>

</tr>

<tr>

<td style="text-align:left;">

sympton\_onset

</td>

<td style="text-align:left;">

Sympton onset date

</td>

</tr>

<tr>

<td style="text-align:left;">

if\_onset\_approximated

</td>

<td style="text-align:left;">

Whether symptom onset is approximated

</td>

</tr>

<tr>

<td style="text-align:left;">

hosp\_visit\_date

</td>

<td style="text-align:left;">

hospotal visiting date

</td>

</tr>

<tr>

<td style="text-align:left;">

exposure\_start

</td>

<td style="text-align:left;">

Exposure start date

</td>

</tr>

<tr>

<td style="text-align:left;">

exposure\_end

</td>

<td style="text-align:left;">

Exposure end date

</td>

</tr>

<tr>

<td style="text-align:left;">

visiting Wuhan

</td>

<td style="text-align:left;">

Whether the patient visted Wuhan

</td>

</tr>

<tr>

<td style="text-align:left;">

from Wuhan

</td>

<td style="text-align:left;">

Whether the patient is from Wuhan

</td>

</tr>

<tr>

<td style="text-align:left;">

death

</td>

<td style="text-align:left;">

Whether the patient died

</td>

</tr>

<tr>

<td style="text-align:left;">

recovered

</td>

<td style="text-align:left;">

Whether the patient recovered

</td>

</tr>

<tr>

<td style="text-align:left;">

symptom

</td>

<td style="text-align:left;">

Symptom

</td>

</tr>

<tr>

<td style="text-align:left;">

source

</td>

<td style="text-align:left;">

Source of the patient’s information

</td>

</tr>

<tr>

<td style="text-align:left;">

link

</td>

<td style="text-align:left;">

Source link

</td>

</tr>

</tbody>

</table>

## 2 Methodology

The data set that is used in this report is downloaded from a Kaggle
page. It offers day-level information and data set on COVID-19 affected
cases. First, basic statistics of variables will be computed. Second,
basic plots, for instance, box plot, line plot and histograms will be
drawn to give ideas of how each variables are distributed. Then, missing
value will be evaluated and necessary substitution or deletion of
missing value will be used for each variables. Specifically, the
following method will be used to deal with specific variable:

1.  If a row has all NA in most of the columns, it will be deleted;

2.  Missing values in “location”, “gender” and “country” will not be
    imputed;

3.  Missing values in “age” will be generated using the mean of “age”;

4.  Missing values in “hosp visit date” will be imputed by it’s
    “reporting date”;

5.  Missing value in “symptom onset date” will be imputed by the average
    of the difference between “symptom onset data” and “hosp visit
    date”;

6.  Missing value in “exposure start data” will be imputed by the
    average of the difference between “exposure start data” and “symptom
    onset date”;

7.  Missing value in “exposure end data” will be imputed by “hosp visit
    data”.

8.  Missing value in “symptoms” will be imputed by the most frequent
    symptoms.

In the later steps, time-series plot of COVID-19 cases will be drawn to
see how the case number increases by time. Age-specific,
gender-specific, country-specific confirm rate will be compared.

## 3 Results

In the beginning, 3 descriptive variables “summary”, “source” and “link”
will be excluded and the main data set will have 17 variables and 1085
observations.The following table listed some descriptive statistics
about main variables in COVID-19 data set.

<table>

<caption>

Table3.1 Descriptive statistics of main variables in COVID-19 data set

</caption>

<thead>

<tr>

<th style="text-align:left;">

Variable Name

</th>

<th style="text-align:left;">

Obs/frequency

</th>

<th style="text-align:left;">

\#NA

</th>

</tr>

</thead>

<tbody>

<tr>

<td style="text-align:left;">

country

</td>

<td style="text-align:left;">

38 countries

</td>

<td style="text-align:left;">

183

</td>

</tr>

<tr>

<td style="text-align:left;">

gender

</td>

<td style="text-align:left;">

F/M=382/520

</td>

<td style="text-align:left;">

242

</td>

</tr>

<tr>

<td style="text-align:left;">

age

</td>

<td style="text-align:left;">

Min:25 Max:96 Mean:49.48

</td>

<td style="text-align:left;">

222

</td>

</tr>

<tr>

<td style="text-align:left;">

if\_onset\_approximated

</td>

<td style="text-align:left;">

Yes:24 No:536

</td>

<td style="text-align:left;">

577

</td>

</tr>

<tr>

<td style="text-align:left;">

visiting Wuhan

</td>

<td style="text-align:left;">

Yes:192 No 893

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;">

from Wuhan

</td>

<td style="text-align:left;">

Yes:156 No:925

</td>

<td style="text-align:left;">

4

</td>

</tr>

<tr>

<td style="text-align:left;">

death

</td>

<td style="text-align:left;">

Yes:63, No:1022

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;">

recovered

</td>

<td style="text-align:left;">

Yes:159 No:926

</td>

<td style="text-align:left;">

</td>

</tr>

<tr>

<td style="text-align:left;">

symptom

</td>

<td style="text-align:left;">

</td>

<td style="text-align:left;">

815

</td>

</tr>

</tbody>

</table>

In order to avoid problems when analyzing sparse data set, different
methods of imputing missing values were used to deal with variables
individually.

1.  When checking the missing values in “reporting data”, we found that
    262 row has all other attributes equal to “NA”. Thus the 262th row
    is deleted.

2.  The mean of age is around 49 (Fig3.2). Thus 49 is used for imputing
    the missing values in “age” .

![](README_files/figure-gfm/unnamed-chunk-5-1.png)<!-- -->

3.  The mean difference between hospital visiting date and symptom onset
    date is 4 (Fig3.3). Then, the missing value in “symptom\_onset” is
    substitute by “hosp\_visit\_date” plus 4 days.

![](README_files/figure-gfm/unnamed-chunk-6-1.png)<!-- -->

4.  The mean difference between exposure start date and symptom onset
    date is 12 (Fig3.3). Then, the missing values in “exposure start”
    are imputed by “symptom onset” minus 12 days.

![](README_files/figure-gfm/unnamed-chunk-7-1.png)<!-- -->

5.  By computing the frequency for the main symptoms, it is easy to find
    that “fever” is the most common symptom that shows among COVID-19
    cases (Table3). Thus, the missing values in “symptom” are imputed by
    “fever”.

6.  The difference in numbers infected cases between male and female can
    be seen in Fig3.5. We can see that there are more males than females
    who are confirmed with COVID-19.

![](README_files/figure-gfm/unnamed-chunk-8-1.png)<!-- -->

## Conclusion

First, by computing the mean age of patient, we can see that most of the
confirmed cases are around 49 years old, which can be explained by the
reason that older people tend to be more infected by virus. Then, we
found that the difference between the date of exposure and date of
symptom onset is around 14 days. This results is consistent with the
claimed incubation period of COVID-19. Third, fever is the most frequent
symptom that shows up on the confirmed cases. It is why fever is
concerned as official symptom of COVID-19. Even though there are
difference in confirm numbers between gender, the there is not enough
evidence show that the infected rate is difference between Male and
Female. However, this COVID-19 data is only collected in the early
period of the pandemic, which is not enough to draw conclusion outside
this data set. Thus, more statistical tests should be done and a updated
data set is required in future steps.

## Reference

<https://www.uptodate.com/contents/coronavirus-disease-2019-covid-19-epidemiology-v>

irology-and-prevention

<https://medium.com/microbial-instincts/the-latest-theory-that-may-answer-the-origin-of-covid-19-d9efbe7072ae>

View
[here](https://ghcdn.rawgit.org/shiyushen/PM566-Project/master/Midterm.html)
