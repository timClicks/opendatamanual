==============================
Making Personal Data Anonymous
==============================

Governments hold lots of personally identifiable and commercially sensitive 
information. This sensitive information necessarily restricts agencies’ 
ability to share this information as open data. This article will go some 
way to introducing you to the option that you have to make it anonymous. 
Sometimes, just removing fields from a row is insufficient. It can be 
possible to use statistical techniques to identify individuals. This is 
especially the case when your data are combined with other sources of 
information.

Defining personal information
=============================

What counts?
------------

This question is more complicated than what one would initially believe. 
Every jurisdiction has its own requirements and and every culture has its 
own norms about what counts as personal and private.

Things to look out for
----------------------

Identifiers
-----------

Any number or other value that is used by a computer to identify individuals
can be examined by an attacker. Typical identifiers include registration 
numbers, ID numbers, passport numbers, credit card numbers, IP addresses, 
and order numberr.

Very rare characteristics
-------------------------

Outliers are very easy to identify in a statistical manner.

Very specific descriptions
--------------------------

Specific descriptions make it very easy to identify individuals. As specificity
increases, the number of individuals possessing a characteristic decreases. For 
example, there are fewer French than Europeans. While the specific information
can be valuable, be wary of its effects in very small population segments. 

Images
------

This can include photos of individuals, their property and other items of 
interest.

Biometric data
--------------

Biometric data are collected specifically to identify individuals. Therefore,
it is highly likely that they will be sensitive. Biometric data includes 
fingerprints, retina, DNA, height, body markings. It may also include 
samples of handwriting.

Free text
---------

Respondents’ free text responses very can often identify who has spoken.
Free text can be subject to word frequency analysis and other computational
linguistic analysis.

Strategies for making data anonymous
====================================

Aggregate
---------

When data are aggregated, they unable to be used to identify the sources of 
the data. That is, if we provide the mean household income for a street, we 
will not be able to identify the household income of any particular family. 
The downside of this approach is that aggregating data too far will impair 
analysts’ ability to interpret the data.

Remove
------

A very simple approach to privacy protection. Here, we simply remove some 
field of interest that was originally collected. For example, we could 
omit gender, age, location or any other variable that has been collected.

Dither
------

Dithering results means to add a variation to every value within a sample,
while attempting to maintain the integrity of the aggregate values. The 
goal is to prevent the the true value for any specific value to be deduced, 
but to enable statistical analysis to be carried out. For example, for 
geographic data, you could move points of interest to a random location 
within a given radius.

Top and Bottom Coding
---------------------

Top and bottom coding means to replace extreme values of sensitive numerical 
variables with the weighted group mean for those values in order to mask 
outlying values which are potentially identifying. For example if the data 
is about the airline industry in New Zealand results from Air New Zealand 
might be replaced with the weighted group mean for the values in the group 
of data in order to ensure that the results from Air New Zealand could not 
be identified.

From the `OECD`_:

    “It consists in setting top-codes or bottom-codes on quantitative 
    variables. A top-code for a variable is an upper limit on all 
    published values of that variable. Any value greater than this 
    upper limit is replaced by the upper limit or is not published 
    on the microdata file at all. Similarly, a bottom-code is a lower 
    limit on all published values for a variable. Different limits may 
    be used for different quantitative variables, or for different 
    subpopulations.” 


.. _OECD: http://stats.oecd.org/glossary/detail.asp?ID=7011

Group
-----

We can group multiple values together to protect individuals’ privacy. 
Consider the following table, with the transformation appearing in the 
right-hand column.

    ======    =========
    132 cm    139.67 cm
    143 cm    139.67 cm
    144 cm    139.67 cm
    144 cm    152 cm
    153 cm    152 cm
    159 cm    152 cm
    161 cm    164 cm
    167 cm    164 cm
    ======    =========


There may be problems with this approach, as you will impact on the 
median and other percentile values. 

Hash digests
------------

Using a crypographic hash of a string can make it impossible for 
someone to determine what the original string was, while being able
allow 3rd parties to check if strings they have are included. As
they can apply the hash function to their own values, they can 
undertake comparisons without being able to access data that they
don't already have. The transformation looks something like this:

    ======================  ================================
    researcher@example.org  c242dbe863aa0a38eacc72888fd41804
    consumer@example.com    a99650df0d55169e0d9f1dc17194830f
    ======================  ================================



References
==========


- http://www.ihsn.org/home/index.php?q=tools/anonymization/techniques
- http://latanyasweeney.org/work/identifiability.html
- http://www2.stats.govt.nz/domino/external/omni/omni.nsf/23f076d733ded7e74c256570001d92b4/9476cd9e52a1d515cc2572ca0009f8ca?OpenDocument
- http://stats.oecd.org/glossary/detail.asp?ID=7011

