# Star Trek Transcript Search
Transcripts of all of Star Trek and some commands to search them

## getting stared
Check out this repo, and put it somewhere you like:

```sh
$ git checkout https://github.com/varenc/star_trek_transcript_search
$ cd star_trek_transcript_search/scripts
$ ls
DIS		DS9		Enterprise	Movies		NextGen		StarTrek	TAS		Voyager
```
## search commands
Now search the transcripts. Here's the most basic command for searching:

```sh
grep -rin "<search term>" .
```

For example:

```sh
$ grep -rin "terraform.*venus" .
./scripts/DS9/200457.txt:401:O'BRIEN: All of it. The Utopia Planitia yards on Mars, the terraforming stations on Venus, Starfleet Headquarters. I'm not detecting a single sign of Starfleet activity anywhere in this sector.
```

For a better experience, use [The Silver Search (`ag`)](https://github.com/ggreer/the_silver_searcher) instead of `grep`

```sh
$ ag "terraform.*venus" .
scripts/DS9/200457.txt
401:O'BRIEN: All of it. The Utopia Planitia yards on Mars, the terraforming stations on Venus, Starfleet Headquarters. I'm not detecting a single sign of Starfleet activity anywhere in this sector.

```

Make this an easily used function by adding this to your `.bashrc` or `.zshrc`

```sh
function trekLines() {
	cd /path/to/star_trek_transcript_search/scripts/
	ag "${1}" .
}
```

Then just call `trekLines "terraform.*venus"` to do a search.

There's lots more things you can do as well.  Like count the number of lines per character per episode.  Or find the episode where each character spoke the fewest number of words. May update this with examples of how to do that later.