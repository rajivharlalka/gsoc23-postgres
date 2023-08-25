# GSoC 2023 Project Report

## pg_statviz: Time Series Analysis & Visualization of Statistics

**Contributor**: [Rajiv Harlalka](https://github.com/rajivharlalka)

**Organisation**: [PostgreSQL](https://postgresql.org)

**Mentors**: [Jimmy Angelakos](https://github.com//vyruss), [Pavlo Golub](https://github.com/pashagolub), [Boriss Mejías](https://www.linkedin.com/in/boriss-mej%C3%ADas-4637401)

**Project Repository**: [pg_statviz](https://github.com/vyruss/pg_statviz)

**Project Proposal**: [Proposal](https://docs.google.com/document/d/1vCa7Fukx8IhGxY86P3dY-En9ZYNjb6j2jqyTDe5cHbk/edit?usp=sharing)

## Project Overview

pg_statviz is a PostgreSQL extension with a command line utility pair. The extension can snapshot cumulative and dynamic statistics of various PostgreSQL internal tables. These snapshots are stored in another schema, pgstatviz, which can be queried using SQL for analysis. 

The python command-line utility accesses the tables in this schema to perform time-series analysis and create visualizations. Using both the extension and python tool, database administrators can efficiently perform sophisticated analysis of their PostgreSQL database statistics over different time intervals.

## Project Deliverables

- Increased Modules in the extension
- Packaging of extension for PGDG Repositories and Linux Distributions
- Add/Update Documentation about the tool and packaging extensions 
- Bug fixes in the original implementation 

## Project Results

### Added various new metrics to collect

The newer version of the PostgreSQL extension now collects more statistics which increases room for finding bottlenecks in the database. System Views such as `pg_stat_database`, `pg_stat_locks` provided various metrics which helps in analyzing mission critical systems.

Various GUC's whose value have a huge role in deciding various factors internally by the database and affect planner paths. Changes in such metrics are helpful to find the suitable value and even check for anamolies if any.

### Added support through packages in the Red Hat and Debian community.

Helped in packageing the extension which would facilitate the end users in the installation process by reducing the number of steps involved by huge count.

### Various Minor fixes to handle edge cases

Made several minor fixes to add support for systems with different tools, (missing `hostname` support) and checks that handle edge cases for various versions of the extension. (`wal` statistics missing in version<15).

### Documentation on the features added

I significantly enhanced the project during GSoC by  crafting comprehensive updated documentation. This empowers users to easily understand and utilize the software's features, fostering accessibility and accelerating its adoption within the community.

# Contributions


|Commit|Descritption|
|---|---|
|[94e4a05](https://github.com/vyruss/pg_statviz/commit/94e4a054bf06246e4a3a46f220fa0fdc4480d0b2) | Add condition to support wal statistics in PG version>15|
|[299039c](https://github.com/vyruss/pg_statviz/commit/299039c481ad349f47b9c1f9df8dcf73e1d6f2b2) | Add support for systems that have missing `hostname` tool|
|[27d51ff](https://github.com/vyruss/pg_statviz/commit/27d51ffd5a098b883c4e48b05077d0f1edcc65ab) | Added more GUC to the statistics|
|[8ef810](https://github.com/vyruss/pg_statviz/commit/8ef8108e38f571f926627b0203805991e3e2f0bc)| Added statistics collection about locks|
|[22f64dd](https://github.com/vyruss/pg_statviz/commit/22f64ddd555ac00114a2d5bd74c945144b62292b)| Updated deprecated python's importlib functions|
|[f11923](https://github.com/vyruss/pg_statviz/commit/f11923eef12be70244a4d8f8aaccdd45fe4e0ccc)| Fix formula to calculate the cache hit ratio|

Along with these, wrote multiple blogs on my learnings and experiences on my jouney. 
Blogs can be found here: [Website](https://rajivharlalka.tech/blogs) and my learning dump with various articles/books I read through can be found [here](https://gist.github.com/rajivharlalka/d8283358b8aaf5f8db5c0a7b4bfd909f) and [here](https://gist.github.com/rajivharlalka/f9a54c95eeafeef58734e2006f957fed).

# Conclusion

I was able to complete almost all of the goals that were decided for the project. I would thank my mentors for guiding me throughout the journey. I loved working on this project and I would continue working and contributing to the community.

For me, Open-Source seemed like a wild forest which pretty much confused me, but contributing to this project is one of the best experiences I have had and it gave me quite some clarity and confidence on contributing to large codebases and fixing issues. Thanks to Google Summer of Code I got this opportunity to learn and contribute for this amazing organization. It has been a fun experience. I am grateful that I got an opportunity to get mentored by such experienced developers, they helped and guided me whenever I got stuck and thanks to them for bearing the silly mistakes I did and helping me throughout the journey.

# Acknowledgement

I am extremely grateful to get mentored by [Jimmy Angelakos](https://github.com//vyruss), [Pavlo Golub](https://github.com/pashagolub), [Boriss Mejías](https://www.linkedin.com/in/boriss-mej%C3%ADas-4637401)
, for their constant support, guidance and help. Also the PostgreSQL Community has been immensely helpful and developers guided me throughout the project.

Thanks to Google and PostgreSQL for providing me the opportunity to work on this amazing project. It has been a great learning experience and contributing to PostgreSQL has been an amazing experience. I would certainly want to continue contributing and help the community.