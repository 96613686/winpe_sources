# Microsoft.ReportingServices.Common.RSPerfCounterRes::get_MODELCACHEMISSPERSECOND

- ea: `0x16f0`
- end: `0x16fb`
- name: `Microsoft.ReportingServices.Common.RSPerfCounterRes::get_MODELCACHEMISSPERSECOND`
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

- `0x16f0`: `MODELCACHEMISSPERSECOND`

## pseudocode

```c

```

## disassembly

```asm
0x16f0  ldstr    aModelcachemiss_0// "MODELCACHEMISSPERSECOND"
0x16f5  call     string Keys::GetString(string key)
0x16fa  ret
```
