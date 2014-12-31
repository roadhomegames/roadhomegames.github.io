---
title: Designing the Net Detective Interface
date: 2014-12-27
---
I am not a graphic designer, but I had to design the interface for my game Net Detective. I don't know of any games that play like it, so it had to be an original design. This is the story of how I arrived at what came to be the final design for the game's interface.

I wanted the look of the game to suggest refrigerator magnets being moved around the surface of a fridge. There are lots of videos on Youtube of stop motion films showing this sort of look in action. For example:

<iframe width="560" height="315" src="//www.youtube.com/embed/44eudz2MdBE" frameborder="0" allowfullscreen></iframe>

When I was prototyping the game in its early stages, the game had a look closer to the one showed in the video above. It wasn't stop-motion because I discovered pretty quickly that the effect of my attempts at emulating stop-motion in-game mostly induced nausea and did not produce the playful feel you get when watching the Youtube videos.

So I wrote a bunch of code to pack and move magnets around a board. I wrote code to pack them end-to-end in lines I called "shelves", to pack them in 2D bounding boxes (I used a heuristic approach because 2D bin-packing is an <a href="http://en.wikipedia.org/wiki/Bin_packing_problem">NP-hard problem</a> and I had to solve the packing in the space of a single frame to not destroy the frame-rate). Then I wrote code to move magnets around a flat board, using Unity's physics engine and attaching each magnet or group of magnets to invisible springs so that they moved in a visually pleasing manner. Moving the magnets around so they didn't crash into each other and/or clip through each other was a tricky problem.

I was able to get a prototype out of this pretty rapidly, and it ended up looking like this:

<iframe width="560" height="315" src="//www.youtube.com/embed/m7HEmJvEWww" frameborder="0" allowfullscreen></iframe>

People had fun playing this version of the game, but it suffered from some serious usability problems. Everything was too small! Playing on a mobile device, the text could sometimes be a little difficult to read (particularly on older devices) and tapping on a piece of the interface to select it was really difficult, particularly for players with large fingers. The interface was very difficult to use for anybody more than about 10 years old. So I went back to the drawing board.

I don't really use smartphones. This is a problem for someone making a game designed to be played on smartphones. That may be why my initial design incorporated such a fundamental mistake. So in designing the update, I was inspired by an old story about the design of the original Palm Pilot back when I worked at Palm. They would tell all their new employees the story of how company founder Jeff Hawkins cut out a block of wood in the shape of the device and carried it around for months in his pocket before the device actually existed. It turns out this is a somewhat famous example of something called <a href="http://pretotyping.blogspot.com/2010/08/one-of-my-favorite-pretotype-stories.html">pretotyping</a>. Well, I don't have a woodshop, but I do have plenty of empty cereal boxes and access to Elmer's glue, so I decided I would make my own physical interface models to play with. I needed to make an interface that would work properly on small old devices and scale up to the big new devices with giant screens, but couldn't afford to buy all these devices to test on. So I made a bunch of cardboard cutouts that look like this:

<a href="/images/Cardboard1.jpg"><img class="size-medium wp-image-103" alt="Front of device" src="/images/Cardboard1.jpg" width="300" height="156" /></a> Front of cardboard "device"

<a href="/images/Cardboard21.jpg"><img class="size-medium wp-image-104" alt="Screen grid" src="/images/Cardboard21.jpg" width="300" height="198" /></a> Screen grid

<a href="/images/Cardboard3.jpg"><img class="size-medium wp-image-105" alt="Rear showing description" src="/images/Cardboard3.jpg" width="156" height="300" /></a> Rear showing description

I used these cardboard cutouts so I could have something to hold in my hands and feel and tap and swipe to get a sense for how much information I could pack onto a screen before it became too cramped to easily read and touch. I came up with the sizing for the partitions in the grid image above based on the size of home-screen icons on the iPhone4, figuring Apple had done lots of usability testing to ensure icons of this size were pleasing to interact with.

At the same time I was doing this, I was reading a bunch of books about typography and layout (most of them were written before the term "graphic design" was invented) such as <a href="http://www.amazon.com/The-New-Typography-Weimar-Now/dp/0520250125/">The New Typography</a>,  <a href="http://www.amazon.com/The-Art-Color-Subjective-Experience/dp/0442240376/">The Art of Color</a>, and <a href="http://www.amazon.com/Interaction-Color-Revised-Expanded-Edition/dp/0300115954/">The Interaction of Color</a>. These works also influenced my design choices, and help explain things like why the list of word choices on the left side of the gameplay screen are tilted at a 10-degree angle.

My goals in the updated interface were that interface elements be very usable and have a tactile feeling and sense of depth. I made the decision to step away from displaying all elements of the interface simultaneously, so players would now switch between choosing available clues and solving words on the left side of the screen.

Here are shots of some of the various phases of the new interface over the course of development:

<a href="/images/Screenshot1.png"><img class="aligncenter size-medium wp-image-107" alt="Screenshot1" src="/images/Screenshot1.png" width="300" height="180" /></a> <a href="/images/Screenshot.png"><img class="aligncenter size-medium wp-image-108" alt="Screenshot" src="/images/Screenshot.png" width="300" height="179" /></a>And after going through numerous iterations and doing a bunch of playtesting, I wound up with the interface you can see in the final game:

<iframe width="560" height="315" src="//www.youtube.com/embed/errFp7kuI0k" frameborder="0" allowfullscreen></iframe>

In retrospect, the new interface has problems too. One issue is that players wind up not looking for clues as often as I would like because it takes an action to switch over to the clues list from the word choice list. Another issue is that not everyone is sure which pieces of the interface are interactive and which aren't. I feel like it also traded some of the charm the fridge magnet design had in favor of improvements in usability. Overall, I definitely learned a lot by going through the design process.
