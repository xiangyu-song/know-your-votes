# Know Your Votes: NZ Election 2026, explained simply

A free, neutral, phone-friendly guide to the 2026 New Zealand general election, for people who just want the facts in one place.

**Live site:** https://xiangyu-song.github.io/know-your-votes/

Independent and neutral. Doesn't recommend a party. Not affiliated with any political party or the Electoral Commission. For official information, go to [vote.nz](https://vote.nz/).

## What's on the site

It works on phones, tablets and computers, in light and dark mode:

- **Phones:** each section has its own tab in a bar at the bottom of the screen.
- **Tablets and computers:** everything is on one page with a menu at the top. Wide screens show party and debate cards three across. Touchscreens get finger-sized buttons.

| Section | What you'll find |
|---|---|
| **Dates** | Election day (Saturday 7 November), countdowns to advance voting and official results, the enrolment deadline and a timeline of key dates |
| **Your two votes** | How your party vote and electorate vote work under MMP, with the Electoral Commission's own 2-minute explainer video |
| **Policies** | 11 topics × 8 parties, quoted word for word from each party's own website, with links to the full policy. View by topic or by party. Two independent comparison tools side by side (Policy.nz and 1News Vote Compass), and every party on the ballot |
| **Polls** | The latest 14-day poll average, a chart since August (each dot is one poll's result, each line a 14-day average; tap any point to see which polls it uses), every poll with its source, and a seat calculator |
| **Debates** | Upcoming and past debates, with "Watch on…" and "Watch again on…" links to the broadcaster's own site. Ends with **Election news** (see below) |
| **Before you vote** | Five quick steps before you vote, how to vote, accessible formats, and how to add the site to your phone's home screen |

### Election news

At the end of the Debates section, an **Election news** card links to the Election 2026 page of seven New Zealand newsrooms, listed A to Z so none is favoured: 1News, Newsroom, NZ Herald, RNZ, Stuff, Te Ao Māori News and The Spinoff. It's there for day-to-day campaign coverage, which the site itself doesn't summarise. The newsrooms are independent and not connected to Know Your Votes; their reporting and opinion pieces are their own, and some stories may need a subscription.

### Other languages

An **Other languages** button at the top links to the Electoral Commission's official translations. The site does not use machine translation.

## Ground rules

- **Accuracy first.** Every poll figure, date and quote links to its source, and each one is checked against that source before it goes live.
- **Parties' own words.** Policies are exact quotes from the visible text of each party's website. The same rules apply to every party: up to three quotes per topic, specific commitments preferred over slogans, conditions and start dates kept, and petitions excluded. Where a party lists nothing on a topic, the site says "Not covered on [party]'s 2026 policy pages", with the date it was checked.
- **Equal treatment.** Parties appear in random order (the same order for your whole visit), with a switch to show them A to Z. No logos. Party colours appear only next to party names.
- **No predictions or opinions.** No recommendations, rankings, coalition predictions, debate scoring, betting odds or AI chatbot. The seat calculator is a what-if tool, not a forecast.
- **Link, don't copy.** News articles and debates are linked to the original site, never copied. The only video on the site is the Electoral Commission's MMP explainer, which plays from YouTube.
- **No updates on election day** (7 November), in line with the Electoral Commission's rules.
- **Accessible.** Text meets WCAG AA contrast in light and dark mode, works with a keyboard, and has no tap-highlight boxes on phones.

"How we chose these" on the Policies section explains which parties are included and how quotes are picked.

## How the numbers work

- **Poll average:** the average of every poll whose fieldwork ended in the 14 days up to a given date, weighted by sample size (1,000 is assumed if a poll doesn't report its sample). This is the site's own calculation from the figures in the poll table, not a pollster's.
- **Seat calculator:** uses the Sainte-Laguë method that the Electoral Commission uses, with the 5% threshold, the electorate exception and overhang seats. It was tested against the official 2023 result. Tick "Wins electorate" to give a party an electorate seat (the count starts at 1 and can be changed; delete it or type 0 to untick). The whole calculator fits on one phone screen. Te Tai Tokerau Party isn't reported separately in most polls, so its party vote starts empty.

## Keeping it up to date

A daily update runs at 7pm NZ time. Each update re-checks polls, debates, enrolment figures, every party's policy pages and quotes, and every source. It then updates the "checked" dates on the site, runs the layout and calculator tests, publishes, and sends the owner a short report. Any change to a party's policy quotes needs the owner's approval before it goes live. There are no updates on election day.

## How it was made

Built with AI, checked by a person. Xiangyu set the scope, the neutrality and accuracy rules and the design, tested every change on real devices and approved it before release. Claude (an AI assistant made by Anthropic) wrote the code, gathered and checked the sources, and ran the tests.

## How it's built

A plain static website hosted on GitHub Pages, with no build step, no tracking and no cookies.

```
index.html                 the page
assets/app.js              reads the data and builds each section
assets/style.css           layout, light and dark mode
assets/manifest.webmanifest, assets/img/   home-screen icon
data/*.json                all content: dates, enrolment, polls, policies,
                           parties, debates, glossary, sources, site settings
                           (updates.json is an internal change log, not shown)
```

Content changes are made in `data/`, so no code needs to change. When `app.js` or `style.css` changes, bump the `?v=` tag where `index.html` loads them, so phones don't mix new content with old cached styles.

To preview the site on your own computer, run this in the project folder:

```
python3 -m http.server 8000
```

Then open http://localhost:8000.

## Feedback

Spotted a mistake or have a suggestion? Open an issue on this repository or message Xiangyu on [LinkedIn](https://www.linkedin.com/in/xiangyusong/).

## Credits

Made by Xiangyu Song, with help from Claude. Poll figures, policies and dates belong to their original sources, which are linked throughout the site.
