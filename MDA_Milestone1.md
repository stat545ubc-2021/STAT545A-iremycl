MDA-Milestone1
================
Irem YUCEL
09/10/2021

    ## ── Attaching packages ─────────────────────────────────────── tidyverse 1.3.1 ──

    ## ✓ ggplot2 3.3.5     ✓ purrr   0.3.4
    ## ✓ tibble  3.1.5     ✓ dplyr   1.0.7
    ## ✓ tidyr   1.1.3     ✓ stringr 1.4.0
    ## ✓ readr   2.0.2     ✓ forcats 0.5.1

    ## ── Conflicts ────────────────────────────────────────── tidyverse_conflicts() ──
    ## x dplyr::filter() masks stats::filter()
    ## x dplyr::lag()    masks stats::lag()

## Task 1: Choose your favorite dataset

#### 1.1 Out of the 7 datasets available in the datateachr package, choose 4 that appeal to you based on their description. Write your choices below:

##### 1: cancer\_sample

##### 2: vancouver\_trees

##### 3: steam\_games

##### 4: building\_permits

#### 1.2 One way to narrowing down your selection is to explore the datasets. Use your knowledge of dplyr to find out at least 3 attributes about each of these datasets (an attribute is something such as number of rows, variables, class type…). The goal here is to have an idea of what the data looks like.

### Cancer Dataset

``` r
glimpse(cancer_sample) 
```

    ## Rows: 569
    ## Columns: 32
    ## $ ID                      <dbl> 842302, 842517, 84300903, 84348301, 84358402, …
    ## $ diagnosis               <chr> "M", "M", "M", "M", "M", "M", "M", "M", "M", "…
    ## $ radius_mean             <dbl> 17.990, 20.570, 19.690, 11.420, 20.290, 12.450…
    ## $ texture_mean            <dbl> 10.38, 17.77, 21.25, 20.38, 14.34, 15.70, 19.9…
    ## $ perimeter_mean          <dbl> 122.80, 132.90, 130.00, 77.58, 135.10, 82.57, …
    ## $ area_mean               <dbl> 1001.0, 1326.0, 1203.0, 386.1, 1297.0, 477.1, …
    ## $ smoothness_mean         <dbl> 0.11840, 0.08474, 0.10960, 0.14250, 0.10030, 0…
    ## $ compactness_mean        <dbl> 0.27760, 0.07864, 0.15990, 0.28390, 0.13280, 0…
    ## $ concavity_mean          <dbl> 0.30010, 0.08690, 0.19740, 0.24140, 0.19800, 0…
    ## $ concave_points_mean     <dbl> 0.14710, 0.07017, 0.12790, 0.10520, 0.10430, 0…
    ## $ symmetry_mean           <dbl> 0.2419, 0.1812, 0.2069, 0.2597, 0.1809, 0.2087…
    ## $ fractal_dimension_mean  <dbl> 0.07871, 0.05667, 0.05999, 0.09744, 0.05883, 0…
    ## $ radius_se               <dbl> 1.0950, 0.5435, 0.7456, 0.4956, 0.7572, 0.3345…
    ## $ texture_se              <dbl> 0.9053, 0.7339, 0.7869, 1.1560, 0.7813, 0.8902…
    ## $ perimeter_se            <dbl> 8.589, 3.398, 4.585, 3.445, 5.438, 2.217, 3.18…
    ## $ area_se                 <dbl> 153.40, 74.08, 94.03, 27.23, 94.44, 27.19, 53.…
    ## $ smoothness_se           <dbl> 0.006399, 0.005225, 0.006150, 0.009110, 0.0114…
    ## $ compactness_se          <dbl> 0.049040, 0.013080, 0.040060, 0.074580, 0.0246…
    ## $ concavity_se            <dbl> 0.05373, 0.01860, 0.03832, 0.05661, 0.05688, 0…
    ## $ concave_points_se       <dbl> 0.015870, 0.013400, 0.020580, 0.018670, 0.0188…
    ## $ symmetry_se             <dbl> 0.03003, 0.01389, 0.02250, 0.05963, 0.01756, 0…
    ## $ fractal_dimension_se    <dbl> 0.006193, 0.003532, 0.004571, 0.009208, 0.0051…
    ## $ radius_worst            <dbl> 25.38, 24.99, 23.57, 14.91, 22.54, 15.47, 22.8…
    ## $ texture_worst           <dbl> 17.33, 23.41, 25.53, 26.50, 16.67, 23.75, 27.6…
    ## $ perimeter_worst         <dbl> 184.60, 158.80, 152.50, 98.87, 152.20, 103.40,…
    ## $ area_worst              <dbl> 2019.0, 1956.0, 1709.0, 567.7, 1575.0, 741.6, …
    ## $ smoothness_worst        <dbl> 0.1622, 0.1238, 0.1444, 0.2098, 0.1374, 0.1791…
    ## $ compactness_worst       <dbl> 0.6656, 0.1866, 0.4245, 0.8663, 0.2050, 0.5249…
    ## $ concavity_worst         <dbl> 0.71190, 0.24160, 0.45040, 0.68690, 0.40000, 0…
    ## $ concave_points_worst    <dbl> 0.26540, 0.18600, 0.24300, 0.25750, 0.16250, 0…
    ## $ symmetry_worst          <dbl> 0.4601, 0.2750, 0.3613, 0.6638, 0.2364, 0.3985…
    ## $ fractal_dimension_worst <dbl> 0.11890, 0.08902, 0.08758, 0.17300, 0.07678, 0…

``` r
summary(cancer_sample) #Summary function returns numeric summaries for each *numeric* variable (columns) in the dataset.
```

    ##        ID             diagnosis          radius_mean      texture_mean  
    ##  Min.   :     8670   Length:569         Min.   : 6.981   Min.   : 9.71  
    ##  1st Qu.:   869218   Class :character   1st Qu.:11.700   1st Qu.:16.17  
    ##  Median :   906024   Mode  :character   Median :13.370   Median :18.84  
    ##  Mean   : 30371831                      Mean   :14.127   Mean   :19.29  
    ##  3rd Qu.:  8813129                      3rd Qu.:15.780   3rd Qu.:21.80  
    ##  Max.   :911320502                      Max.   :28.110   Max.   :39.28  
    ##  perimeter_mean     area_mean      smoothness_mean   compactness_mean 
    ##  Min.   : 43.79   Min.   : 143.5   Min.   :0.05263   Min.   :0.01938  
    ##  1st Qu.: 75.17   1st Qu.: 420.3   1st Qu.:0.08637   1st Qu.:0.06492  
    ##  Median : 86.24   Median : 551.1   Median :0.09587   Median :0.09263  
    ##  Mean   : 91.97   Mean   : 654.9   Mean   :0.09636   Mean   :0.10434  
    ##  3rd Qu.:104.10   3rd Qu.: 782.7   3rd Qu.:0.10530   3rd Qu.:0.13040  
    ##  Max.   :188.50   Max.   :2501.0   Max.   :0.16340   Max.   :0.34540  
    ##  concavity_mean    concave_points_mean symmetry_mean    fractal_dimension_mean
    ##  Min.   :0.00000   Min.   :0.00000     Min.   :0.1060   Min.   :0.04996       
    ##  1st Qu.:0.02956   1st Qu.:0.02031     1st Qu.:0.1619   1st Qu.:0.05770       
    ##  Median :0.06154   Median :0.03350     Median :0.1792   Median :0.06154       
    ##  Mean   :0.08880   Mean   :0.04892     Mean   :0.1812   Mean   :0.06280       
    ##  3rd Qu.:0.13070   3rd Qu.:0.07400     3rd Qu.:0.1957   3rd Qu.:0.06612       
    ##  Max.   :0.42680   Max.   :0.20120     Max.   :0.3040   Max.   :0.09744       
    ##    radius_se        texture_se      perimeter_se       area_se       
    ##  Min.   :0.1115   Min.   :0.3602   Min.   : 0.757   Min.   :  6.802  
    ##  1st Qu.:0.2324   1st Qu.:0.8339   1st Qu.: 1.606   1st Qu.: 17.850  
    ##  Median :0.3242   Median :1.1080   Median : 2.287   Median : 24.530  
    ##  Mean   :0.4052   Mean   :1.2169   Mean   : 2.866   Mean   : 40.337  
    ##  3rd Qu.:0.4789   3rd Qu.:1.4740   3rd Qu.: 3.357   3rd Qu.: 45.190  
    ##  Max.   :2.8730   Max.   :4.8850   Max.   :21.980   Max.   :542.200  
    ##  smoothness_se      compactness_se      concavity_se     concave_points_se 
    ##  Min.   :0.001713   Min.   :0.002252   Min.   :0.00000   Min.   :0.000000  
    ##  1st Qu.:0.005169   1st Qu.:0.013080   1st Qu.:0.01509   1st Qu.:0.007638  
    ##  Median :0.006380   Median :0.020450   Median :0.02589   Median :0.010930  
    ##  Mean   :0.007041   Mean   :0.025478   Mean   :0.03189   Mean   :0.011796  
    ##  3rd Qu.:0.008146   3rd Qu.:0.032450   3rd Qu.:0.04205   3rd Qu.:0.014710  
    ##  Max.   :0.031130   Max.   :0.135400   Max.   :0.39600   Max.   :0.052790  
    ##   symmetry_se       fractal_dimension_se  radius_worst   texture_worst  
    ##  Min.   :0.007882   Min.   :0.0008948    Min.   : 7.93   Min.   :12.02  
    ##  1st Qu.:0.015160   1st Qu.:0.0022480    1st Qu.:13.01   1st Qu.:21.08  
    ##  Median :0.018730   Median :0.0031870    Median :14.97   Median :25.41  
    ##  Mean   :0.020542   Mean   :0.0037949    Mean   :16.27   Mean   :25.68  
    ##  3rd Qu.:0.023480   3rd Qu.:0.0045580    3rd Qu.:18.79   3rd Qu.:29.72  
    ##  Max.   :0.078950   Max.   :0.0298400    Max.   :36.04   Max.   :49.54  
    ##  perimeter_worst    area_worst     smoothness_worst  compactness_worst
    ##  Min.   : 50.41   Min.   : 185.2   Min.   :0.07117   Min.   :0.02729  
    ##  1st Qu.: 84.11   1st Qu.: 515.3   1st Qu.:0.11660   1st Qu.:0.14720  
    ##  Median : 97.66   Median : 686.5   Median :0.13130   Median :0.21190  
    ##  Mean   :107.26   Mean   : 880.6   Mean   :0.13237   Mean   :0.25427  
    ##  3rd Qu.:125.40   3rd Qu.:1084.0   3rd Qu.:0.14600   3rd Qu.:0.33910  
    ##  Max.   :251.20   Max.   :4254.0   Max.   :0.22260   Max.   :1.05800  
    ##  concavity_worst  concave_points_worst symmetry_worst   fractal_dimension_worst
    ##  Min.   :0.0000   Min.   :0.00000      Min.   :0.1565   Min.   :0.05504        
    ##  1st Qu.:0.1145   1st Qu.:0.06493      1st Qu.:0.2504   1st Qu.:0.07146        
    ##  Median :0.2267   Median :0.09993      Median :0.2822   Median :0.08004        
    ##  Mean   :0.2722   Mean   :0.11461      Mean   :0.2901   Mean   :0.08395        
    ##  3rd Qu.:0.3829   3rd Qu.:0.16140      3rd Qu.:0.3179   3rd Qu.:0.09208        
    ##  Max.   :1.2520   Max.   :0.29100      Max.   :0.6638   Max.   :0.20750

``` r
sapply(cancer_sample, class) #This line shows the class type of each variable in the dataset
```

    ##                      ID               diagnosis             radius_mean 
    ##               "numeric"             "character"               "numeric" 
    ##            texture_mean          perimeter_mean               area_mean 
    ##               "numeric"               "numeric"               "numeric" 
    ##         smoothness_mean        compactness_mean          concavity_mean 
    ##               "numeric"               "numeric"               "numeric" 
    ##     concave_points_mean           symmetry_mean  fractal_dimension_mean 
    ##               "numeric"               "numeric"               "numeric" 
    ##               radius_se              texture_se            perimeter_se 
    ##               "numeric"               "numeric"               "numeric" 
    ##                 area_se           smoothness_se          compactness_se 
    ##               "numeric"               "numeric"               "numeric" 
    ##            concavity_se       concave_points_se             symmetry_se 
    ##               "numeric"               "numeric"               "numeric" 
    ##    fractal_dimension_se            radius_worst           texture_worst 
    ##               "numeric"               "numeric"               "numeric" 
    ##         perimeter_worst              area_worst        smoothness_worst 
    ##               "numeric"               "numeric"               "numeric" 
    ##       compactness_worst         concavity_worst    concave_points_worst 
    ##               "numeric"               "numeric"               "numeric" 
    ##          symmetry_worst fractal_dimension_worst 
    ##               "numeric"               "numeric"

``` r
colSums(is.na(cancer_sample))#Number of missing values for each variable in steam games data
```

    ##                      ID               diagnosis             radius_mean 
    ##                       0                       0                       0 
    ##            texture_mean          perimeter_mean               area_mean 
    ##                       0                       0                       0 
    ##         smoothness_mean        compactness_mean          concavity_mean 
    ##                       0                       0                       0 
    ##     concave_points_mean           symmetry_mean  fractal_dimension_mean 
    ##                       0                       0                       0 
    ##               radius_se              texture_se            perimeter_se 
    ##                       0                       0                       0 
    ##                 area_se           smoothness_se          compactness_se 
    ##                       0                       0                       0 
    ##            concavity_se       concave_points_se             symmetry_se 
    ##                       0                       0                       0 
    ##    fractal_dimension_se            radius_worst           texture_worst 
    ##                       0                       0                       0 
    ##         perimeter_worst              area_worst        smoothness_worst 
    ##                       0                       0                       0 
    ##       compactness_worst         concavity_worst    concave_points_worst 
    ##                       0                       0                       0 
    ##          symmetry_worst fractal_dimension_worst 
    ##                       0                       0

The cancer dataset has 569 rows and 32 columns. \` \#\#\# Vancouver
Trees Data

``` r
glimpse(vancouver_trees) 
```

    ## Rows: 146,611
    ## Columns: 20
    ## $ tree_id            <dbl> 149556, 149563, 149579, 149590, 149604, 149616, 149…
    ## $ civic_number       <dbl> 494, 450, 4994, 858, 5032, 585, 4909, 4925, 4969, 7…
    ## $ std_street         <chr> "W 58TH AV", "W 58TH AV", "WINDSOR ST", "E 39TH AV"…
    ## $ genus_name         <chr> "ULMUS", "ZELKOVA", "STYRAX", "FRAXINUS", "ACER", "…
    ## $ species_name       <chr> "AMERICANA", "SERRATA", "JAPONICA", "AMERICANA", "C…
    ## $ cultivar_name      <chr> "BRANDON", NA, NA, "AUTUMN APPLAUSE", NA, "CHANTICL…
    ## $ common_name        <chr> "BRANDON ELM", "JAPANESE ZELKOVA", "JAPANESE SNOWBE…
    ## $ assigned           <chr> "N", "N", "N", "Y", "N", "N", "N", "N", "N", "N", "…
    ## $ root_barrier       <chr> "N", "N", "N", "N", "N", "N", "N", "N", "N", "N", "…
    ## $ plant_area         <chr> "N", "N", "4", "4", "4", "B", "6", "6", "3", "3", "…
    ## $ on_street_block    <dbl> 400, 400, 4900, 800, 5000, 500, 4900, 4900, 4900, 7…
    ## $ on_street          <chr> "W 58TH AV", "W 58TH AV", "WINDSOR ST", "E 39TH AV"…
    ## $ neighbourhood_name <chr> "MARPOLE", "MARPOLE", "KENSINGTON-CEDAR COTTAGE", "…
    ## $ street_side_name   <chr> "EVEN", "EVEN", "EVEN", "EVEN", "EVEN", "ODD", "ODD…
    ## $ height_range_id    <dbl> 2, 4, 3, 4, 2, 2, 3, 3, 2, 2, 2, 5, 3, 2, 2, 2, 2, …
    ## $ diameter           <dbl> 10.00, 10.00, 4.00, 18.00, 9.00, 5.00, 15.00, 14.00…
    ## $ curb               <chr> "N", "N", "Y", "Y", "Y", "Y", "Y", "Y", "Y", "Y", "…
    ## $ date_planted       <date> 1999-01-13, 1996-05-31, 1993-11-22, 1996-04-29, 19…
    ## $ longitude          <dbl> -123.1161, -123.1147, -123.0846, -123.0870, -123.08…
    ## $ latitude           <dbl> 49.21776, 49.21776, 49.23938, 49.23469, 49.23894, 4…

``` r
summary(vancouver_trees)
```

    ##     tree_id        civic_number    std_street         genus_name       
    ##  Min.   :    12   Min.   :    0   Length:146611      Length:146611     
    ##  1st Qu.: 65464   1st Qu.: 1306   Class :character   Class :character  
    ##  Median :134903   Median : 2604   Mode  :character   Mode  :character  
    ##  Mean   :131892   Mean   : 2937                                        
    ##  3rd Qu.:194450   3rd Qu.: 4005                                        
    ##  Max.   :266203   Max.   :17888                                        
    ##                                                                        
    ##  species_name       cultivar_name      common_name          assigned        
    ##  Length:146611      Length:146611      Length:146611      Length:146611     
    ##  Class :character   Class :character   Class :character   Class :character  
    ##  Mode  :character   Mode  :character   Mode  :character   Mode  :character  
    ##                                                                             
    ##                                                                             
    ##                                                                             
    ##                                                                             
    ##  root_barrier        plant_area        on_street_block  on_street        
    ##  Length:146611      Length:146611      Min.   :   0    Length:146611     
    ##  Class :character   Class :character   1st Qu.:1300    Class :character  
    ##  Mode  :character   Mode  :character   Median :2600    Mode  :character  
    ##                                        Mean   :2909                      
    ##                                        3rd Qu.:4000                      
    ##                                        Max.   :9900                      
    ##                                                                          
    ##  neighbourhood_name street_side_name   height_range_id     diameter     
    ##  Length:146611      Length:146611      Min.   : 0.000   Min.   :  0.00  
    ##  Class :character   Class :character   1st Qu.: 1.000   1st Qu.:  3.50  
    ##  Mode  :character   Mode  :character   Median : 2.000   Median :  9.00  
    ##                                        Mean   : 2.627   Mean   : 11.49  
    ##                                        3rd Qu.: 4.000   3rd Qu.: 16.50  
    ##                                        Max.   :10.000   Max.   :435.00  
    ##                                                                         
    ##      curb            date_planted          longitude         latitude    
    ##  Length:146611      Min.   :1989-10-27   Min.   :-123.2   Min.   :49.20  
    ##  Class :character   1st Qu.:1998-02-23   1st Qu.:-123.1   1st Qu.:49.23  
    ##  Mode  :character   Median :2004-01-28   Median :-123.1   Median :49.25  
    ##                     Mean   :2004-04-07   Mean   :-123.1   Mean   :49.25  
    ##                     3rd Qu.:2010-03-02   3rd Qu.:-123.1   3rd Qu.:49.26  
    ##                     Max.   :2019-07-03   Max.   :-123.0   Max.   :49.29  
    ##                     NA's   :76548        NA's   :22771    NA's   :22771

``` r
sapply(vancouver_trees, class)
```

    ##            tree_id       civic_number         std_street         genus_name 
    ##          "numeric"          "numeric"        "character"        "character" 
    ##       species_name      cultivar_name        common_name           assigned 
    ##        "character"        "character"        "character"        "character" 
    ##       root_barrier         plant_area    on_street_block          on_street 
    ##        "character"        "character"          "numeric"        "character" 
    ## neighbourhood_name   street_side_name    height_range_id           diameter 
    ##        "character"        "character"          "numeric"          "numeric" 
    ##               curb       date_planted          longitude           latitude 
    ##        "character"             "Date"          "numeric"          "numeric"

``` r
colSums(is.na(vancouver_trees))
```

    ##            tree_id       civic_number         std_street         genus_name 
    ##                  0                  0                  0                  0 
    ##       species_name      cultivar_name        common_name           assigned 
    ##                  0              67559                  0                  0 
    ##       root_barrier         plant_area    on_street_block          on_street 
    ##                  0               1486                  0                  0 
    ## neighbourhood_name   street_side_name    height_range_id           diameter 
    ##                  0                  0                  0                  0 
    ##               curb       date_planted          longitude           latitude 
    ##                  0              76548              22771              22771

Vancouver Trees dataset has 146,611 rows and 20 columns.

### Steam Games Data

``` r
glimpse(steam_games) 
```

    ## Rows: 40,833
    ## Columns: 21
    ## $ id                       <dbl> 1, 2, 3, 4, 5, 6, 7, 8, 9, 10, 11, 12, 13, 14…
    ## $ url                      <chr> "https://store.steampowered.com/app/379720/DO…
    ## $ types                    <chr> "app", "app", "app", "app", "app", "bundle", …
    ## $ name                     <chr> "DOOM", "PLAYERUNKNOWN'S BATTLEGROUNDS", "BAT…
    ## $ desc_snippet             <chr> "Now includes all three premium DLC packs (Un…
    ## $ recent_reviews           <chr> "Very Positive,(554),- 89% of the 554 user re…
    ## $ all_reviews              <chr> "Very Positive,(42,550),- 92% of the 42,550 u…
    ## $ release_date             <chr> "May 12, 2016", "Dec 21, 2017", "Apr 24, 2018…
    ## $ developer                <chr> "id Software", "PUBG Corporation", "Harebrain…
    ## $ publisher                <chr> "Bethesda Softworks,Bethesda Softworks", "PUB…
    ## $ popular_tags             <chr> "FPS,Gore,Action,Demons,Shooter,First-Person,…
    ## $ game_details             <chr> "Single-player,Multi-player,Co-op,Steam Achie…
    ## $ languages                <chr> "English,French,Italian,German,Spanish - Spai…
    ## $ achievements             <dbl> 54, 37, 128, NA, NA, NA, 51, 55, 34, 43, 72, …
    ## $ genre                    <chr> "Action", "Action,Adventure,Massively Multipl…
    ## $ game_description         <chr> "About This Game Developed by id software, th…
    ## $ mature_content           <chr> NA, "Mature Content Description  The develope…
    ## $ minimum_requirements     <chr> "Minimum:,OS:,Windows 7/8.1/10 (64-bit versio…
    ## $ recommended_requirements <chr> "Recommended:,OS:,Windows 7/8.1/10 (64-bit ve…
    ## $ original_price           <dbl> 19.99, 29.99, 39.99, 44.99, 0.00, NA, 59.99, …
    ## $ discount_price           <dbl> 14.99, NA, NA, NA, NA, 35.18, 70.42, 17.58, N…

``` r
summary(steam_games)
```

    ##        id            url               types               name          
    ##  Min.   :    1   Length:40833       Length:40833       Length:40833      
    ##  1st Qu.:10209   Class :character   Class :character   Class :character  
    ##  Median :20417   Mode  :character   Mode  :character   Mode  :character  
    ##  Mean   :20417                                                           
    ##  3rd Qu.:30625                                                           
    ##  Max.   :40833                                                           
    ##                                                                          
    ##  desc_snippet       recent_reviews     all_reviews        release_date      
    ##  Length:40833       Length:40833       Length:40833       Length:40833      
    ##  Class :character   Class :character   Class :character   Class :character  
    ##  Mode  :character   Mode  :character   Mode  :character   Mode  :character  
    ##                                                                             
    ##                                                                             
    ##                                                                             
    ##                                                                             
    ##   developer          publisher         popular_tags       game_details      
    ##  Length:40833       Length:40833       Length:40833       Length:40833      
    ##  Class :character   Class :character   Class :character   Class :character  
    ##  Mode  :character   Mode  :character   Mode  :character   Mode  :character  
    ##                                                                             
    ##                                                                             
    ##                                                                             
    ##                                                                             
    ##   languages          achievements        genre           game_description  
    ##  Length:40833       Min.   :   1.00   Length:40833       Length:40833      
    ##  Class :character   1st Qu.:  12.00   Class :character   Class :character  
    ##  Mode  :character   Median :  21.00   Mode  :character   Mode  :character  
    ##                     Mean   :  77.24                                        
    ##                     3rd Qu.:  38.00                                        
    ##                     Max.   :9821.00                                        
    ##                     NA's   :28639                                          
    ##  mature_content     minimum_requirements recommended_requirements
    ##  Length:40833       Length:40833         Length:40833            
    ##  Class :character   Class :character     Class :character        
    ##  Mode  :character   Mode  :character     Mode  :character        
    ##                                                                  
    ##                                                                  
    ##                                                                  
    ##                                                                  
    ##  original_price     discount_price  
    ##  Min.   :     0.0   Min.   :  0.00  
    ##  1st Qu.:     2.0   1st Qu.:  8.78  
    ##  Median :     5.0   Median : 19.98  
    ##  Mean   :    53.1   Mean   : 46.82  
    ##  3rd Qu.:    10.0   3rd Qu.: 43.92  
    ##  Max.   :730640.0   Max.   :962.60  
    ##  NA's   :5353       NA's   :26290

``` r
sapply(steam_games, summary)
```

    ## $id
    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##       1   10209   20417   20417   30625   40833 
    ## 
    ## $url
    ##    Length     Class      Mode 
    ##     40833 character character 
    ## 
    ## $types
    ##    Length     Class      Mode 
    ##     40833 character character 
    ## 
    ## $name
    ##    Length     Class      Mode 
    ##     40833 character character 
    ## 
    ## $desc_snippet
    ##    Length     Class      Mode 
    ##     40833 character character 
    ## 
    ## $recent_reviews
    ##    Length     Class      Mode 
    ##     40833 character character 
    ## 
    ## $all_reviews
    ##    Length     Class      Mode 
    ##     40833 character character 
    ## 
    ## $release_date
    ##    Length     Class      Mode 
    ##     40833 character character 
    ## 
    ## $developer
    ##    Length     Class      Mode 
    ##     40833 character character 
    ## 
    ## $publisher
    ##    Length     Class      Mode 
    ##     40833 character character 
    ## 
    ## $popular_tags
    ##    Length     Class      Mode 
    ##     40833 character character 
    ## 
    ## $game_details
    ##    Length     Class      Mode 
    ##     40833 character character 
    ## 
    ## $languages
    ##    Length     Class      Mode 
    ##     40833 character character 
    ## 
    ## $achievements
    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max.    NA's 
    ##    1.00   12.00   21.00   77.24   38.00 9821.00   28639 
    ## 
    ## $genre
    ##    Length     Class      Mode 
    ##     40833 character character 
    ## 
    ## $game_description
    ##    Length     Class      Mode 
    ##     40833 character character 
    ## 
    ## $mature_content
    ##    Length     Class      Mode 
    ##     40833 character character 
    ## 
    ## $minimum_requirements
    ##    Length     Class      Mode 
    ##     40833 character character 
    ## 
    ## $recommended_requirements
    ##    Length     Class      Mode 
    ##     40833 character character 
    ## 
    ## $original_price
    ##     Min.  1st Qu.   Median     Mean  3rd Qu.     Max.     NA's 
    ##      0.0      2.0      5.0     53.1     10.0 730640.0     5353 
    ## 
    ## $discount_price
    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max.    NA's 
    ##    0.00    8.78   19.98   46.82   43.92  962.60   26290

``` r
colSums(is.na(steam_games)) 
```

    ##                       id                      url                    types 
    ##                        0                        0                        2 
    ##                     name             desc_snippet           recent_reviews 
    ##                        2                       41                    35317 
    ##              all_reviews             release_date                developer 
    ##                     9553                        2                      342 
    ##                publisher             popular_tags             game_details 
    ##                     5100                      135                      520 
    ##                languages             achievements                    genre 
    ##                       36                    28639                      438 
    ##         game_description           mature_content     minimum_requirements 
    ##                      103                    35126                    16953 
    ## recommended_requirements           original_price           discount_price 
    ##                    16947                     5353                    26290

Steam Games dataset has 40,833 rows and 21 columns.

### Building Permits Data

``` r
glimpse(building_permits)
```

    ## Rows: 20,680
    ## Columns: 14
    ## $ permit_number               <chr> "BP-2016-02248", "BU468090", "DB-2016-0445…
    ## $ issue_date                  <date> 2017-02-01, 2017-02-01, 2017-02-01, 2017-…
    ## $ project_value               <dbl> 0, 0, 35000, 15000, 181178, 0, 15000, 0, 6…
    ## $ type_of_work                <chr> "Salvage and Abatement", "New Building", "…
    ## $ address                     <chr> "4378 W 9TH AVENUE, Vancouver, BC V6R 2C7"…
    ## $ project_description         <chr> NA, NA, NA, NA, NA, NA, NA, NA, NA, NA, NA…
    ## $ building_contractor         <chr> NA, NA, NA, "Mercury Contracting Ltd", "08…
    ## $ building_contractor_address <chr> NA, NA, NA, "88 W PENDER ST  \r\nUnit 2069…
    ## $ applicant                   <chr> "Raffaele & Associates DBA: Raffaele and A…
    ## $ applicant_address           <chr> "2642 East Hastings\r\nVancouver, BC  V5K …
    ## $ property_use                <chr> "Dwelling Uses", "Dwelling Uses", "Dwellin…
    ## $ specific_use_category       <chr> "One-Family Dwelling", "Multiple Dwelling"…
    ## $ year                        <dbl> 2017, 2017, 2017, 2017, 2017, 2017, 2017, …
    ## $ bi_id                       <dbl> 524, 535, 539, 541, 543, 546, 547, 548, 54…

``` r
summary(building_permits)
```

    ##  permit_number        issue_date         project_value       type_of_work      
    ##  Length:20680       Min.   :2017-01-03   Min.   :        0   Length:20680      
    ##  Class :character   1st Qu.:2017-09-25   1st Qu.:    10739   Class :character  
    ##  Mode  :character   Median :2018-07-18   Median :    48000   Mode  :character  
    ##                     Mean   :2018-07-24   Mean   :   609166                     
    ##                     3rd Qu.:2019-05-13   3rd Qu.:   217791                     
    ##                     Max.   :2020-04-29   Max.   :807185500                     
    ##                                          NA's   :52                            
    ##    address          project_description building_contractor
    ##  Length:20680       Length:20680        Length:20680       
    ##  Class :character   Class :character    Class :character   
    ##  Mode  :character   Mode  :character    Mode  :character   
    ##                                                            
    ##                                                            
    ##                                                            
    ##                                                            
    ##  building_contractor_address  applicant         applicant_address 
    ##  Length:20680                Length:20680       Length:20680      
    ##  Class :character            Class :character   Class :character  
    ##  Mode  :character            Mode  :character   Mode  :character  
    ##                                                                   
    ##                                                                   
    ##                                                                   
    ##                                                                   
    ##  property_use       specific_use_category      year          bi_id      
    ##  Length:20680       Length:20680          Min.   :2017   Min.   :    1  
    ##  Class :character   Class :character      1st Qu.:2017   1st Qu.: 5171  
    ##  Mode  :character   Mode  :character      Median :2018   Median :10340  
    ##                                           Mean   :2018   Mean   :10340  
    ##                                           3rd Qu.:2019   3rd Qu.:15510  
    ##                                           Max.   :2020   Max.   :20680  
    ## 

``` r
sapply(building_permits, summary)
```

    ## $permit_number
    ##    Length     Class      Mode 
    ##     20680 character character 
    ## 
    ## $issue_date
    ##         Min.      1st Qu.       Median         Mean      3rd Qu.         Max. 
    ## "2017-01-03" "2017-09-25" "2018-07-18" "2018-07-24" "2019-05-13" "2020-04-29" 
    ## 
    ## $project_value
    ##      Min.   1st Qu.    Median      Mean   3rd Qu.      Max.      NA's 
    ##         0     10739     48000    609166    217791 807185500        52 
    ## 
    ## $type_of_work
    ##    Length     Class      Mode 
    ##     20680 character character 
    ## 
    ## $address
    ##    Length     Class      Mode 
    ##     20680 character character 
    ## 
    ## $project_description
    ##    Length     Class      Mode 
    ##     20680 character character 
    ## 
    ## $building_contractor
    ##    Length     Class      Mode 
    ##     20680 character character 
    ## 
    ## $building_contractor_address
    ##    Length     Class      Mode 
    ##     20680 character character 
    ## 
    ## $applicant
    ##    Length     Class      Mode 
    ##     20680 character character 
    ## 
    ## $applicant_address
    ##    Length     Class      Mode 
    ##     20680 character character 
    ## 
    ## $property_use
    ##    Length     Class      Mode 
    ##     20680 character character 
    ## 
    ## $specific_use_category
    ##    Length     Class      Mode 
    ##     20680 character character 
    ## 
    ## $year
    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##    2017    2017    2018    2018    2019    2020 
    ## 
    ## $bi_id
    ##    Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
    ##       1    5171   10340   10340   15510   20680

``` r
colSums(is.na(building_permits))
```

    ##               permit_number                  issue_date 
    ##                           0                           0 
    ##               project_value                type_of_work 
    ##                          52                           0 
    ##                     address         project_description 
    ##                          22                        6734 
    ##         building_contractor building_contractor_address 
    ##                        8070                       11474 
    ##                   applicant           applicant_address 
    ##                           0                          30 
    ##                property_use       specific_use_category 
    ##                           5                           6 
    ##                        year                       bi_id 
    ##                           0                           0

Building Permits dataset has 20,680 rows and 14 columns

#### 1.3 Now that you’ve explored the 4 datasets that you were initially most interested in, let’s narrow it down to 2. What lead you to choose these 2? Briefly explain your choices below, and feel free to include any code in your explanation.

I chose Vancouver Trees and Building Permits dataset. The Cancer data
does not have many samples ( 569 ) and steam games data has many missing
values 26393.

#### 1.4 Time for the final decision\! Going back to the beginning, it’s important to have an end goal in mind. For example, if I had chosen the titanic dataset for my project, I might’ve wanted to explore the relationship between survival and other variables. Try to think of 1 research question that you would want to answer with each dataset. Note them down below, and make your final choice based on what seems more interesting to you\!

In the building permits dataset, I wanted the see the relationship
between project value and other few variables, such as postal code,
building contractor (there are 2566 contractors\!) and issue date.

## Task 2: Exploring your dataset

#### 2.1 Complete 4 out of the following 8 exercises to dive deeper into your data. All datasets are different and therefore, not all of these tasks may make sense for your data - which is why you should only answer 4. Use dplyr and ggplot.

#### 2.2 For each of the 4 exercises that you complete, provide a brief explanation of why you chose that exercise in relation to your data (in other words, why does it make sense to do that?), and sufficient comments for a reader to understand your reasoning and code.

## Plot the distribution of a numeric variable.

I want to look at the number of permits given in each year, and the
distribution of project\_value

``` r
ggplot(building_permits, aes(x = year)) +
  geom_histogram() 
```

    ## `stat_bin()` using `bins = 30`. Pick better value with `binwidth`.

![](MDA_Milestone1_files/figure-gfm/unnamed-chunk-6-1.png)<!-- -->

``` r
ggplot(building_permits, aes(x = project_value)) + 
  geom_histogram() 
```

    ## `stat_bin()` using `bins = 30`. Pick better value with `binwidth`.

    ## Warning: Removed 52 rows containing non-finite values (stat_bin).

![](MDA_Milestone1_files/figure-gfm/unnamed-chunk-6-2.png)<!-- --> This
graph doesnt look so good, so I need to arrange the data, so many 0s and
possibly NAs.

## Make a new tibble with a subset of your data, with variables and observations that you are interested in exploring.

Removing columns that I am not interested like contractor address or
applicant information, and selecting the ones I am interested in.

``` r
building_permits <- building_permits %>%
  select(issue_date, project_value,address, building_contractor,year)
```

## Create a new variable based on other variables in your data (only if it makes sense)

I want to investigate the relationship between project value and other
variables, one of which is Postal Code, so I am creating a new column
using the address column

``` r
building_permits <- building_permits %>% #remove rows containing NA in address column
  drop_na(address) 
length(grep("BC", building_permits$address)) == nrow(building_permits) # Each row in the address column contains BC, so we can use BC as the separator for the new column, which is PostalCodes.
```

    ## [1] TRUE

``` r
building_permits2 = building_permits %>%
  separate(address, c("adress", "PostalCode"), sep = "BC", remove = FALSE) %>% # create a new variable named PostalCode, separating the address column by BC
  select(-adress) #drop the other new created column

building_permits2[building_permits2 == ""] <- NA  #Replace the missing values  with NA, Some of the addresses do not have Postal Code indicated
  
sum(is.na(building_permits2$PostalCode)) #Number of missing values in the PostalCode
```

    ## [1] 2111

## Investigate how many missing values there are per variable. Can you find a way to plot this?

To look at the relationship between the variables I chose, I need to
remove the rows with NAs.

``` r
permit_nas <-tibble(vars = colnames(building_permits2), NumNAs = colSums(is.na(building_permits2))) #Create a new tibble showing the number of NAs in each variable
ggplot(permit_nas, aes(x = vars, y = NumNAs)) + # Using ggplot, plot the number of NAs
  geom_point() +
  geom_text(aes(label=NumNAs),hjust=0, vjust=0)+ #Label each point with NA count
  coord_flip() #Flip the coordinates so it is easier to read
```

![](MDA_Milestone1_files/figure-gfm/unnamed-chunk-9-1.png)<!-- -->

Now remove the rows containing NA values in Postal Code and Project
Value columns:

``` r
building_permits3 <- building_permits2 %>%
  drop_na(c(PostalCode, project_value))
```

## Filter observations in your data according to your own criteria.

I want to look at the relationship within a year:

``` r
building_permits3 %>% #Creating a tibble showing sample numbers per year:
  group_by(year) %>%
  summarise(n = n(), #Number of total samples
            na = sum(is.na(PostalCode)),#Number of NA values in Postal Code
            zero = sum(project_value == 0), # Number of 0s in Project Value
            sampleSize = n-na-zero) #Number of remainig samples
```

    ## # A tibble: 4 × 5
    ##    year     n    na  zero sampleSize
    ##   <dbl> <int> <int> <int>      <int>
    ## 1  2017  5887     0  1207       4680
    ## 2  2018  6128     0   956       5172
    ## 3  2019  5016     0   695       4321
    ## 4  2020  1474     0   217       1257

``` r
#The year 2018 has the most samples, so I will use the samples from that year.

building_permits_2018 <- building_permits3 %>%
  filter(year == 2018)
```

Explore the relationship between 2 variables in a plot. The relationship
between Postal Code and Project Value

``` r
#First clean the project value variable:

#Number of NAs:
sum(is.na(building_permits_2018$project_value))
```

    ## [1] 0

``` r
#Number of 0s:
sum(building_permits_2018$project_value == 0)
```

    ## [1] 956

``` r
building_permits_2018 =  building_permits_2018 %>% #Remove the 0s from data
  filter(project_value != 0) 

building_permits_2018 =  building_permits_2018 %>% # #Since we have so many postal codes, we can group the postal codes by FSA code ( First 3 letters of Postal code) so that we will have a more meaningful graph
  mutate(FSA = substr(PostalCode,1,4)) 


means <- building_permits_2018 %>% #Now grouping the data by FSA and getting the mean project value for each FCA
  group_by(FSA) %>%
  summarise(mean = mean(project_value)) %>%
  mutate(region = substr(FSA,1,3)) #Creating a region column to group the postal codes together.

#Finalyy, plot the relationship!

ggplot(means, aes(x = FSA, y = mean, colour = region)) +
   geom_point() +
   coord_flip()
```

![](MDA_Milestone1_files/figure-gfm/unnamed-chunk-12-1.png)<!-- -->

## Task 3: Write your research questions

1)  Is there a correlation between the building contractor and project
    value? Would that indicate the budget of the contractor?
2)  Can we see that some of buildings with certain postal code are more
    related to a certain specific use category?
3)  How did the project values change over time for regions with
    different postal code?
4)  Is there a relationship between project value and property use? eg.
    Does it cost more to build offices or houses?
