# Microsoft.ReportingServices.Common.RSPerfCounterRes::get_MEMORYCACHEHITSPERSECOND

- ea: `0x1690`
- end: `0x169b`
- name: `Microsoft.ReportingServices.Common.RSPerfCounterRes::get_MEMORYCACHEHITSPERSECOND`
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

- `0x1690`: `MEMORYCACHEHITSPERSECOND`

## pseudocode

```c

```

## disassembly

```asm
0x1690  ldstr    aMemorycachehit_0// "MEMORYCACHEHITSPERSECOND"
0x1695  call     string Keys::GetString(string key)
0x169a  ret
```
