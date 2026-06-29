# Local Government Innovation Scan — Cowork daily-job spec

A daily Cowork job that scans for **innovation signals** — new ideas, technologies,
pilots and proven practices — relevant to Australian local government, and writes a
styled digest that a separate helper publishes to GitHub Pages. The agent writes
structured JSON, never HTML; a native macOS helper does the git push.

This is an **innovation / horizon-scanning** radar (not a risk radar): the goal is to
surface things a council could *adopt, trial, or watch*, scoped strictly to functions
Australian councils actually perform.

> Current context (2026): Three forces dominate the sector — a severe workforce/skills
> shortage (≈83% of councils) pushing automation and AI into statutory work; the
> housing-and-planning crunch driving AI-assisted development assessment (NSW AI
> Solutions Panel, DAISY, PlanSA automation); and the circular-economy transition
> (FOGO rollouts, energy-from-waste, recycled-content roads). Smart-community programs
> (ASCA members like City of Casey, Newcastle, Sunshine Coast) and climate/biodiversity
> tech are the other active frontiers.

## 1. Source register

### 1a. Australia — councils & sector — PRIMARY (full depth, scan DAILY)
| Source | Origin tag | Lens / why |
|---|---|---|
| Council media releases via Mirage News | AU-council | Daily firehose of individual-council announcements |
| LG News Roundup (lgnewsroundup.com, VLGA-backed) | AU-council | Curated daily AU council news/podcast — governance, CEO/mayor moves, notable motions |
| ALGA (incl. National General Assembly motions) | AU-council | National advocacy + grassroots council ideas |
| State peak bodies: LGNSW, MAV, LGAQ, WALGA, LGA SA, LGAT, LGANT | AU-council | Member innovation, policy, awards |
| National Awards for Local Government | AU-council | Proven, judged innovation (strongest "adopt" signal) |
| ASCA (Australian Smart Communities Association) | AU-council | Smart-community case studies, conference, trials |
| Government News; Council Magazine; LG Focus; Gov Tech Review | AU-council | Sector press incl. notable council motions/pilots |
| IPWEA | AU-industry | Public works, roads, asset-management innovation |

### 1b. Australia — industry verticals — PRIMARY (scan DAILY)
| Source | Origin tag | Domain |
|---|---|---|
| WMRR; Waste Management Review; Inside Waste | AU-industry | Waste / circular economy |
| Roads & Infrastructure Magazine; Infrastructure Magazine | AU-industry | Roads, bridges, civil construction |
| ABCB (NCC); Green Building Council of Australia; NABERS | AU-industry | Building standards & environmental performance |
| Parks & Leisure Australia; ALIA / APLA | AU-industry | Open space; public libraries |
| Infrastructure Australia; ARENA | AU-industry | Infrastructure pipeline; council energy projects |

### 1c. Overseas — EQUAL WEIGHT across regions (scan DAILY, scope-filtered per §3b)
| Source | Origin tag | Region |
|---|---|---|
| LGIU (and LGIU Australia); LocalGov.co.uk | UK | Closest council scope to AU |
| Bloomberg Cities (Johns Hopkins) | global | City innovation, very active |
| Route Fifty; GovTech (e.Republic) | US | State & local (heaviest scope filtering) |
| Cities Today; Apolitical | global | Public-sector innovation network |
| LGNZ; Taituarā | NZ | Similar council scope to AU |

### 1d. Tertiary & research institutes — EQUAL WEIGHT by origin (scan DAILY, low-frequency/high-signal)
Occasional publishers (blogs, papers, case studies); most output is `horizon` or `trial`
maturity. Scope-filter per §3b. Highest-frequency outlets flagged ▲.
| Institute | Origin tag |
|---|---|
| ▲ UTS Centre for Local Government / IPPG (Commonwealth Journal of Local Governance) | AU-research |
| UNSW City Futures Research Centre | AU-research |
| University of Canberra — Institute for Governance & Policy Analysis | AU-research |
| University of New England — local government program | AU-research |
| Griffith University — Centre for Governance & Public Policy | AU-research |
| University of Melbourne — Melbourne School of Government | AU-research |
| RMIT — Centre for Urban Research | AU-research |
| ▲ ANZSOG (Australia & New Zealand School of Government) | AU-research |
| ▲ University of Birmingham — INLOGOV (blog) | UK |
| De Montfort University — Local Governance Research Centre | UK |
| UCL — Institute for Innovation & Public Purpose | UK |
| LSE Cities (broader urban — lighter touch) | UK |
| ▲ University of Toronto — Institute on Municipal Finance & Governance | CA |
| University of Victoria — Local Government Institute | CA |
| ▲ Harvard Kennedy School — Taubman Center + Ash Center (Innovations in Government) | US |
| ▲ Johns Hopkins — Bloomberg Center for Public Innovation / GovEx | US |
| NYU — Marron Institute of Urban Management | US |
| University of Pennsylvania — Fels Institute of Government | US |

### 1e. The 50-council watchlist — DEEP SCAN ON SATURDAYS ONLY
On Saturdays, additionally scan these councils' newsrooms and the most recent
available council/committee business papers and Councillor Notices of Motion. (Councils
meet ~monthly and agendas drop only days before, so expect lumpy yield — empty is fine.)

NSW: City of Sydney; City of Newcastle; City of Parramatta; Lake Macquarie City;
City of Wollongong; Blacktown City; Liverpool City; Penrith City; Georges River;
Ku-ring-gai; Northern Beaches; Parkes Shire; Lithgow City; Burwood.
VIC: City of Melbourne; City of Casey; City of Greater Geelong; Wyndham City; Knox City;
City of Greater Dandenong; City of Ballarat; City of Greater Bendigo; City of Darebin;
City of Port Phillip.
QLD: Brisbane City; Sunshine Coast; City of Logan; City of Ipswich; City of Moreton Bay;
City of Gold Coast; Townsville City; Cairns Regional; Palm Island Aboriginal Shire.
WA: City of Stirling; City of Joondalup; City of Wanneroo; City of Vincent;
Town of Victoria Park; City of Fremantle; Shire of Murray.
SA: City of Adelaide; City of Salisbury; City of Marion; City of Onkaparinga;
City of Charles Sturt.
TAS: City of Launceston; City of Hobart; Devonport City.
NT: City of Darwin; West Arnhem Regional.

### 1f. Paid — headline + standfirst only, flagged
AFR / SMH (held): public headline + standfirst only, `"paywall": true`, link out; never
log in or scrape full text. UK's LGC and The MJ: same treatment. Any other paywalled
trade title: headline + standfirst only.

## 2. Paywall & copyright policy
- Free: fetch (RSS-first, respect robots.txt), summarise in own words, link out.
- Paid not held: public headline + standfirst only, `"paywall": true`, link out.
- AFR/SMH/LGC/MJ (held or hard paywall): same, flagged; never log in or scrape full text.
- Always paraphrase; never reproduce article paragraphs or sentences.

## 3. Relevance filter

### 3a. Innovation keyword set
Include items signalling something new or newly proven: innovation, pilot, trial,
first-in-Australia, world-first, prototype, proof-of-concept, AI / machine learning,
digital twin, IoT / sensors, automation, robotics, drone, smart city / smart community,
circular economy, energy-from-waste, FOGO, recycled / recycled-content, net zero,
electrification, microgrid, battery, biodiversity tech, nature-based, modular / prefab
construction, 3D-printed, geopolymer / low-carbon concrete, data platform, open data,
GIS, customer-experience redesign, service transformation, award-winning, grant-funded
trial, partnership / co-design, regulatory sandbox.

### 3b. SCOPE FILTER — Australian local-government functions ONLY
INCLUDE (AU council functions): waste & recycling; local roads, footpaths, bridges,
drainage/stormwater; parks, open space, trees, biodiversity; libraries; community,
recreation & aquatic facilities; planning & development assessment; building regulation;
environmental health; animal management; economic development & placemaking; climate &
sustainability; customer service & digital/data; asset management; governance,
procurement & workforce.
EXCLUDE (not AU council functions): policing / law enforcement; K-12 schools &
education; public hospitals & clinical health; social-welfare payments; prisons; and —
except where a specific Australian council demonstrably runs it — water/sewerage
utilities and public-transport operations (mostly state-run here).
Rule for overseas items: judge by the FUNCTION, not the label. A US "city" tackling
police staffing is OUT; the same city's waste-routing AI is IN. When an overseas item
mixes in/out functions, cover only the in-scope part.

### 3c. Weighting & tagging
All regions equal weight. Tag every item with its origin tag FIRST
(`AU-council` | `AU-industry` | `UK` | `US` | `NZ` | `global`), then a topic tag.

## 4. Innovation taxonomy — assign each item exactly one
- Waste & circular economy
- Roads, transport & mobility
- Built environment & planning
- Climate, energy & biodiversity
- Digital, data & AI / customer service
- Community, libraries & placemaking
- Asset management & infrastructure delivery
- Governance, procurement & workforce

## 5. Maturity — assign exactly one (mapped to the shared renderer's keys)
Use the existing three JSON severity keys; their MEANING in this digest is:
- `"act"`    = **ADOPT** — proven and replicable in Australia now; a council could pick it up.
- `"watch"`  = **TRIAL** — being piloted somewhere; promising but unproven at scale.
- `"inform"` = **HORIZON** — early/emerging idea or signal; awareness only.
Reserve `"act"` (adopt) for genuinely proven, transferable innovations.

## 6. Writing rules
- Paraphrase; never reproduce sentences. `headline`: rewritten one-liner.
  `summary`: 1–2 sentences (what it is). `so_what`: 1–2 sentences naming the relevance
  to an Australian council (who could use it / what function it improves).
- Deduplicate across sources and the previous 3 days. Never fabricate; real source +
  URL on every item. Empty day → publish empty sections and say so in `summary`.

## 7. Output schema (same renderer as all digests)
Write `data/digests/<TODAY>.json` (YYYY-MM-DD, Australia/Sydney):
```
{ "date","generated_at","posture","summary","counts":{ "act","watch","inform" },
  "sections":[ { "category","items":[ { "severity","headline","summary","so_what",
  "tags":["<origin tag first>", "topic"], "source","url","published","paywall" } ] } ] }
```
- `posture`: one-line read of the innovation climate today.
- `counts`: tally of adopt(act)/trial(watch)/horizon(inform) across all items.
Then update `data/manifest.json`: refresh today's top entry in place if present, else
prepend `{ date, file, posture, counts }` (newest first); leave older entries alone.
Validate both files parse. Do NOT run git; the helper publishes.

## 8. Cadence (read carefully)
- Run **every day** (7 days/week).
- **Every day:** scan §1a, §1b, §1c, §1d.
- **Saturdays only:** ADDITIONALLY scan the §1e 50-council watchlist (news + latest
  business papers / Notices of Motion).
- (If you prefer the deep council scan on Sunday instead, change "Saturday" here and in
  the Cowork task prompt — one word each.)
