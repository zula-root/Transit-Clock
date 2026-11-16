# Transit Clock

A clock made of timetables. Every minute it shows a real train, ferry or bus
that is timetabled to leave at exactly that minute, somewhere in the world.

> The **7:12 a.m.** Nozomi leaves Tokyo for Hakata.
>
> *It reaches Hakata at 12:09 p.m., 4 hours and 57 minutes later.*

**Live:** https://zula-root.github.io/Transit-Clock/

![The Transit Clock on a phone folded into a tent on a desk, showing the 7:12 a.m. Nozomi from Tokyo](docs/duo-stand.jpg)

*The clock's stand face on a folded iPhone Duo. A rendering, not a photograph.*

Every minute is somebody's train. There are 9,995 departures in the data, and
all 1,440 minutes of the day have at least six.

## Where the idea comes from

The [literary clock](https://literature-clock.jenevoldsen.com/) tells the time
with sentences from novels: at 4:12 you read a line of fiction that happens to
mention 4:12. It began in 2011, when the Guardian asked its readers to send in
quotations. Jaap Meijers put the list on an old Kindle, and Johannes
Enevoldsen made the web version.

A timetable turns out to be full of sentences too. "The 4:12" is already how
people name a train they mean to catch. This clock takes that literally.

## How to read it

![The whole page on the same phone opened like a book: the sentence, the route and the map](docs/duo.jpg)

*The whole page, on the same phone opened like a book. Also a rendering.*

- **The line above the sentence** says what the clock is and which train this
  is: "Every minute is somebody's train. This is the 4:12."
- **The sentence** is a real departure, with the time on a departure-board
  chip. Under it is the route as a board would show it, and a map that flies
  to the line.
- **The time never changes.** It is always the time on your own clock, read
  off a station clock somewhere else. The chevrons at the top turn through
  the parts of the world that station can be in: North America, Latin
  America, Europe & Africa or Asia-Pacific. Where the timetables have nothing
  leaving from that region at this minute, the clock says so and shows one
  from elsewhere.
- **Another 4:12** steps through the other departures that share the minute:
  the chosen region's first, then the rest of the world's. The space bar and
  the arrow keys do the same.
- The date in the corner opens a card with the day's first and last
  departures.

Each minute opens on a departure a stranger can picture: a train with a name
or a long-distance brand, or a ferry, that starts or ends in a well-known
city. The others are a tap away.

## Put it on a phone, a tablet or a foldable

The page is built to be left running on a stand. The **Add to your device**
button at the top of the page gives the steps below for whichever device it is
opened on.

**iPhone or iPad**

1. Open the clock in Safari.
2. Tap Share, then **Add to Home Screen**.
3. Open it from the new icon. It runs full screen, without Safari's bars.
4. Stand the device up and plug it in.

The page asks the device to keep the screen on while it is open. If yours
still dims, set Settings, Display & Brightness, Auto-Lock to Never while it is
on the stand.

**A foldable, such as iPhone Duo**

Follow the same steps. Then fold the phone into a tent with the outer screen
facing you, or stand it open like a book.

On a small, wide screen the clock switches to its **stand face** by itself:
only the sentence, set as large as will fit, the line it runs on, and the
time in the corner. That is the picture at the top of this page. A phone
turned on its side does the same.

This is the page running full screen. It is not iOS StandBy, which only shows
widgets from installed apps and so cannot show a web page.

On the stand face, tap the sentence to see the minute's other departures.

**Android**

Open the clock in Chrome, then choose **Add to Home screen** or **Install app**
from the menu.

A few options go on the end of the address:

| Add this | What it does |
| --- | --- |
| `?theme=dark` or `?theme=light` | Holds one theme whatever the device is set to. Dark suits a bedside. |
| `?at=16:12` | Holds the clock at one minute, to share a single train. It reads the same on any day. |
| `&pick=tokyo` | With `?at`, opens on one train: a word or two from its name or its stations. |
| `?face=stand` | The stand face on any screen. `?face=full` keeps the whole page. |
| `?region=eu` | Opens on one part of the world: `na`, `la`, `eu` or `ap`. |
| `#widget` | A square card the size of a Home Screen widget. |

## Run it locally

The page loads its data with `fetch`, so serve the folder instead of opening
the file:

```
python3 -m http.server
```

Then open http://localhost:8000.

## Files

```
index.html            the clock: markup, styles and script in one file
data/00.json … 23     one file per hour: the departures for each minute
data/days.json        the first, last and longest trips for each date
data/land.json        coastlines for the dot-matrix map
manifest.webmanifest  lets a phone install it to the Home Screen
icon.svg, icon-*.png  the icon
```

There is no build step and nothing to install.

## Credits

- The idea: the Guardian's readers, Jaap Meijers and Johannes Enevoldsen.
- Times: the operators' published timetables. Each departure names its
  operator on the page.
- Tokyo: six bullet trains were added by hand, because the timetables the
  clock was built from had none. Their times are from the JR Timetable for
  November 2026, as shown on JR East's timetable site. The card behind the
  date counts the original timetables only.
- Type: Newsreader, Overpass and Overpass Mono.
- A sibling: the [Docket Clock](https://github.com/zula-root/Docket-Clock),
  which tells the time with sentences from court opinions.

![The Transit Clock and the Docket Clock side by side on two folded phones](docs/duo-stand-pair.jpg)
