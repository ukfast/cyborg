# cyborg

A simple tool for testing availability of a given URI, utilising configurable concurrency

## Help

```
      --delay string         Optional delay per request
  -H, --header stringArray   Header(s) to use e.g. Accept: application/json
      --host string          Optional host header
  -k, --httpsskipverify      Specifies HTTPS insecure validation should be skipped
      --jsonbody string      JSON body of request
      --method string        HTTP method to use (default "GET")
      --uri string           URI to hit
      --workers int          Amount of workers (default 1)
```

## Environment

* `CYBORG_COLOUR`: Output log messages with colour

## Usage

Example usage:

> cyborg --uri https://ukfast.co.uk --delay 3s --workers 3


## Output

Example output:

```
2020/06/16 16:44:23 [Worker 3] Starting worker
2020/06/16 16:44:23 [Worker 3] Starting worker
2020/06/16 16:44:23 [Worker 3] Starting worker
2020/06/16 16:44:23 [Worker 3] Got result with status code [200] in [145.9957ms]
2020/06/16 16:44:23 [Worker 3] Got result with status code [200] in [145.9957ms]
2020/06/16 16:44:23 [Worker 3] Got result with status code [200] in [146.9981ms]
2020/06/16 16:44:24 [Worker 3] Got result with status code [200] in [92.9954ms]
2020/06/16 16:44:24 [Worker 3] Got result with status code [200] in [93.993ms]
2020/06/16 16:44:24 [Worker 3] Got result with status code [200] in [98.9922ms]
2020/06/16 16:44:26 [Worker 3] Got result with status code [200] in [176.9983ms]
2020/06/16 16:44:26 [Worker 3] Got result with status code [200] in [172.0018ms]
2020/06/16 16:44:26 [Worker 3] Got result with status code [200] in [177.9985ms]
2020/06/16 16:44:26 Caught interupt signal, instructing workers to stop
2020/06/16 16:44:27 [Worker 3] Worker stopped
2020/06/16 16:44:27 [Worker 3] Worker stopped
2020/06/16 16:44:27 [Worker 3] Worker stopped
2020/06/16 16:44:27 Executed [9] requests. Successful requests: 9, Failed requests: 0, Total execution time: 3.4349985s, Minimum request time: 92.9954ms, Maximum request time: 177.9985ms
```