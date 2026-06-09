# Microsoft.ReportingServices.Common.RSPerfCounterRes::get_SharePointService

- ea: `0x1580`
- end: `0x158b`
- name: `Microsoft.ReportingServices.Common.RSPerfCounterRes::get_SharePointService`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2530`

## callees

- `0x15520`

## string_xrefs

- `0x1580`: `SharePointService`

## pseudocode

```c

```

## disassembly

```asm
0x1580  ldstr    aSharepointserv// "SharePointService"
0x1585  call     string Keys::GetString(string key)
0x158a  ret
```
