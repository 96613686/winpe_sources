# Microsoft.ReportingServices.Common.RSPerfCounterRes::get_CACHEFLUSHES

- ea: `0x1770`
- end: `0x177b`
- name: `Microsoft.ReportingServices.Common.RSPerfCounterRes::get_CACHEFLUSHES`
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

- `0x1770`: `CACHEFLUSHES`

## pseudocode

```c

```

## disassembly

```asm
0x1770  ldstr    aCacheflushes// "CACHEFLUSHES"
0x1775  call     string Keys::GetString(string key)
0x177a  ret
```
