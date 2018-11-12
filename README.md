# akinator-api
[![npm version](https://badge.fury.io/js/akinator-api.svg)](https://badge.fury.io/js/akinator-api)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)

# WARN
## This project is now depreciated and is not being updated due to changes on Akinator's end. If I have time I will rewrite the code.

An api built to interact with Akinator based in NodeJS.

This package has many features that you may use to interact with the Akinator api.
Below you will find information on how to install the package + the package's features.
This package supports 15 different languages.

## Requirements
| Requirement | Version |
| ---|---|
| Node | ^8.8.0 |
| NPM | ^5.5.1 |


## Installation

``npm i akinator-api``


## Usage

### Region/Language List
us - English<br>
de - German<br>
fr - French<br>
in - Hindi<br>
es - Spanish<br>
cn - Chinese<br>
ar - Arabic<br>
il - Hebrew<br>
it - Italian<br>
jp - Japanese<br>
kr - Korean<br>
nl - Dutch<br>
pl - Polish<br>
pt - Portuguese<br>
ru - Russian<br>
tr - Turkish

### Start A Game

#### Sample JSON Response

```json
{  
   "session":"20",
   "signature":"793609611",
   "question":"Is your character's gender female?",
   "answers":[  
      "0 - Yes",
      "1 - No",
      "2 - Don't know",
      "3 - Probably",
      "4 - Probably not"
   ]
}
```

#### Example Code for Start

```js
const api = require('akinator-api');

api.start(region, (gamedata, error) => {
  if (error) {
    console.log(error);
  } else {
    console.log(gamedata);
  }
})
```

### Answer a Question

#### Sample JSON Response

```json
{  
   "nextquestion":"Is your character a youtuber?",
   "progress":"2.05700",
   "answers":[  
      "0 - Yes",
      "1 - No",
      "2 - Don't know",
      "3 - Probably",
      "4 - Probably not"
   ]
}
```

#### Example Code for Answer

```js
const api = require('akinator-api');

api.answer(region, session, signature, answerid, step, (next, error) => {
  if (error) {

  } else {
    console.log(next);
    step++;
  }
})
```

## TODO

1. Completion Detection
