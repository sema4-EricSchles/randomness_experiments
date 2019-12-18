# Exploration In Randomness

The goal of this set of experiments is to investigate the notion of randomness across various machine learning libraries and tasks.  The ultimate goal is to understand, does fixing a seed number help or matter?  Does it really lead to reproducibility?  How do results change as your seed changes?  

Typical datasets will be used from:

* Scikit-learn: https://scikit-learn.org/stable/datasets/index.html
* Seaborn: https://seaborn.pydata.org/generated/seaborn.load_dataset.html
* Kaggle: https://www.kaggle.com/ (no direct link, since there are so many)
* data.world: https://data.world/
* awesome-public-datasets: https://github.com/awesomedata/awesome-public-datasets
* nltk: https://www.nltk.org/book/ch02.html
* enigma: https://public.enigma.com/

I will investigate the following discrete questions.

Modeling work:

For each of the classifiers and regressors in Scikit-learn, Statsmodels, and a discrete set of Keras architectures, how does a random seed effect the performance, accuracy and generalizability of the model?

Discretly there will be two lines of high level questions here:

1. Do specific random seeds or ranges of random seeds work "well" for specific models with specific hyper parameters?

2. Is it "better" to use a randomly generated seed every time?  And if so, should that seed come from a specific distribution?  Or is a uniform random number best?

Within line of work one:  

A list of centered ranges will be investigated.  Each range will be checked against other ranges for performance and accuracy against _each_ configuration.  The results will be reviewed and compared against benchmarks.

Within line of work two:

Different distributions will be used to generate a random seed.  Then the same exercise in part one will be applied.  Results will be compared between part one and part two and general conclusions will be drawn.

It is imperative to understand where and how randomness is used on an implementation by implementation basis, this will inform how random seeds come into contact with the rest of the code.  It could be that a design choice in one library versus another _could_ effect how random seeds augment performance.  As always, the devil is in the details.  And therefore, a code review will also take place.  Then the author will attempt to re-implement from psuedo code each algorithm used.  There will be no guarantee of performance of speed from these reference implementations.  But the author will make every attempt to create as correct as possible an implementation.  The goal of these reference implementations is to understand how choice of code design and randomness inter-relate.  The final goal will be to understand how and if code design choices effect statistical performance and accuracy or inform assumptions of algorithms.  And if so, how, why and in what context?  Can we draw conclusions from randomness to how we interpret our results?  

Finally, a careful analysis of explainers will be treated from this context.  We want to know how explanations change when randomness changes.  Therefore the above analysis will be carried out for:

* LIME
* SHAP
* EL5

