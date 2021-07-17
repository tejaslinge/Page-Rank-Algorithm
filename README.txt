Simple Python Search Spider, Page Ranker, and Visualizer

This is a set of programs that emulate some of the functions of a 
search engine.  They store their data in a SQLITE3 database named
'spider.sqlite'.  This file can be removed at any time to restart the
process.   

This program(spider_webpages.py) crawls a web site and pulls a series of pages into the
database, recording the links between pages.

Enter web url or enter: ['http://www.google.com']
How many pages:2
143 https://www.google.com/drive/download (40210) 15
41 https://www.google.com/about/philosophy.html (31145) 15
How many pages:

In this sample run, we told it to crawl a website and retrieve two 
pages.  If you restart the program again and tell it to crawl more
pages, it will not re-crawl any pages already in the database.  Upon 
restart it goes to a random non-crawled page and starts there.  So 
each successive run of spider_webpages.py is additive.

You can have multiple starting points in the same database - 
within the program these are called "webs". The spider
chooses randomly amongst all non-visited links across all
the webs.

If you want to dump the contents of the spider.sqlite file, you can 
run spider_dump.py.

Once you have a few pages in the database, you can run Page Rank on the
pages using the spider_rank.py program.  You simply tell it how many Page
Rank iterations to run.

You can dump the database again to see that page rank has been updated.

You can run spider_rank.py as many times as you like and it will simply refine
the page rank the more times you run it. 

If you want to visualize the current top pages in terms of page rank,
run spider_json.py to write the pages out in JSON format to be viewed in a
web browser.

You can view this data by opening the file force.html in your web browser.  
This shows an automatic layout of the nodes and links.  You can click and 
drag any node and you can also double click on a node to find the URL
that is represented by the node.

