Horror Films
================

  - [Scraping Data](#scraping-data)
  - [Plotting Data](#plotting-data)

## Scraping Data

``` r
library(rvest)

topGrossingLink <- "https://en.wikipedia.org/wiki/List_of_highest-grossing_horror_films"

horrorMovies <- read_html(topGrossingLink) %>% 
  html_table(fill = TRUE) %>% 
  `[[`(1)

knitr::kable(horrorMovies)
```

| Rank | Film                                  | Worldwide gross | Year | Franchise or basis     | Studio                            | Ref    |
| ---: | :------------------------------------ | :-------------- | ---: | :--------------------- | :-------------------------------- | :----- |
|    1 | It                                    | $700,381,748    | 2017 | It                     | New Line Cinema                   | \[1\]  |
|    2 | The Sixth Sense                       | $672,806,292    | 1999 | N/A                    | Hollywood Pictures                | \[2\]  |
|    3 | War of the Worlds                     | $591,745,540    | 2005 | The War of the Worlds  | Amblin Entertainment              | \[3\]  |
|    4 | I Am Legend                           | $585,349,010    | 2007 | I Am Legend            | Village Roadshow Pictures         | \[4\]  |
|    5 | World War Z                           | $540,007,876    | 2013 | World War Z            | Skydance Productions              | \[5\]  |
|    6 | The Meg                               | $530,243,742    | 2018 | The Meg                | Warner Bros. Pictures             | \[6\]  |
|    7 | Godzilla                              | $529,076,069    | 2014 | Godzilla               | Legendary Pictures                | \[7\]  |
|    8 | It Chapter Two                        | $473,093,228    | 2019 | It                     | Warner Bros. Pictures             | \[8\]  |
|    9 | Jaws                                  | $470,653,000    | 1975 | Jaws                   | Universal Pictures                | \[9\]  |
|   10 | The Exorcist                          | $441,306,145    | 1973 | The Exorcist           | Hoya Productions                  | \[10\] |
|   11 | The Mummy Returns                     | $433,013,274    | 2001 | The Mummy              | Universal Pictures                | \[11\] |
|   12 | The Mummy                             | $415,933,406    | 1999 | The Mummy              | Universal Pictures                | \[12\] |
|   13 | The Mummy                             | $409,231,607    | 2017 | The Mummy              | Universal Pictures                | \[13\] |
|   14 | Signs                                 | $408,247,917    | 2002 | N/A                    | Blinding Edge Pictures            | \[14\] |
|   15 | Prometheus                            | $403,354,469    | 2012 | Alien                  | Scott Free Productions            | \[15\] |
|   16 | The Mummy: Tomb of the Dragon Emperor | $401,128,639    | 2008 | The Mummy              | Universal Pictures                | \[16\] |
|   17 | Godzilla: King of the Monsters        | $385,900,138    | 2019 | Godzilla               | Legendary Pictures                | \[17\] |
|   18 | Godzilla                              | $379,014,294    | 1998 | Godzilla               | Centropolis Entertainment         | \[18\] |
|   19 | The Nun                               | $365,550,119    | 2018 | The Conjuring Universe | New Line Cinema                   | \[19\] |
|   20 | Hannibal                              | $351,692,268    | 2001 | Hannibal Lecter        | Dino De Laurentiis Company        | \[20\] |
|   21 | A Quiet Place                         | $340,939,361    | 2018 | N/A                    | Platinum Dunes                    | \[21\] |
|   22 | The Conjuring 2                       | $320,392,818    | 2016 | The Conjuring Universe | New Line Cinema                   | \[19\] |
|   23 | The Conjuring                         | $319,494,638    | 2013 | The Conjuring Universe | New Line Cinema                   | \[19\] |
|   24 | Resident Evil: The Final Chapter      | $312,242,626    | 2017 | Resident Evil          | Constantin Film                   | \[22\] |
|   25 | Annabelle: Creation                   | $306,515,884    | 2017 | The Conjuring Universe | New Line Cinema                   | \[19\] |
|   26 | Van Helsing                           | $300,257,475    | 2004 | Dracula                | Sommers Company / Stillking Films | \[23\] |
|   27 | Resident Evil: Afterlife              | $300,228,084    | 2010 | Resident Evil          | Constantin Film                   | \[24\] |
|   28 | Shutter Island                        | $294,804,195    | 2010 | Shutter Island         | Phoenix Pictures                  | \[25\] |
|   29 | Split                                 | $278,454,358    | 2017 | Unbreakable            | Blinding Edge Pictures            | \[26\] |
|   30 | Scary Movie                           | $278,019,771    | 2000 | Scary Movie            | Dimension Films                   | \[27\] |
|   31 | The Silence of the Lambs              | $272,742,922    | 1991 | Clarice Starling       | Strong Heart/Demme Production     | \[28\] |
|   32 | Annabelle                             | $257,047,661    | 2014 | The Conjuring Universe | New Line Cinema                   | \[19\] |
|   33 | The Village                           | $256,697,520    | 2004 | N/A                    | Blinding Edge Pictures            | \[29\] |
|   34 | Halloween                             | $255,498,536    | 2018 | Halloween              | Blumhouse Productions             | \[30\] |
|   35 | Get Out                               | $255,407,663    | 2017 | N/A                    | Blumhouse Productions             | \[31\] |
|   36 | Us                                    | $254,732,150    | 2019 | N/A                    | Monkeypaw Productions             | \[32\] |
|   37 | The Blair Witch Project               | $248,639,099    | 1999 | Blair Witch            | Haxan Films                       | \[33\] |
|   38 | The Ring                              | $248,218,486    | 2002 | The Ring               | DreamWorks Pictures               | \[34\] |
|   39 | Unbreakable                           | $248,118,121    | 2000 | Unbreakable            | Blinding Edge Pictures            | \[35\] |
|   40 | Glass                                 | $246,985,576    | 2019 | Unbreakable            | Blinding Edge Pictures            | \[36\] |
|   41 | Dark Shadows                          | $245,527,149    | 2012 | Dark Shadows           | Village Roadshow Pictures         | \[37\] |
|   42 | Alien: Covenant                       | $240,891,763    | 2017 | Alien                  | 20th Century Fox                  | \[38\] |
|   43 | Resident Evil: Retribution            | $240,004,424    | 2012 | Resident Evil          | Constantin Film                   | \[39\] |
|   44 | Constantine                           | $230,884,728    | 2005 | Hellblazer             | Warner Bros. Pictures             | \[40\] |
|   45 | Annabelle Comes Home                  | $228,552,591    | 2019 | The Conjuring Universe | New Line Cinema                   | \[41\] |
|   46 | Interview with the Vampire            | $223,664,608    | 1994 | The Vampire Chronicles | The Geffen Film Company           | \[42\] |
|   47 | Scary Movie 3                         | $220,673,217    | 2003 | Scary Movie            | Dimension Films                   | \[43\] |
|   48 | Dracula Untold                        | $217,124,280    | 2014 | Dracula                | Universal Pictures                | \[44\] |
|   49 | Bram Stoker’s Dracula                 | $215,862,692    | 1992 | Dracula                | American Zoetrope                 | \[45\] |
|   50 | End of Days                           | $211,989,043    | 1999 | N/A                    | Beacon Pictures                   | \[46\] |

## Plotting Data
