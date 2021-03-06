
[![Travis build
status](https://travis-ci.org/JohnCoene/echarts4r.maps.svg?branch=master)](https://travis-ci.org/JohnCoene/echarts4r.maps)
<!-- README.md is generated from README.Rmd. Please edit that file -->

# echarts4r.maps

Includes:

  - 215 maps for [echarts4r](https://echarts4r.john-coene.com/).
  - A dataset of the latitude and longitude of all cities on planet
    earth with greater than 1000 people.

## Installation

Install `echarts4r`.

``` r
install.packages("echarts4r")
```

Then install `echarts4r.maps`

``` r
install.packages("remotes")
remotes::install_github('JohnCoene/echarts4r.maps')
```

## Example

Use in echarts4r

``` r
library(echarts4r)
library(echarts4r.maps)

df <- data.frame(
  x = c(
    "Rajasthan",
    "Gujarat",
    "Odisha"
  ), 
  y = 1:3
)

df %>% 
  e_charts(x) %>%
  em_map("India") %>% 
  e_map(y, map = "India") %>% 
  e_visual_map(y)

# cities
library(dplyr)
data("cities")

cities %>% 
  filter(country == "US") %>% 
  mutate(val = runif(n(), 1, 2)) %>% 
  e_charts(lon) %>%
  em_map("USA") %>% 
  e_geo(map = "USA") %>% 
  e_scatter(lat, val, coord_system = "geo", scale = NULL) %>% 
  e_visual_map(min = 1, max = 2)
```

## Bank

Another great resource for detailed maps is
[here](https://code.highcharts.com/mapdata/) (use with
`e_map_register`).

``` r
em_bank()
#>   [1] "Afghanistan"                                 
#>   [2] "Albania"                                     
#>   [3] "Algeria"                                     
#>   [4] "Andorra"                                     
#>   [5] "Angola"                                      
#>   [6] "Anguilla"                                    
#>   [7] "Antigua_and_Barbuda"                         
#>   [8] "Argentina"                                   
#>   [9] "Armenia"                                     
#>  [10] "Australia"                                   
#>  [11] "Austria"                                     
#>  [12] "Azerbaijan"                                  
#>  [13] "Bahrain"                                     
#>  [14] "Bangladesh"                                  
#>  [15] "Barbados"                                    
#>  [16] "Belarus"                                     
#>  [17] "Belgium"                                     
#>  [18] "Belize"                                      
#>  [19] "Benin"                                       
#>  [20] "Bermuda"                                     
#>  [21] "Bhutan"                                      
#>  [22] "Bolivia"                                     
#>  [23] "Bosnia_and_Herzegovina"                      
#>  [24] "Botswana"                                    
#>  [25] "Brazil"                                      
#>  [26] "British_Indian_Ocean_Territory"              
#>  [27] "British_Virgin_Islands"                      
#>  [28] "Brunei"                                      
#>  [29] "Bulgaria"                                    
#>  [30] "Burkina_Faso"                                
#>  [31] "Burundi"                                     
#>  [32] "Cambodia"                                    
#>  [33] "Cameroon"                                    
#>  [34] "Canada"                                      
#>  [35] "Cape_Verde"                                  
#>  [36] "Cayman_Islands"                              
#>  [37] "Central_African_Republic"                    
#>  [38] "Chad"                                        
#>  [39] "Chile"                                       
#>  [40] "China"                                       
#>  [41] "Colombia"                                    
#>  [42] "Comoros"                                     
#>  [43] "Congo-Brazzaville"                           
#>  [44] "Congo-Kinshasa"                              
#>  [45] "Cook_Islands"                                
#>  [46] "Coral_Sea_Islands_Territory"                 
#>  [47] "Costa_Rica"                                  
#>  [48] "Croatia"                                     
#>  [49] "Cuba"                                        
#>  [50] "Cyprus"                                      
#>  [51] "Czechia"                                     
#>  [52] "Denmark"                                     
#>  [53] "Djibouti"                                    
#>  [54] "Dominica"                                    
#>  [55] "Dominican_Republic"                          
#>  [56] "East_Timor"                                  
#>  [57] "Ecuador"                                     
#>  [58] "Egypt"                                       
#>  [59] "El_Salvador"                                 
#>  [60] "Equatorial_Guinea"                           
#>  [61] "Eritrea"                                     
#>  [62] "Estonia"                                     
#>  [63] "Ethiopia"                                    
#>  [64] "Falkland_Islands"                            
#>  [65] "Faroe_Islands"                               
#>  [66] "Federated_States_of_Micronesia"              
#>  [67] "Fiji"                                        
#>  [68] "Finland"                                     
#>  [69] "France"                                      
#>  [70] "Gabon"                                       
#>  [71] "Georgia"                                     
#>  [72] "Germany"                                     
#>  [73] "Ghana"                                       
#>  [74] "Gibraltar"                                   
#>  [75] "Greece"                                      
#>  [76] "Greenland"                                   
#>  [77] "Guatemala"                                   
#>  [78] "Guernsey"                                    
#>  [79] "Guinea-Bissau"                               
#>  [80] "Guinea"                                      
#>  [81] "Guyana"                                      
#>  [82] "Haiti"                                       
#>  [83] "Honduras"                                    
#>  [84] "Hungary"                                     
#>  [85] "Iceland"                                     
#>  [86] "India"                                       
#>  [87] "Indonesia"                                   
#>  [88] "Iraq"                                        
#>  [89] "Ireland"                                     
#>  [90] "Islamic_Republic_of_Iran"                    
#>  [91] "Isle_of_Man"                                 
#>  [92] "Israel"                                      
#>  [93] "Italy"                                       
#>  [94] "Jamaica"                                     
#>  [95] "Japan"                                       
#>  [96] "Jersey"                                      
#>  [97] "Jordan"                                      
#>  [98] "Juguang"                                     
#>  [99] "Kazakhstan"                                  
#> [100] "Kenya"                                       
#> [101] "Kiribati"                                    
#> [102] "Kuwait"                                      
#> [103] "Kyrgyzstan"                                  
#> [104] "Laos"                                        
#> [105] "Latvia"                                      
#> [106] "Lebanon"                                     
#> [107] "Lesotho"                                     
#> [108] "Liberia"                                     
#> [109] "Libya"                                       
#> [110] "Liechtenstein"                               
#> [111] "Lithuania"                                   
#> [112] "Luxemburg"                                   
#> [113] "Macedonia"                                   
#> [114] "Madagascar"                                  
#> [115] "Malawi"                                      
#> [116] "Malaysia"                                    
#> [117] "Maldives"                                    
#> [118] "Mali"                                        
#> [119] "Malta"                                       
#> [120] "Marshall_Islands"                            
#> [121] "Mauritania"                                  
#> [122] "Mauritius"                                   
#> [123] "Mexico"                                      
#> [124] "Moldova"                                     
#> [125] "Monaco"                                      
#> [126] "Mongolia"                                    
#> [127] "Montenegro"                                  
#> [128] "Montserrat"                                  
#> [129] "Morocco"                                     
#> [130] "Mozambique"                                  
#> [131] "Myanmar"                                     
#> [132] "Namibia"                                     
#> [133] "Nepal"                                       
#> [134] "New_Zealand"                                 
#> [135] "Nicaragua"                                   
#> [136] "Niger"                                       
#> [137] "Nigeria"                                     
#> [138] "Niue"                                        
#> [139] "North_Korea"                                 
#> [140] "Norway"                                      
#> [141] "Oman"                                        
#> [142] "Pakistan"                                    
#> [143] "Palau"                                       
#> [144] "Palestine"                                   
#> [145] "Panama"                                      
#> [146] "Papua_New_Guinea"                            
#> [147] "Paraguay"                                    
#> [148] "Peru"                                        
#> [149] "Philippines"                                 
#> [150] "Pitcairn_Islands"                            
#> [151] "Poland"                                      
#> [152] "Portugal"                                    
#> [153] "Qatar"                                       
#> [154] "Republic_of_Kosovo"                          
#> [155] "Romania"                                     
#> [156] "Russia"                                      
#> [157] "Russian_Federation"                          
#> [158] "Rwanda"                                      
#> [159] "Sahrawi_Arab_Democratic_Republic"            
#> [160] "Saint_Helena_Ascension_and_Tristan_da_Cunha" 
#> [161] "Saint_Kitts_and_Nevis"                       
#> [162] "Saint_Lucia"                                 
#> [163] "Saint_Vincent_and_the_Grenadines"            
#> [164] "Samoa"                                       
#> [165] "San_Marino"                                  
#> [166] "Saudi_Arabia"                                
#> [167] "Senegal"                                     
#> [168] "Serbia"                                      
#> [169] "Seychelles"                                  
#> [170] "Sierra_Leone"                                
#> [171] "Singapore"                                   
#> [172] "Slovakia"                                    
#> [173] "Slovenia"                                    
#> [174] "Solomon_Islands"                             
#> [175] "Somalia"                                     
#> [176] "South_Africa"                                
#> [177] "South_Georgia_and_the_South_Sandwich_Islands"
#> [178] "South_Korea"                                 
#> [179] "South_Sudan"                                 
#> [180] "Spain"                                       
#> [181] "Sri_Lanka"                                   
#> [182] "Sudan"                                       
#> [183] "Suriname"                                    
#> [184] "Swaziland"                                   
#> [185] "Sweden"                                      
#> [186] "Syria"                                       
#> [187] "Tajikistan"                                  
#> [188] "Tanzania"                                    
#> [189] "Thailand"                                    
#> [190] "The_Bahamas"                                 
#> [191] "The_Gambia"                                  
#> [192] "The_Netherlands"                             
#> [193] "Togo"                                        
#> [194] "Tokelau"                                     
#> [195] "Tonga"                                       
#> [196] "Trinidad_and_Tobago"                         
#> [197] "Tunisia"                                     
#> [198] "Turkey"                                      
#> [199] "Turkmenistan"                                
#> [200] "Turks_and_Caicos_Islands"                    
#> [201] "Tuvalu"                                      
#> [202] "Uganda"                                      
#> [203] "Ukraine"                                     
#> [204] "United_Arab_Emirates"                        
#> [205] "United_Kingdom"                              
#> [206] "Uruguay"                                     
#> [207] "USA"                                         
#> [208] "Uzbekistan"                                  
#> [209] "Vanuatu"                                     
#> [210] "Vatican_City"                                
#> [211] "Venezuela"                                   
#> [212] "Vietnam"                                     
#> [213] "Yemen"                                       
#> [214] "Zambia"                                      
#> [215] "Zimbabwe"
```
