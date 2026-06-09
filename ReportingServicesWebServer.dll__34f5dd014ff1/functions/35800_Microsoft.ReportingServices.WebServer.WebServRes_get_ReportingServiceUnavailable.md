# Microsoft.ReportingServices.WebServer.WebServRes::get_ReportingServiceUnavailable

- ea: `0x35800`
- end: `0x3580b`
- name: `Microsoft.ReportingServices.WebServer.WebServRes::get_ReportingServiceUnavailable`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x33100`

## callees

- `0x3cd30`

## string_xrefs

- `0x35800`: `ReportingServiceUnavailable`

## pseudocode

```c

```

## disassembly

```asm
0x35800  ldstr    aReportingservi// "ReportingServiceUnavailable"
0x35805  call     string Keys::GetString(string key)
0x3580a  ret
```
