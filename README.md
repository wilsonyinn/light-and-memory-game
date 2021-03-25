# Pre-work - *Memory Game*

**Memory Game** is a Light & Sound Memory game to apply for CodePath's SITE Program. 

Submitted by: Wilson Yin

Time spent: 5 hours spent in total

Link to project: https://glitch.com/edit/#!/light-and-memory-game

## Required Functionality

The following **required** functionality is complete:

* [x] Game interface has a heading (h1 tag), a line of body text (p tag), and four buttons that match the demo app
* [x] "Start" button toggles between "Start" and "Stop" when clicked. 
* [x] Game buttons each light up and play a sound when clicked. 
* [x] Computer plays back sequence of clues including sound and visual cue for each button
* [x] Play progresses to the next turn (the user gets the next step in the pattern) after a correct guess. 
* [x] User wins the game after guessing a complete pattern
* [x] User loses the game after an incorrect guess

The following **optional** features are implemented:

* [x] Any HTML page elements (including game buttons) has been styled differently than in the tutorial
* [ ] Buttons use a pitch (frequency) other than the ones in the tutorial
* [x] More than 4 functional game buttons
* [x] Playback speeds up on each turn
* [x] Computer picks a different pattern each time the game is played
* [x] Player only loses after 3 mistakes (instead of on the first mistake)
* [ ] Game button appearance change goes beyond color (e.g. add an image)
* [ ] Game button sound is more complex than a single tone (e.g. an audio file, a chord, a sequence of multiple tones)
* [x] User has a limited amount of time to enter their guess on each turn

The following **additional** features are implemented:

- [x] Graphical display that keeps track of remaining lives
- [x] Graphical display for remaining time on each turn


## Video Walkthrough

Here's a walkthrough of implemented user stories:
![](your-link-here)


## Reflection Questions
1. If you used any outside resources to help complete your submission (websites, books, people, etc) list them here. 
-https://fonts.google.com/
-https://coolors.co/palettes/trending
-https://developer.mozilla.org/en-US/

2. What was a challenge you encountered in creating this submission (be specific)? How did you overcome it? (recommended 200 - 400 words) 
  A challenge that I encountered was implementing a timer for limiting the amount of time to guess on each turn. I started by reading the small hint provided and searched up how to use the setInterval and clearInterval methods on MDN Web Docs. After doing some reading about the two methods, I tried implementing it into my own code. I was able to program the timer to work with ease by writing the function startTimer() which used the setInterval method to continuously decrease the timer by 1000 milliseconds every 1000 milliseconds. This way, every 1000 milliseconds the setInterval method was called, the timer decremented the remaining time by the amount of time that has passed since the last method call. 

  However, I encountered a problem where the timer started ticking the moment the clue sequence started playing. In order to make the timer start, the moment the clue sequence ended, I created an algorithm to account for the amount of delay on each turn since each turn has a different amount of clues playing. The algorithm I used was timerDelay=nextClueWaitTime + (clueHoldTime * (progress + 1)) + (cluePauseTime * progress) where the progress variable represents the index of the pattern array. Since the timerDelay was not always a well rounded number like the timer, I used 1 millisecond for the delay parameter in the setInterval method. However, this created problems as the time was not properly syncing up. I am not certain, but I am assuming this is due to having too many calculations and my computer could not keep up with decrementing the delayTimer by 1 millisecond every millisecond, causing the timer to desync. When I changed the delay parameter for timerDelay to 100 milliseconds and decremented by 100 milliseconds, the problem was solved and the delayTimer synced up properly with the setInterval method. I set my script to immediately start the actual timer to moment the delay timer runs out. As a result, the script for my timer was working properly. 

  The final part was implementing an HTML graphic display so the user can know how much time is remaining. I made this work by writing a print function that uses the inner.HTML method in order to update the remaining time each time the timer was decremented until it hit 0 where the game is over. 


3. What questions about web development do you have after completing your submission? (recommended 100 - 300 words) 
  How could I fix the graphical display for the remaining lives and remaining time? It is set to hidden before the script starts and when it is time to unhide the displays, it creates a new line and the rest of the web page moves down a little which looks clunky. Also, how would I make my remaining lives display update properly? When the third mistake is made, the game over alert pops up before the third heart can disappear. 


4. If you had a few more hours to work on this project, what would you spend them doing (for example: refactoring certain functions, adding additional features, etc). Be specific. (recommended 100 - 300 words) 
  In terms of functionality, I would want the buttons to be disabled while the clues sequence is playing. If a user accidentally presses on the buttons while the clue sequence was currently playing, it could cause confusion as multiple tones would play at the same time. 

  In terms of design, I would like to spend more time making the buttons and font look better. While I do not think the button design and font is very bad, it can always be better. 

  A functionality that I would try to fix is the remaining lives and remaining time graphical displays. I was not able to figure out how to make it hide properly as the webpage would make a new line for the displays when it was time to unhide them. For example, the moment the start button is pressed, the remaining lives display will unhide but a new line is created and the rest of the web page moves down by one line. It looks quite clunky and I am going to look for a solution during my free time because it is bugging me a lot.




## License

    Copyright [Wilson Yin]

    Licensed under the Apache License, Version 2.0 (the "License");
    you may not use this file except in compliance with the License.
    You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing, software
    distributed under the License is distributed on an "AS IS" BASIS,
    WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
    See the License for the specific language governing permissions and
    limitations under the License.