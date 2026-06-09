# Microsoft.ReportingServices.Common.RSPerfCounterRes::get_CACHEFLUSHESPERSECOND

- ea: `0x1780`
- end: `0x178b`
- name: `Microsoft.ReportingServices.Common.RSPerfCounterRes::get_CACHEFLUSHESPERSECOND`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2050`

## callees

- `0x15520`

## string_xrefs

- `0x1780`: `CACHEFLUSHESPERSECOND`

## pseudocode

```c

```

## disassembly

```asm
0x1780  ldstr    aCacheflushespe// "CACHEFLUSHESPERSECOND"
0x1785  call     string Keys::GetString(string key)
0x178a  ret
```
