# Online-BookStore-Promotion-Response
Predict the response to an online bookstore promotional activity

## Business Situation: 
A German online book seller has provided data on a sample of 33,713
customers on their purchases of books prior to 01AUG2014 when a promotional offer was
made and their purchase amounts (targamt) in euros over the next 3 months in response
to the offer. The total sample of 33,713 customers is divided into a training sample of 8,311
customers and a test sample 25,402 customers. The goal of the project is to build a predictive
model for targamt based on the predictor variables from the past purchase history and use the
model to predict targamt for the test sample customers. The response rates (proportion of
customers with targamt > 0, i.e., who bought a book) are 327/8311 = 3.93% in the training
sample and also 999/25,402 = 3.93% in the test sample. Note that targamt is log-transformed
as logtargamt = ln(targamt+1), so that if targamt = 0 then logtargamt is also 0.

## Data: 
There are a four data tables which can be matched by common customer id's.

1. book.csv : This is the most extensive data table with the following data on all 33,713
customers:
* id: unique customer id
* logtargamt: blank for the test sample
* recency: no. of days since the last order
* frequency: number of orders
* amount: total past purchase amount in euros (not sure why all purchase amounts and
* prices are reported to many decimal places)
* tof: time on file
* Fxx: frequency of orders of books of category xx
* Mxx: amount of purchase of books of category xx

The following are the categories : 1=Action, 3=classics, 5=cartoons, 6=legends, 7=phi-
losophy, 8=religion, 9=psychology, 10=linguistics, 12=art, 14=music, 17=art reprints,
19=history, 20=contemporary history, 21=economy, 22=politics, 23=science, 26=com-
puter science, 27=traffic, railroads, 30=maps, 31=travel guides, 35=health, 36=cooking,
37=learning, 38=games and riddles, 39=sports, 40=hobbies, 41=nature/animals/plants,
44=encyclopedias, 50=videos, DVDs, 99=non-books
      
2. ordersall.csv table: This table contains data on all 627,955 orders, which translates to an
average of 18.45 orders per customer. The data fields are as follows.
* id: unique customer id
* orddate: order date
* ordnum: order number
* category: category of the book
* qty: quantity ordered
* price: price

3. booktrain.csv: This table has only two variables: id and logtargamt for 8,311 customers
in the training set

4. booktest.csv: This le also has only two variables: id and logtargamt for 25,402
customers in the test set.
