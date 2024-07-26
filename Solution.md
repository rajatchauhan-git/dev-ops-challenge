## **Solution/Assignment 1**

https://d1yr670m6vsud2.cloudfront.net/

Second hosting throwing error

---

## **Solution/Assignment 2**

Script:

```bash
#!/bin/bash

if [[ $# -ne 1 ]]; then
    echo "Usage: $0 <path_to_logfile>"
    exit 1
fi

# Get the log file path
LOG_FILE="$1"

# Check if the log file exists
if [[ ! -f "$LOG_FILE" ]]; then
    echo "Log file not found at $LOG_FILE!"
    exit 1
fi

awk '{print $1}' "$LOG_FILE" | sort | uniq -c | sort -nr | head -n 8 | awk '{print $2, $1}'
```
---

## **Solution/Assignment 3**

High load average indicates the server is busy. To troubleshoot it on Linux Server we need to identify which processes consume the most resources and understand the nature of the system load.

1. Check System Resource Usage  (command: **top**)
2. Analyze Disk I/O (command: **iostat** or **iotop**)
3. Check for Resource Contention (**ps aux --sort=-%cpu** or **ps aux --sort=-%mem**)
   - ps aux --sort=-%cpu - it will look for high CPU
   - ps aux --sort=-%mem - it will look for high memory
4. Examine System Logs (command: **dmesg**)
