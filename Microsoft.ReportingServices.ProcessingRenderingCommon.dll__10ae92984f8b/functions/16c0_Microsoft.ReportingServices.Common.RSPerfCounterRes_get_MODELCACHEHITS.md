# Microsoft.ReportingServices.Common.RSPerfCounterRes::get_MODELCACHEHITS

- ea: `0x16c0`
- end: `0x16cb`
- name: `Microsoft.ReportingServices.Common.RSPerfCounterRes::get_MODELCACHEHITS`
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

- `0x16c0`: `MODELCACHEHITS`

## pseudocode

```c

```

## disassembly

```asm
0x16c0  ldstr    aModelcachehits// "MODELCACHEHITS"
0x16c5  call     string Keys::GetString(string key)
0x16ca  ret
```
