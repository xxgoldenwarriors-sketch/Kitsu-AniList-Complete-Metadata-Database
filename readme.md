# AnimeVault – Complete Anime Metadata Database

A large-scale anime metadata collection combining data from **Kitsu** and **AniList**, including detailed anime information and episode-level metadata.

AnimeVault brings together two major anime databases into a single SQLite database, providing a searchable collection of anime records, metadata, and episode information.

## Database Statistics

| Statistic | Count |
|---|---:|
| Total Anime Records | 23,603 |
| Kitsu Anime | 22,573 |
| AniList Anime | 1,030 |
| Total Episodes | 291,485 |
| Database Size | 491 MB |

## Data Sources

### Kitsu

**22,573 anime records**

Kitsu provides the majority of the anime metadata in this database.

Available information includes:
- Anime titles (canonical, English, and Japanese)
- Synopsis and descriptions
- Total episode count
- Airing status
- Start and end dates
- Average user rating
- User popularity count
- Genres and categories
- Original API response data

**Episode Metadata**

Kitsu episode information has also been fully enriched.

The database includes:
- Episode IDs
- Episode numbers
- Relative episode numbers
- Season numbers
- Episode titles
- Episode synopses and descriptions
- Original air dates
- Episode runtime / length
- Episode thumbnail URLs
- Original episode API response data

### AniList

**1,030 anime records**

AniList contributes additional anime metadata and information.

Available information includes:
- Anime titles (Romaji, English, and Native)
- Synopsis and descriptions
- Total episode count
- Airing status
- Start and end dates
- Average community score
- Popularity ranking
- Genres
- Studio information
- MyAnimeList IDs (where available)
- Cover image URLs
- Banner image URLs
- Original GraphQL response data

## Database Structure

The SQLite database contains the following tables:

| Table | Description |
|---|---|
| `anime` | Main anime metadata from Kitsu and AniList |
| `episodes` | Detailed Kitsu episode metadata |
| `progress_state` | Source collection progress information |
| `episode_progress` | Episode enrichment progress information |

### Anime Records

Each anime record contains standardized fields:

- `id` – Internal database ID
- `source` – Original data source (`kitsu` or `anilist`)
- `source_id` – Original source-specific anime ID
- `title` – Primary anime title
- `title_english` – English title
- `title_japanese` – Japanese title
- `synopsis` – Anime description
- `episodes` – Total episode count
- `status` – Release / airing status
- `start_date` – Release start date
- `end_date` – Release end date
- `score` – Average score
- `popularity` – Popularity count or value
- `genres` – Genre information (JSON)
- `studios` – Studio information (JSON)
- `raw_data` – Original API response (JSON)
- `fetched_at` – Record collection timestamp

### Episode Records

Episode records contain:

- `source` – Original data source
- `anime_source_id` – Associated anime ID
- `episode_id` – Original episode ID
- `number` – Episode number
- `relative_number` – Relative episode number
- `season_number` – Season number
- `title` – Episode title
- `synopsis` – Episode description
- `airdate` – Original air date
- `length` – Episode runtime
- `thumbnail_url` – Episode thumbnail URL
- `raw_data` – Original API response (JSON)

## Dataset Completion

<details>
<summary>Collection status</summary>

| Collection | Status |
|---|---|
| Kitsu anime metadata | Complete |
| Kitsu episode enrichment | Complete |
| AniList anime metadata | Complete |

</details>

## Database Format

- **Format:** SQLite 3
- **Filename:** `anime.db`
- **Size:** Approximately 491 MB
- **Anime Records:** 23,603
- **Episode Records:** 291,485

The original API responses are preserved as JSON in the database, alongside standardized columns. This allows access to both normalized metadata and additional source-specific information.

## Intended Uses

AnimeVault can serve as a foundation for:

- Anime catalog websites
- Anime discovery and search engines
- Anime tracking applications
- Anime recommendation systems
- Anime metadata APIs
- Episode databases
- Anime analytics and statistical projects
- Applications requiring locally stored anime metadata

## Data Attribution

Anime metadata originates from [Kitsu](https://kitsu.io/) and [AniList](https://anilist.co/).

This is an independently collected and consolidated dataset. AnimeVault is not affiliated with, endorsed by, or officially associated with either service.

Please refer to the respective platforms' terms and data policies when using or redistributing their data.

---

**AnimeVault** — A consolidated collection of anime metadata from Kitsu and AniList.
