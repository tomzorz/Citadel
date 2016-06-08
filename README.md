# Citadel
a customizable self-hosted homepage built with asp.net core

## My current plans

* three built-in main modules
  * speed dial
    * two main features
    * #1: links in categories
    * #2: "goto console" that supports custom search engines, website shortcuts or anything you want
    * links have: name, color, icon (optional), url, weight (for ordering)
    * categories have: name, color, list of links, weight (for ordering)
    * "goto console" entries have: name, shorthand, parameterized url
    * the "goto console" can also open urls directly if you type '.' first
  * bookmarks
    * these have: name, url, description (optional), date of addition, tags (optional)
    * two extra (non-implicit) features
    * #1: quick way to add a bookmark (browser toolbar js button?)
    * #2: quick way to sort + tag uncategorized bookmarks
  * frame
    * this is to embed things like rss readers, GTD tools etc...
    * I don't want to implement a bunch of 3rd party APIs, so this seems like an easy solution
    * maybe css injection and other things could come in handy here
* auth
  * for one user or multiple
  * could be disabled, or limited to editing only
  * content is same for all users
* ability to add custom modules (I might do a sample for github stars, or reddit saved posts)
* API first design, so clients can be easily built if needed
  * maybe expose some sort of bot api after 1.0 as that's going to be all the rage later 
* "principle of the single http call": load a heavily cached static site so it's fast (yeah I just made that principle up, but you get the jist)
  * to clarify a bit: a single call to the speed dial page should get all the content (including js, css and html) in one pass - I don't want to see browser redraws, or any JS running on the page (maybe analytics, but that could be done with redirects as well)
  * JS is fine in edit more
* sqlite db
  * but maybe abstract that away so someone could change it around later if needed 

## Some sketches

Speed Dial
![speed dial](https://raw.githubusercontent.com/tomzorz/Citadel/master/plans/1.jpg)

Bookmarks
![bookmarks](https://raw.githubusercontent.com/tomzorz/Citadel/master/plans/2.jpg)

Speed dial edit
![speed dial edit](https://raw.githubusercontent.com/tomzorz/Citadel/master/plans/3.jpg)
