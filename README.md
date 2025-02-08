# INaturalist API Observation Data Scraper
This notebook contains a scraper for retrieving data from the [iNaturalist API](https://www.inaturalist.org/pages/api+reference). The scraper collects observations based on user-specified parameters, such as species names, location, or media types (photos, sounds, etc.).

This script utilizes the "window" method of requesting data from the API. Due to INaturalist's limit of 10,000 observations per request, you must first tailor your parameters to fetch no more than 10,000 results per each request. You should not alter the request rate to fetch more than 60 times per minute, and should also not request more than 10,000 times per day (though difficult). Download capacity (monitored by the program) is capped at 5GB per hour, and no more than 24GB per day per INaturalist's usage policy. If you start and stop this program rather than running it once per day, be sure to monitor your total data usage manually. Should an error occur, your data will automatically be saved.

This program works to scrape together data through incremental search "windows" of all possible id numbers, compiling and formatting the data as necessary into a .csv format. It has a timer and data meter to prevent exceeding the download limit policy, and thus can be run in the background over the course of however long it will take. For example, processing 700k observations may take several days. Multiple IP's/proxies/VPN's can allow you to do this much faster, however that is a violation of the usage policy. 

Note: INaturalist's API is not intended for data scraping. While this script complies with their policies, I cannot condone its usage. I created this program for educational and proof of concept purposes. This script is especially intended to retrieve information that is unavailable through their formal data export tool, and can be used to collect more data than their data export tool allows (given enough time). Be sure to include appropriate attributions when using photos copyrighted under the Creative Commons License.<br>
<a href="https://www.inaturalist.org/pages/api+recommended+practices">INaturalist's API recommended practices</a> <br>
<a href="https://www.inaturalist.org/observations/export">INaturalist's formal data export tool</a>


<H2>Features:</h2>
<ul>
<p>-Fetches observations from Inaturalist based on configurable parameters</p>
<p>-Filters observation data according to a configurable field list</p>
<p>-Handles data issues of the currently pressent fields</p>
<p>-Fully complies with Inaturalist's API use and data downloading policy</p>
<p>-Saves results to CSV for further analysis</p>
</ul>

<H2>Prerequisites:</h2>
<ul>
<p>-Python 3.12 and the following libraries:</p>
    <ul>
        <p>-requests</p>
        <p>-pandas</p>
        <p>-time</p>
        <p>-json</p>
        <p>-math</p>
        <p>-os</p>
        <p>-datetime</p>
    </ul>
</ul>
Launch in your favorite IDE or Colab to begin.<br>
Feel free to email me with any questions or concerns: jweil@ucsd.edu
