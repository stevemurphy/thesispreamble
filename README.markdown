README

LaTeX thesis preamble

Created by Stephen Murphy on 2009-08-20

# Folder Contents

LaTeX preamble for use with thesis temple, intended for dissertation and other academic/research writing.

This file will need to be included in the LaTeX file created from the template, and sets most of the options required. The LaTeX document itself would typically be under version control, and the preamble.tex file would be used as a submodule of the Git repository.

Note that style files, BibTeX files etc would be in the texmf tree.

This folder is versioned with git.

# LaTeX Template

    %
    % LaTeX Template
    %
    % For UTS theses and assignments - by SM
    %

    \documentclass[11pt,oneside,a4paper,openright]{memoir}

    % Definitions
    \newcommand\mykeywords{} 
    \newcommand\myauthor{} 
    \newcommand\mytitle{}

    \newcommand\mydate{\today} % \today - or a fixed date e.g. 17 August 2009

    % Special cases for titlePW title page
    \newcommand\mycovertitle{\uppercase{} % \\[10pt] %
    %\large\uppercase{} \\[10pt] %
    %\normalsize\uppercase{} \\[20pt] S\lowercase{upervisor:}\\  %
    } % Multi-line title. uppercase has to be here

    \newcommand\mycoverauthor{\myauthor \\ \small{Student~No.~ \\[10pt] tel:\\  \\ email:\\ \urlstyle{same}\url{}}}

    \newcommand\myfaculty{Faculty of \\
        University of }


    \input{includes/preamble}


    %-----------------------------------------------------------------------
    %  Control included chapters here
    %-----------------------------------------------------------------------

    %\includeonly{onechapter} %Text from only one file with numbering etc of whole doc


    %%% BEGIN DOCUMENT

    \begin{document}

    % frontmatter goes here
    \input{includes/frontmatter_thesis} % everything
    % use any combo of below if not including all frontmatter
    %\input{includes/frontmatter_chapter}
    %\input{includes/frontmatter_toc}
    %\input{includes/frontmatter_abstract}


    %-----------------------------------------------------------------------
    % Begin thesis: use \include for each chapter as a separate file.
    %-----------------------------------------------------------------------

    \linespread{1.4}\small\normalsize % change linespacing for main part of doc
    \mainmatter

    \setcounter{secnumdepth}{-1}


    % chapter 1
    \include{chapter1} % Introduction

    % chapter 2
    %\include{chapter2} % Literature

    % chapter 3
    %\include{chapter3} % Methodology

    % chapter 4
    %\include{chapter4} % Data

    % chapter 5
    %\include{chapter5} % Analysis

    % chapter 6
    %\include{chapter6} % Conclusions


    %-----------------------------------------------------------------------
    % Appendices: use \appendix switch to change to appendices.
    %-----------------------------------------------------------------------

    %\appendix

    % First appendix
    %\include{appendix1}

    % Second Appendix
    %\include{appendix2}


    %-----------------------------------------------------------------------
    % Bibliography
    %-----------------------------------------------------------------------
    %\section{References}


    \urlstyle{same}
    \renewcommand{\bibname}{References} % Needs to be before bibliography command
    \bibliography{eddbib}        % expects file "eddbib.bib"


    %% To create indexes for TODOs etc, need to run these makeindex commands after LaTeXing:
    %% makeindex -o file.tnd file.tod
    %% makeindex -o file.fnd file.fix
    %% makeindex -o file.cnd file.chg

    %\printindex[todo]
    %\printindex[fixme]
    %\printindex[changed]

    \end{document}

# License

All files are written by and copyright Stephen Murphy <mailto:stephen.j.murphy@student.uts.edu.au>, although there have been many influences over the years affecting the final result. The idea of the TODO indexes comes from Mark Eli Kalderon -- see this blog [post](http://markelikalderon.com/blog/2008/11/23/latex-todo/).

Any and all of the author's rights are currently reserved.

The inspiration for using git to version this LaTeX document comes from Mark Eli Kalderon <mailto:eli@markelikalderon.com>. For more information, see this blog [post](http://markelikalderon.com/blog/2008/07/31/keeping-your-latex-preamble-in-a-git-submodule/).