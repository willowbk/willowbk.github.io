---
permalink: /
title: "Biophysics in Network Science, Molecular Evolution, Stochastic Processes, and Optimization"
excerpt: "I am a researcher near completion of my Ph.D in Physics & Astronomy studying various topics in the field of biological physics."
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---
The field of biophysics covers a vast umbrella of topics. During my graduate career I have delved into several subfields of this enormous science with the hope to grasp the mysteries of life on a fundamental level. This has been attempted primarily through the avenues of complex network science and inference, molecular evolution and population genetics modeling, the study of stochastic processes and even objective function optimization. The following sections overview some of the work I have completed in the last few years on these topics.

Complex Networks
====

The instances of [complex networks](https://en.wikipedia.org/wiki/Complex_network) in the life sciences are endless. Examples include protein interaction networks, neural networks, networks of predator-prey interactions, etc. In my own research, I have focused on weighted, undirected networks, the main contribution being a general Bayesian formalism for generating estimators of global network properties after sampling only a very small portion of the entire system, $<1\%$. The method of sampling is via [random walk](https://en.wikipedia.org/wiki/Random_walk), e.i. after a single node is examined a random neighbor is chosen as the next sample, and this process is continued until the number of desired samples is attained.  

According to this Bayesian formalism, the estimator for the network-wide average connectivity, denoted $\langle c \rangle$, is given by

\begin{aligned}
\widehat{\langle c \rangle} = \frac{\ell}{\sum_c \mathcal{K}_c / c},
\end{aligned}

where $\ell$ is the sample size, and $\mathcal{K}_c$ is the number of visits to nodes with connectivity $c$. This can be compared to what is typically done when nodes are sampled uniformly:

\begin{aligned}
\widehat{\langle c \rangle} = \frac{\sum_c c \mathcal{K}_c}{\ell}.
\end{aligned}

This formalism also establishes a rigorous error analysis which yields a high probability range for these estimators. For this particular quantity, this error range falls off as $\sim 1/\sqrt{\ell},$ independent of the network size! This estimator captures the true value long before the diffusive process of the random walk reaches equilibrium. For further detail and many other examples of estimators of network properties, including one for the full network size, see [this paper](https://willowbk.github.io/publication/RapidBayesianInference).

Epidemiology
====
A clear example of a complex network in the life sciences is one which describes a geographical region through which a pathogen might spread. This could be the network of all major cities in the world, with dynamical links representing traffic between each city, or the network of all major airports, etc. Although this is a dynamical network with time-dependent properties upon which the disease spreads, random walk sampling is indeed applicable given a "rapid-enough" sampling process. Such a network has been sampled both in [this poster](https://willowbk.github.io/talks/NetworkInferencePoster) and [this paper](https://willowbk.github.io/publication/RapidBayesianInference) and the fraction of nodes (cities) infected accurately estimated. This then suggests a new method for tracking the spread of diseases such as the recent Ebola outbreak.

Cancer Research
====
Although in its early stages, I have begun a project to use the network sampling methodology to determine which groups of genes are responsible for the metabolism of cancerous cells. More to come on this topic in the near future!


<!--
Network Science 
======
Complex networks describe a broad spectrum of systems in nature, science, technology, and society. Many of these networks are large and evolving, making
investigation of their statistical properties a challenging task. In particular, estimating the network size becomes non-trivial if the network is too large to visit every node. Consequently, predicting various network statistics, typically from random samples of limited size, has attracted considerable attention in the
literature.

This research project has consisted of the development of a Bayesian theoretical framework for network sampling by random walks (RWs). Unlike previous results, this framework can be used to build
posterior probability distributions for any network node-based quantity of interest. This approach reproduces several previously known global network statistics estimators within a single formalism,
automatically removes statistical biases caused by RW sampling, and yields standard results in the uniform sampling limit. Surprisingly, accurate estimates of various network properties, including its size, are obtained
after examining only a small fraction of all network nodes.

The effectiveness of this formalism has been demonstrated not only on standard $\textit{in silico}$ networks, but additonally has been shown to have applications in epidemiology, and has reproduced known statistics of the network formed by links between pages on Wikipedia.
-->



<!---
A data-driven personal website
======
just be sure to save the markdown files! Finally, you can also write scripts that process the structured data on the site, such as [this one](https://github.com/academicpages/academicpages.github.io/blob/master/talkmap.ipynb) that analyzes metadata in pages about talks to display [a map of every location you've given a talk](https://academicpages.github.io/talkmap.html).

Getting started
======
1. Set site-wide configuration and create content & metadata (see below -- also see [this set of diffs](http://archive.is/3TPas) showing what files were changed to set up [an example site](https://getorg-testacct.github.io) for a user with the username "getorg-testacct")
1. Upload any files (like PDFs, .zip files, etc.) to the files/ directory. They will appear at https://[your GitHub username].github.io/files/example.pdf.  
1. Check status by going to the repository settings, in the "GitHub pages" section

Site-wide configuration
------
The main configuration file for the site is in the base directory in [_config.yml](https://github.com/academicpages/academicpages.github.io/blob/master/_config.yml), which defines the content in the sidebars and other site-wide features. You will need to replace the default variables with ones about yourself and your site's github repository. The configuration file for the top menu is in [_data/navigation.yml](https://github.com/academicpages/academicpages.github.io/blob/master/_data/navigation.yml). For example, if you don't have a portfolio or blog posts, you can remove those items from that navigation.yml file to remove them from the header. 

Create content & metadata
------
For site content, there is one markdown file for each type of content, which are stored in directories like _publications, _talks, _posts, _teaching, or _pages. For example, each talk is a markdown file in the [_talks directory](https://github.com/academicpages/academicpages.github.io/tree/master/_talks). At the top of each markdown file is structured data in YAML about the talk, which the theme will parse to do lots of cool stuff. The same structured data about a talk is used to generate the list of talks on the [Talks page](https://academicpages.github.io/talks), each [individual page](https://academicpages.github.io/talks/2012-03-01-talk-1) for specific talks, the talks section for the [CV page](https://academicpages.github.io/cv), and the [map of places you've given a talk](https://academicpages.github.io/talkmap.html) (if you run this [python file](https://github.com/academicpages/academicpages.github.io/blob/master/talkmap.py) or [Jupyter notebook](https://github.com/academicpages/academicpages.github.io/blob/master/talkmap.ipynb), which creates the HTML for the map based on the contents of the _talks directory).

**Markdown generator**

I have also created [a set of Jupyter notebooks](https://github.com/academicpages/academicpages.github.io/tree/master/markdown_generator
) that converts a CSV containing structured data about talks or presentations into individual markdown files that will be properly formatted for the academicpages template. The sample CSVs in that directory are the ones I used to create my own personal website at stuartgeiger.com. My usual workflow is that I keep a spreadsheet of my publications and talks, then run the code in these notebooks to generate the markdown files, then commit and push them to the GitHub repository.

How to edit your site's GitHub repository
------
Many people use a git client to create files on their local computer and then push them to GitHub's servers. If you are not familiar with git, you can directly edit these configuration and markdown files directly in the github.com interface. Navigate to a file (like [this one](https://github.com/academicpages/academicpages.github.io/blob/master/_talks/2012-03-01-talk-1.md) and click the pencil icon in the top right of the content preview (to the right of the "Raw | Blame | History" buttons). You can delete a file by clicking the trashcan icon to the right of the pencil icon. You can also create new files or upload files by navigating to a directory and clicking the "Create new file" or "Upload files" buttons. 

Example: editing a markdown file for a talk
![Editing a markdown file for a talk](/images/editing-talk.png)

For more info
------
More info about configuring academicpages can be found in [the guide](https://academicpages.github.io/markdown/). The [guides for the Minimal Mistakes theme](https://mmistakes.github.io/minimal-mistakes/docs/configuration/) (which this theme was forked from) might also be helpful.
--->
