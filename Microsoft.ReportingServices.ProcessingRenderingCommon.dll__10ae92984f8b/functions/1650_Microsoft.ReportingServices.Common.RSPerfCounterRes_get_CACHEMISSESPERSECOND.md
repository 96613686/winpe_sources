# Microsoft.ReportingServices.Common.RSPerfCounterRes::get_CACHEMISSESPERSECOND

- ea: `0x1650`
- end: `0x165b`
- name: `Microsoft.ReportingServices.Common.RSPerfCounterRes::get_CACHEMISSESPERSECOND`
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

- `0x1650`: `CACHEMISSESPERSECOND`

## pseudocode

```c

```

## disassembly

```asm
0x1650  ldstr    aCachemissesper// "CACHEMISSESPERSECOND"
0x1655  call     string Keys::GetString(string key)
0x165a  ret
```
