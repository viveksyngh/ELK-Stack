# Welcome to Logstash Tutorial

## Installation

*Add package to ubntu source list*
```
echo 'deb http://packages.elastic.co/logstash/2.2/debian stable main' | sudo tee /etc/apt/sources.list.d/logstash-2.2.x.list
```
*Update your apt package database*
```
sudo apt-get Update
```
*Install Logstash*
```
sudo apt-get install logstash
```
## Hello World

*Move to you logstash installation directory*
```
/opt/logstash
```
*Run basic logstash pipelie in command line*
```
bin/logstash -e 'input { stdin { } } output { stdout {} }'
```
*Once Pipeline start write Hello World in terminal*
```
hello world
2013-11-21T01:22:14.405+0000 0.0.0.0 hello world
```

## Logstash Pipeline
*A logstash pipeline has three elements*

1. Input
```
Input plugins consumes data from a source.
```
2. Filter
```
The filter plugins modify the data as you specify.
```
3. Output
```
The output plugins write the data to a destination
```

*Verify a logstash pipeline*
```
bin/logstash -f first-pipeline.conf --configtest
```
*Starting logstash*
```
bin/logstash -f first-pipeline.conf
```
*Testing with elastic search*
```
curl -XGET 'localhost:9200/logstash-$DATE/_search?q=response=200'
```
