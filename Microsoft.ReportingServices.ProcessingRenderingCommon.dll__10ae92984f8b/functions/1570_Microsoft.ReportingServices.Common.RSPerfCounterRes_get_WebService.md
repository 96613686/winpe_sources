# Microsoft.ReportingServices.Common.RSPerfCounterRes::get_WebService

- ea: `0x1570`
- end: `0x157b`
- name: `Microsoft.ReportingServices.Common.RSPerfCounterRes::get_WebService`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x24d0`

## callees

- `0x15520`

## string_xrefs

- `0x1570`: `WebService`

## pseudocode

```c

```

## disassembly

```asm
0x1570  ldstr    aWebservice// "WebService"
0x1575  call     string Keys::GetString(string key)
0x157a  ret
```
