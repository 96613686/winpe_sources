# Microsoft.ReportingServices.Common.RSPerfCounterRes::get_MODELCACHEHITSPERSECOND

- ea: `0x16d0`
- end: `0x16db`
- name: `Microsoft.ReportingServices.Common.RSPerfCounterRes::get_MODELCACHEHITSPERSECOND`
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

- `0x16d0`: `MODELCACHEHITSPERSECOND`

## pseudocode

```c

```

## disassembly

```asm
0x16d0  ldstr    aModelcachehits_0// "MODELCACHEHITSPERSECOND"
0x16d5  call     string Keys::GetString(string key)
0x16da  ret
```
