# craigslist proxies: stop ghosted ads, post in other cities, and scrape listings without burning your real IP

The most annoying thing about Craigslist isn't the design. It's that the site almost never tells you when it has decided to ignore you.

You hit publish, the confirmation email lands, the ad shows up in your own account view — and it is invisible to everyone else. Or you're halfway through a scrape and requests start timing out after forty-something pages. Neither failure comes with an error message that says "your IP is the problem." That's the part people waste weeks on.

Proxies are the standard fix for both jobs. But "Craigslist proxies" gets thrown around as if any IP will do, and that's where most setups fall apart: the wrong kind of IP produces exactly the silent failure you were trying to escape.

## What's actually going wrong when your post disappears

Three mechanisms matter on Craigslist, and they behave differently.

**Ghosting.** Craigslist accepts your post, then quietly hides it. Your side looks fine — the post is live in your account, the email arrives — but it never enters the public listings. Datacenter ranges, VPN exits, and hosting subnets get ghosted on sight, because a person selling a couch doesn't list it from a server farm. A fresh datacenter IP might survive a browse; it will not survive a post you actually need seen.

**Location mismatch.** Craigslist cross-checks your IP's location against the board you're posting to. Post on the Chicago board from a New York exit and the ad gets deleted, or ghosted outright. This is why city-level targeting isn't a nice-to-have here — it's the difference between a post that exists and one that doesn't.

**Per-IP rate limits.** Craigslist meters how much a single address can post and request, and it throttles automated access hard. One IP paging through listings hits the wall fast. That's the scrape dying on page 40. Post several ads in a row from one address and the later ones get dropped even when the first slipped through.

There's a fourth thing worth naming, because it explains why cheap options waste your time: free proxy lists are shared addresses that hundreds of people have already hammered, including spammers Craigslist has flagged. You're inheriting someone else's burned reputation before your first request goes out. Free exits are fine for a logged-out look at apartment prices in another metro. They are not fine for anything you care about.

## Which proxy type survives Craigslist

Not every proxy category does the same job here. Roughly:

| Proxy type | Ghost risk on Craigslist | Where it actually fits |
| --- | --- | --- |
| Datacenter | Very high — blocked or ghosted on sight | Speed-sensitive scraping against soft targets, nothing on Craigslist |
| Rotating residential | Low, provided you rotate per request | Scraping listings, rate-limit evasion, geo checks |
| Static residential / ISP | Low, and stable | Ad posting and account management — one fixed IP per account |
| Mobile 4G/5G | Lowest | Account warm-up, clearing phone-verification friction |

Residential IPs work because they carry the trust profile of a real home broadband connection. Detection layers see a normal user in a normal city, not a hosting range.

One thing to be straight about: **9Proxy is a residential-only network.** There's a 20M+ IP pool across 90+ countries, and both rotating and sticky sessions, but no separate datacenter, ISP, or mobile product lines. For Craigslist that's mostly fine — residential handles both posting and scraping — but if your workflow depends on a dedicated static ISP IP or a 4G exit for verification steps, you'd be pairing 9Proxy with a second provider rather than replacing one with the other.

## What 9Proxy gives you to work with

The provider runs two different billing models, and understanding the split matters more than the headline price, because the right model depends on whether you're posting or scraping.

**Residential by IPs.** You buy a fixed number of IPs with unlimited bandwidth. An IP is only deducted when you forward it to a local port, unused IPs never expire, and once activated an IP stays online for several hours up to roughly 24 — residential supply being what it is, that ceiling varies. You run these through the 9Proxy desktop app (Windows, macOS, Linux) and use them as `localhost:port`, optionally with username/password authentication. This is the model for anything session-based: a Craigslist account that needs to look like the same person across a whole posting session.

**Residential by GB.** You buy bandwidth instead of addresses, spend it through rotating or sticky sessions, and generate as many endpoints as you want from the dashboard's Proxy Generator. Traffic is valid for 180 days (no expiry at Enterprise level). No app required. This is the model for scraping, where each request needs a different IP and the data per request is small.

Both models support geographic targeting down to country, state, city, ZIP, and ISP, plus HTTP/HTTPS/SOCKS5 — SOCKS5 being the protocol that matters if you're driving anti-detect browsers, Playwright, or a custom script.

Two operational details worth knowing before you commit to a plan:

- A proxy that dies within **60 seconds** of activation is replaced automatically, without you eating the cost.
- The **Today List** lets you reuse any proxy you've touched in the last 24 hours at no extra charge if it comes back online — useful when your daily Craigslist check keeps landing on the same IPs.

What you don't get is a self-serve free trial on the site. Testing happens either through an entry-level package or by asking support for test access, which is a real gap if you want to validate a specific target before spending.

👉 [Grab a small IP package and test it against your own Craigslist boards](https://bit.ly/9-Proxy)

## Matching the plan to the job

Three Craigslist jobs, three different buying decisions.

**Posting ads across cities.** Go IP-based. You want sticky sessions so an account keeps one consistent address through a whole session, and you want city or ZIP targeting so the exit matches the board you're posting on. Size it by accounts, not by traffic: roughly one IP per account, plus spares, because residential IPs do drop and you need replacements ready without pausing a campaign. Twenty to fifty IPs covers a modest multi-city operation; the 100-IP tier at $24 is where most solo operators start.

**Scraping listings at scale.** Go GB-based. Requests are small, rotation is constant, and paying per IP would be waste. The 5 GB pack at $15 is a genuine trial size for plumbing checks; a real daily scrape of multiple metros lands in the 50–200 GB range.

**Bulk account warm-up and management.** Residential works, but the discipline matters more than the plan: one IP per account, held stable, no cross-account sharing, and no switching addresses mid-session while Craigslist is tracking session continuity.

## Every 9Proxy plan and what it costs

Prices below are 9Proxy's published rates. IP-based and bundle pricing was adjusted on 1 June 2026; the GB-based rates were left unchanged. Every tier here carries the same residential pool and targeting.

### Residential by IPs — unlimited bandwidth per IP

| Package | Price | Effective rate | Purchase |
| --- | --- | --- | --- |
| 100 IPs | $24 | $0.24/IP | [Get the 100 IP package](https://bit.ly/9-Proxy) |
| 500 IPs | $72 | $0.144/IP | [Get the 500 IP package](https://bit.ly/9-Proxy) |
| 1,000 IPs + 500 bonus | $126 | $0.084/IP | [Get the 1,500 IP package](https://bit.ly/9-Proxy) |
| 2,500 IPs | $210 | $0.084/IP | [Get the 2,500 IP package](https://bit.ly/9-Proxy) |
| 5,000 IPs | $360 | $0.072/IP | [Get the 5,000 IP package](https://bit.ly/9-Proxy) |
| 15,000 IPs | $720 | $0.048/IP | [Get the 15,000 IP package](https://bit.ly/9-Proxy) |
| 25,000 IPs | $863 | $0.035/IP | [Get the 25,000 IP package](https://bit.ly/9-Proxy) |
| 50,000 IPs | $1,438 | $0.029/IP | [Get the 50,000 IP package](https://bit.ly/9-Proxy) |
| 100,000 IPs (Business) | $2,300 | $0.023/IP | [Get the 100,000 IP package](https://bit.ly/9-Proxy) |
| 200,000 IPs (Business) | $4,140 | $0.021/IP | [Get the 200,000 IP package](https://bit.ly/9-Proxy) |
| 500,000 IPs (Business) | $8,625 | $0.018/IP | [Get the 500,000 IP package](https://bit.ly/9-Proxy) |

Unused IPs don't expire. Each activated IP runs several hours up to ~24 hours.

### Residential by GB — rotating, pay per traffic

| Package | Price | Effective rate | Validity | Purchase |
| --- | --- | --- | --- | --- |
| 5 GB | $15 | $3.00/GB | 180 days | [Start with 5 GB](https://bit.ly/9-Proxy) |
| 50 GB + 5 GB bonus | $105 | $2.10/GB | 180 days | [Get the 50 GB pack](https://bit.ly/9-Proxy) |
| 100 GB | $150 | $1.50/GB | 180 days | [Get the 100 GB pack](https://bit.ly/9-Proxy) |
| 200 GB | $200 | $1.00/GB | 180 days | [Get the 200 GB pack](https://bit.ly/9-Proxy) |
| 1,000 GB | $800 | $0.80/GB | 180 days | [Get the 1,000 GB pack](https://bit.ly/9-Proxy) |
| 2,000 GB | $1,500 | $0.75/GB | 180 days | [Get the 2,000 GB pack](https://bit.ly/9-Proxy) |
| 3,000 GB (Enterprise) | $2,160 | $0.72/GB | Unlimited | [Get the 3,000 GB pack](https://bit.ly/9-Proxy) |
| 6,000 GB (Enterprise) | $4,200 | $0.70/GB | Unlimited | [Get the 6,000 GB pack](https://bit.ly/9-Proxy) |
| 10,000 GB (Enterprise) | $6,800 | $0.68/GB | Unlimited | [Get the 10,000 GB pack](https://bit.ly/9-Proxy) |

Enterprise plans add team mode — one owner plus up to five members, shared traffic that doesn't expire internally, per-member usage controls, and activity logs.

### Bundle packages — IPs plus bandwidth

| Bundle | Includes | Price | Purchase |
| --- | --- | --- | --- |
| Starter | 100 IPs + 5 GB | $30 | [Get the Starter bundle](https://bit.ly/9-Proxy) |
| Popular | 1,500 IPs + 50 GB | $180 | [Get the Popular bundle](https://bit.ly/9-Proxy) |
| Pro | 5,000 IPs + 500 GB | $720 | [Get the Pro bundle](https://bit.ly/9-Proxy) |

Bundles exist for the workflow that does both things: some accounts pinned to stable addresses for posting, plus rotating traffic for market data. If your Craigslist operation includes monitoring competitor listings and posting your own ads, the Popular bundle is usually cheaper than buying the two pieces separately.

## Setting up a Craigslist proxy without guessing

**1. Create the account and pick a model.** IP-based if you're posting; GB-based if you're scraping. Nothing to download for GB — the Proxy Generator lives in the dashboard.

**2. Choose your targeting.** For Craigslist, target the metro of the board you're posting to. Country-level targeting is too coarse; a New York exit posting to Chicago gets removed.

**3. Pick the session type.** Sticky for posting and account work. Rotating per request for scraping.

**4. Set up authentication.** Username/password for cloud tools and scripts, IP whitelisting for a fixed workstation where you'd rather not paste credentials into everything.

**5. Pull the endpoint.** Grab the list as `.txt` or `.csv`, or copy the ready-made code sample in whatever language your stack uses.

**6. Verify before you touch Craigslist.** Point your browser or tool at the endpoint, load an IP-check page, and confirm the exit matches the city you selected. If it shows your home IP, the proxy isn't active.

**7. Log in from a clean profile.** Separate browser profile or anti-detect profile per Craigslist account, one IP each, no exceptions. Cookies carried across proxy switches are how accounts get linked.

## How to tell whether your proxy is actually working

Three checks, in order of effort.

**Vision check.** Load an IP-lookup page through the proxy. Wrong city or your own IP showing means stop there.

**Behaviour check.** Post one low-value ad through a test account, then load your own listing URL from a different IP — or ask someone else to search for it. If your account shows it live and nobody else can see it, you're ghosted and the IP reputation is the first suspect.

**Metrics check.** Track posting success rate and page latency across sessions. A provider whose IPs get accepted one day and ghosted the next is churning its pool; consistent acceptance across a week tells you more than any benchmark chart.

## Where proxies don't save you

Residential IPs die. That's structural, not a brand problem — some last hours, some last minutes, and unlimited bandwidth is a billing model, not a promise of uptime. Auto-refresh and auto-rotation exist precisely because of this, and a Craigslist workflow needs to be built assuming replacements will happen mid-session.

Nothing here changes Craigslist's terms of service, and bypassing IP-based blocks has drawn legal attention in the US under the Computer Fraud and Abuse Act. Duplicate ads blasted across a dozen metros simultaneously will get accounts flagged no matter how clean the IP is. Sensible cadence, distinct ad copy per market, and account hygiene do at least as much work as the proxy does.

And skip the free lists. The one legitimate use — checking how listings look in a city you're not in, without logging in — doesn't come close to justifying the risk on anything that touches an account.

## Common questions

**Do I need a proxy just to browse Craigslist?** No, unless your network blocks it or you need to see listings in a city you can't reach otherwise. Craigslist is blocked on plenty of corporate and school networks, and that's a legitimate reason to route around it.

**Residential or mobile for Craigslist?** Residential is the workhorse for posting and scraping. Mobile carrier IPs clear phone-verification friction more reliably, but 9Proxy doesn't sell mobile exits — that's a second provider if you need it.

**How many accounts per IP?** One. Shared addresses are how Craigslist links accounts and suspends them together, which is the single most common way small operations get wiped out.

**Will 9Proxy handle Craigslist scraping?** The GB model with rotating sessions is the right tool for it, with city-level targeting so you're pulling the boards you actually care about rather than one market's listings.

**Is there a free trial?** Not a self-serve one. Entry-level packages plus the 60-second replacement policy are the realistic way to test before committing volume.

If you're running Craigslist posting or data collection seriously, the cheapest mistake is buying the wrong billing model — so start small, verify your exits match your boards, and scale once your ads stay visible.

👉 [Compare all 9Proxy residential plans and start with the smallest package](https://bit.ly/9-Proxy)
