latex
=====

This is a place where I am maintaining a few latex style files that might be of interest to someone else.  

Warning: These were originally created for very local purposes and not for public consumption.  
There may be some cruft and experimenation in these files that reflects this history.  Clean-up will 
depend on availability of my time and indication that anyone else is actually using these.

Here is a brief description of what these styles do.

 * authNote.sty -- provides a system for creating marginal indicators of end notes that can
 be used during the editing process and turned off before going to press
 * language.sty -- some syntax highlighting for languages like R
 * problems.sty -- a system for creating exercises and solutions
 * probstat.sty -- some macros for probability and statistics
 * sfsect.sty -- typeset section headers in sf font
 
The bin directory contains some utilities

  * knitr -- commandline Rnw -> PDF with multiple runs of latex and intermediaries as needed (written in bash)
  

*Added by DTK* ...

In order to tell the tex compiler where the sty files are located, you will want to give your system the relevant location information.

Suppose you put the .sty files in ~/tex/inputs/

On the command line (or in .bashrc or the equivalent), set the `TEXINPUTS` shell variable
```
TEXINPUTS=:.:$HOME/tex/inputs//:/usr/local/texlive/2011/texmf-dist/tex/latex//:/Applications/sage/local/share/texmf/tex//:$HOME/Sites/courses/cartoons//
TEXINPUTS=$TEXINPUTS:/Library/Frameworks/R.framework/Versions/Current/Resources/share/texmf//
```
Then run `texhash` from the shell. You may need to do this as super-user, e.g. `sudo texhash`

To tell RStudio where to find the .sty files, edit (or create) your `.Renviron` file to include a statement like the following
```
TEXINPUTS=.:/Users/rpruim/tex/inputs/:/usr/local/texlive/2011/texmf-dist/tex/latex/
```
Note that this file doesn't do ~ expansion, so you will have to give the full path name.  Since your name is probably not rpruim, you will want to change the above accordingly.
