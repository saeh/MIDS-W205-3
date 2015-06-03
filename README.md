Readme File

Questions:

Q1. & Q2. output directories attached

Q3. 
Run Locally Output:

root@ip-172-30-0-155:/home/ubuntu/cc-mrjob# time python absolutize_path.py < input/test-1.warc | python tag_counter.py --conf-path mrjob.conf --no-output --output-dir out
No configs specified for inline runner
reading from STDIN
creating tmp directory /tmp/tag_counter.root.20150603.103211.978308
writing to /tmp/tag_counter.root.20150603.103211.978308/step-0-mapper_part-00000
Loading local file /home/ubuntu/cc-mrjob/common-crawl/crawl-data/CC-MAIN-2014-35/segments/1408500800168.29/warc/CC-MAIN-20140820021320-00000-ip-10-180-136-8.ec2.internal.warc.gz
Counters from step 1:
  commoncrawl:
    processed_pages: 42040
    processed_records: 129958
writing to /tmp/tag_counter.root.20150603.103211.978308/step-0-mapper-sorted
> sort /tmp/tag_counter.root.20150603.103211.978308/step-0-mapper_part-00000
writing to /tmp/tag_counter.root.20150603.103211.978308/step-0-reducer_part-00000
Counters from step 1:
  commoncrawl:
    processed_pages: 42040
    processed_records: 129958
Moving /tmp/tag_counter.root.20150603.103211.978308/step-0-reducer_part-00000 -> out/part-00000
removing tmp directory /tmp/tag_counter.root.20150603.103211.978308

real    1m15.574s
user    1m14.029s
sys     0m1.555s




Run EMR job Output:

root@ip-172-30-0-155:/home/ubuntu/cc-mrjob# time python tag_counter.py -r emr --conf-path mrjob.conf --python-archive mrcc.py.tar.gz --no-output --output-dir s3://cc-mr-test/cc-test-1 --source s3 input/test-1.warc
using existing scratch bucket mrjob-8382fcc9e7a06929
using s3://mrjob-8382fcc9e7a06929/tmp/ as our scratch dir on S3
creating tmp directory /tmp/tag_counter.root.20150603.103625.243538
writing wrapper script to /tmp/tag_counter.root.20150603.103625.243538/setup-wrapper.sh
writing master bootstrap script to /tmp/tag_counter.root.20150603.103625.243538/b.py
Copying non-input files into s3://mrjob-8382fcc9e7a06929/tmp/tag_counter.root.20150603.103625.243538/files/
Waiting 5.0s for S3 eventual consistency
Creating Elastic MapReduce job flow
Job flow created with ID: j-1AUWG181JQ8ME
Created new job flow j-1AUWG181JQ8ME
Job launched 30.1s ago, status STARTING: Provisioning Amazon EC2 capacity
Job launched 60.2s ago, status STARTING: Provisioning Amazon EC2 capacity
Job launched 90.3s ago, status STARTING: Provisioning Amazon EC2 capacity
Job launched 120.5s ago, status STARTING: Provisioning Amazon EC2 capacity
Job launched 150.6s ago, status STARTING: Provisioning Amazon EC2 capacity
Job launched 180.7s ago, status STARTING: Provisioning Amazon EC2 capacity
Job launched 210.8s ago, status STARTING: Provisioning Amazon EC2 capacity
Job launched 241.0s ago, status STARTING: Provisioning Amazon EC2 capacity
Job launched 271.1s ago, status STARTING: Provisioning Amazon EC2 capacity
Job launched 301.2s ago, status STARTING: Provisioning Amazon EC2 capacity
Job launched 331.4s ago, status STARTING: Provisioning Amazon EC2 capacity
Job launched 361.5s ago, status STARTING: Provisioning Amazon EC2 capacity
Job launched 391.6s ago, status STARTING: Provisioning Amazon EC2 capacity
Job launched 421.7s ago, status STARTING: Provisioning Amazon EC2 capacity
Job launched 451.9s ago, status STARTING: Provisioning Amazon EC2 capacity
Job launched 482.0s ago, status STARTING: Provisioning Amazon EC2 capacity
Job launched 512.1s ago, status STARTING: Provisioning Amazon EC2 capacity
Job launched 542.3s ago, status STARTING: Provisioning Amazon EC2 capacity
Job launched 572.4s ago, status STARTING: Provisioning Amazon EC2 capacity
Job launched 602.5s ago, status STARTING: Provisioning Amazon EC2 capacity
Job launched 632.7s ago, status STARTING: Provisioning Amazon EC2 capacity
Job launched 662.8s ago, status STARTING: Provisioning Amazon EC2 capacity
Job launched 693.0s ago, status STARTING: Provisioning Amazon EC2 capacity
Job launched 723.1s ago, status STARTING: Provisioning Amazon EC2 capacity
Job launched 753.3s ago, status STARTING: Provisioning Amazon EC2 capacity
Job launched 783.5s ago, status STARTING: Provisioning Amazon EC2 capacity
Job launched 813.6s ago, status STARTING: Provisioning Amazon EC2 capacity
Job launched 843.7s ago, status STARTING: Provisioning Amazon EC2 capacity
Job launched 873.9s ago, status STARTING: Provisioning Amazon EC2 capacity
Job launched 904.0s ago, status STARTING: Configuring cluster software
Job launched 934.1s ago, status STARTING: Configuring cluster software
Job launched 964.2s ago, status STARTING: Configuring cluster software
Job launched 994.4s ago, status BOOTSTRAPPING: Running bootstrap actions
Job launched 1024.5s ago, status BOOTSTRAPPING: Running bootstrap actions
Job launched 1054.6s ago, status RUNNING: Running step
Job launched 1084.8s ago, status RUNNING: Running step
Job launched 1114.9s ago, status RUNNING: Running step (tag_counter.root.20150603.103625.243538: Step 1 of 1)
Job launched 1145.1s ago, status RUNNING: Running step (tag_counter.root.20150603.103625.243538: Step 1 of 1)
Job launched 1175.2s ago, status RUNNING: Running step (tag_counter.root.20150603.103625.243538: Step 1 of 1)
Job launched 1205.3s ago, status RUNNING: Running step (tag_counter.root.20150603.103625.243538: Step 1 of 1)
Job launched 1235.5s ago, status RUNNING: Running step (tag_counter.root.20150603.103625.243538: Step 1 of 1)
Job launched 1265.6s ago, status RUNNING: Running step (tag_counter.root.20150603.103625.243538: Step 1 of 1)
Job launched 1295.7s ago, status RUNNING: Running step (tag_counter.root.20150603.103625.243538: Step 1 of 1)
Job launched 1325.8s ago, status RUNNING: Running step (tag_counter.root.20150603.103625.243538: Step 1 of 1)
Job launched 1356.0s ago, status RUNNING: Running step (tag_counter.root.20150603.103625.243538: Step 1 of 1)
Job launched 1386.1s ago, status RUNNING: Running step (tag_counter.root.20150603.103625.243538: Step 1 of 1)
Job completed.
Running time was 288.0s (not counting time spent waiting for the EC2 instances)
ec2_key_pair_file not specified, going to S3
Fetching counters from S3...
Waiting 5.0s for S3 eventual consistency
Counters from step 1:
  (no counters found)
removing tmp directory /tmp/tag_counter.root.20150603.103625.243538
Removing all files in s3://mrjob-8382fcc9e7a06929/tmp/tag_counter.root.20150603.103625.243538/
Removing all files in s3://mrjob-8382fcc9e7a06929/tmp/logs/j-1AUWG181JQ8ME/
Terminating job flow: j-1AUWG181JQ8ME

real    23m53.225s
user    0m1.330s
sys     0m0.103s


The EMR job takes 288s of actual processing compared to locally only 75s.

Q4. There are 2042 instances of address as found in the output file.

Q5. The two processes produce the same output.
