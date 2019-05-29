# AdGraph
**Abstract** — 
<p style="text-align: justify;">
User demand for blocking advertising and tracking online is large and growing. Existing tools, both deployed and described in research, have proven useful, but lack either the completeness or robustness needed for a general solution. Existing detection approaches generally focus on only one aspect of advertising or tracking (e.g. URL patterns, code structure), making existing approaches susceptible to evasion.

In this work we present AdGraph, a novel graph-based machine learning approach for detecting advertising and tracking resources on the web. AdGraph differs from existing approaches by building a graph representation of the HTML structure, network requests, and JavaScript behavior of a webpage, and using this unique representation to train a classifier for identifying advertising and tracking resources. Because AdGraph considers many aspects of the context a network request takes place in, it is less susceptible to the single-factor evasion techniques that flummox existing approaches.

We evaluate AdGraph on the Alexa top-10K websites, and find that it is highly accurate, able to replicate the labels of human-generated filter lists with 95.33% accuracy, and can even identify many mistakes in filter lists. We implement AdGraph as a modification to Chromium. AdGraph adds only minor overhead to page loading and execution, and is actually faster than stock Chromium on 42% of websites and AdBlock Plus on 78% of websites. Overall, we conclude that AdGraph is both accurate enough and performant enough for online use, breaking comparable or fewer websites than popular filter list based approaches.

</p>

**Please check our full paper for more details**

## Repository Structure

1. Binaries (from [`release` tab](https://github.com/uiowa-irl/AdGraph/releases), currently versioned `AdGraph-v1.0`)
```
── AdGraph-Linux.tar.gz (modified Chromium binary for Linux)
```
2. Source Code
```
├── LICENSE
├── README.md
├── patches
│   ├── patch.diff
│   └── v8_patch.diff
├── scripts
│   └── example_selenium_script.py
```
We provide both the binaries (**download them from GitHub's [`release` tab](https://github.com/uiowa-irl/AdGraph/releases)**) and source code (as Chromium patches) to allow for reproducibility and future extensions from research commiunity.

## Run Prebuilt Binary
Binaries are located in the **`release`** folder. Please follow the steps below to run them.

1. Unzip the folder `AdGraph-Linux.tar.gz` and simple run `chrome` with `--nosandbox` flag from command line 
```.\chrome --nosandbox```
2. To extract fine grained rendering details create a `CDATASection` element with text `NOTVERYUNIQUESTRING`
```document.createCDATASection('NOTVERYUNIQUESTRING');```
3. To extract/crawl a large number of webistes, a sample script is added in the `sacripts` folder

## Build From Scratch
