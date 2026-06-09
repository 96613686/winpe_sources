# Microsoft.ReportingServices.Common.RSPerfCounterRes::get_CACHEHITSPERSECOND

- ea: `0x1630`
- end: `0x163b`
- name: `Microsoft.ReportingServices.Common.RSPerfCounterRes::get_CACHEHITSPERSECOND`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1a10`

## callees

- `0x15520`

## string_xrefs

- `0x1630`: `CACHEHITSPERSECOND`

## pseudocode

```c

```

## disassembly

```asm
0x1630  ldstr    aCachehitsperse// "CACHEHITSPERSECOND"
0x1635  call     string Keys::GetString(string key)
0x163a  ret
```
