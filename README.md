# SQLSaturday

This repository has been created as the placeholder for the fourth reboot of the SQLSaturday franchise.

## Goals

For now, there are limited goals for this project.

* Provide a website for listing events taking place around the world
* Provide a temporary place for issues related to setting up events.
## Culture

We expect and demand that you follow some basic rules. Nothing dramatic here. There will be a proper code of conduct for the websites added soon, but in this repository

**BE EXCELLENT TO EACH OTHER**

Do I need to say more? 
If your behavior or communication does not fit into this statement, we do not wish for you to help us.

## What can you do?

* We would like you to comment on them and provide help and assistance  
* We have no idea what else is required, that's for you, the community, to decide  

## What this is not

* For profit for any directors or volunteers.

## Event Post

The general structure for an event is to add front matter to a file in _posts. Name this file as follows:

- yyyy-mm-dd-sqlsaturdaynnnn.markdown

nnnn will be the event number, and increment this from the previous events listed. In this file, you add the "front matter" for Jekyll. This is in the following structure:

---
layout: event
title: "event title"
subtitle: ""
tags: [tags comma separated]
comments: false
data: SQLSatnnnn
---

The title should be filled out, a subtitle if you have one, add tags for year, location, country. For data, the nnnn matches the number in the markdown file name. So, for event 1020, this is in the file name and listed as the data file name. The data file is a YAML file and stored in the data/events folder. Entries in that file are described below.
## YAML Documentation

This section has a few notes on how to set up a YAML file for the events. If you don't know YAML, copy an existing file, but remember that whitespace matters. Use a space after colons and enclose entries in quotes if you aren't sure about anything.

Each entry is documented here. If you don't have something for an entry, leave it blank, like this:

googlemapurl: 

The entries are listed below with some notes:

**name**

The title of your event. In general, we are suggesting "SQL Saturday <location> <month> <year>". However, you are free to add or change this slightly if you wish. 

This is rendered at the top of the page.

**logo**

The URL of a logo if you have one for your event. This should be stored in /assets/img/logos as a part of your PR. This is rendered at the top of the page.

**logocredit**

If you have an artist credit for your logo. This is rendered below the logo image.

**date**

Event date in local time. This is rendered as a long string, shown below the images.

**virtual/physical/hybrid**

These are separate entries. You can use true/false for each of these, as apporpriate. The entries will be listed below the description of your event.

**description**

This is the text that you want to include to describe your event. The YAML for this is shown in the [SQLSat1020](/data/events/1020.yml) file is listed like this:

description: |<br/>
    ipsum lorem

The bar allows a multi-line entry, so you can put your text on the lines below, indented. If you want breaks for multiple lines, enter things like this (using _ to represent spaces):

description: |\
____ipsum lorem\

____ipsum lorem

The line break is needed to render these as separate paragraphs.

**officialwebsite**

If you have a separate website for your event, you can enter the URL here. If not, leave this blank. This is rendered below the description, but above the type of event (virtual, hybrid, etc.)

**eventlocation**

This should be the address for your event. If you need multiple lines, format this as the description with a bar for a multi-line listing. If you enter this on consecutive lines, end each with a <br> tag to get a formatted address. As an example:

eventlocation: |
   123 My St<br>
   My rown, my city<br>
   USA

**Countdown Timer** 

I have tested with [https://logwork.com/countdown-timer](https://logwork.com/countdown-timer) as one of the timers. The structure in the YAML file is to set eventcountdown as true if you want this. If you do, then you put the script in the countdownscript: entry. An example is the SQLSat1020.yml file.

**registrationurl**

URL for your registration service. This should include the "https://". This value is used as the target for the registration button. 

**eventbriteembed**

If this is included as the iframe code, this is rendered instead of the registration button.

**capacity**

This value is printed after the text "The capacity limit for this event is". You can include a numeric value or "unlimited", "uncapped", or anything.

**googlemapurl:**

A URL to a map URL for your event location. We render this in the Location section, as part of an iframe that is 600x450. This would be the src value in that iframe. This has been tested with Google Maps.

**scheduleurl**

This is the URL from Sessionize for the schedule. This is part of an iFRAME, as the src part of the SRCDOC element.

**join**

This is the top level section for your virtual links. The subtags are listed below as join.description and join.rooms.

**join.description**

This is the text that is printed below the "Rooms" heading. Enter any text you want attendees to see for this tag.

**join.rooms**

This is the subtag for your rooms. Below this tag is an array of rooms. Each takes a name and a URL. The name is used to render a button. The URL is the target of the button. The structure of this tag is the first line below rooms: starts with a hyphen, space, then name:. Indent the subsequent url: entry to the same level as name. An example is (underscores used spaces here):

join:\
__description: Click on the room you want to join. You can change room at any time to attend the sessions that you prefer.\
__rooms:\
____- name: First
______url: https://www.youtube.com/results?search_query=first
____- name: Second
______url: https://www.youtube.com/results?search_query=second

**speakertext**

This is text that you want shown under the Speakers heading. Leave blank if you don't want anything.

**speakerlisturl**

This is the sessionize (or other) call for speakers URL. This is used for the target of the submit a session button.

**callforspeakers**

If true, the submission button is shown. If false, the button is not shown and the text displays the call for speakers is closed.

**callforspeakersenddate**

Date on which the call for speakers ends.