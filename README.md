## TPCN: A novel terpenoids database embedded with content
## Overview
To gain unique insights into the quantitative diversity of natural products, we have developed the first content-embedded database of terpenoids (TPCN). This database can be accessed through a web-based computational toolkit available at http://www.tpcn.pro/. By conducting meticulous manual searches and analyzing over 10 thousand reference papers, the TPCN database has successfully integrated 6383 terpenoids obtained from 1,254 distinct plant species. It encompasses exhaustive details including isolation parts, comprehensive molecule structures, CAS numbers, and 7,508 content descriptions.
![image text](https://github.com/ylchen0622/TPCN/blob/main/TPCN.png "DBSCAN Performance Comparison")
## Environment
1. python == 3.7.0
2. rdkit == 2020.09.1
3. numpy == 1.19.2
4. pandas == 1.3.5
5. matplotlib == 3.5.2
## Codes
### >>> 0 data preparation
Normalize structures and filter out compounds without structures
### >>> 1 compound distribution
It provides a comprehensive description of the distribution of terpenoids from different perspectives, including structural type, biological source, extraction part, and content.
#### 1.1 category distribution
Category distribution of terpenoids.
#### 1.2 part distribution
Part distribution of terpenoids. The distribution of each category of terpenoids in different parts was also calculated.
#### 1.3 species distribution
The distribution of terpenoids from different family and species.
#### 1.4 content distribution
The content distribution of terpenoids. We segmented the content into seven ranges: 10-6% to 10-5%, 10-5% to 10-4%, 10-4% to 10-3%, 10-3% to 10-2%, 10-2% to 10-1%, 10-1% to 1% and 1% to 10%. The number of terpenoids in each content range was counted.
### >>> 2 scaffold analysis
Murcko scaffolds of terpenoids from different content ranges were generated using RDKit.
### >>> 3 property analysis
11 physicochemical properties of terpenoids were calculated by RDKit. And the average value of the physicochemical properties of terpenoids from different content ranges was calculated.
### >>> 4 glycosylation analysis
Deglycoside processing of terpenoids in the TPCN database.
* SRU parameters:
java -jar "SugarRemovalUtility-jar-with-dependencies.jar" -i "filename" -t "3" -remTerm "false" -presMode "1" -oxyAtomsThres "0.4"
### >>> 5 similarity analysis
#### 5.1 Similarity analysis (Calculation)
Using RDKit to calculate the similarity between terpenoids in the TPCN database based on Daylight fingerprint and Tanimoto coefficient.
#### 5.2 Similarity analysis (heatmap)
Generating a heatmap of similarities between terpenoids in the TPCN database.
#### 5.3 Similarity analysis (threshold)
Extract terpenoids with a similarity greater than 0.95 in the TPCN database and add content information to them.
#### 5.4 Similarity Analysis (Statistics)
Calculate the content differences among terpenoids in the TPCN database with similarity exceeding 0.95.
#### 5.5 Similarity analysis (important natural products)
Extract terpenoids and their content information in the TPCN database that have a similarity of more than 0.95 to specified compounds.
