# Microsoft.ReportingServices.Common.RSPerfCounterRes::get_MEMORYCACHEHITS

- ea: `0x1680`
- end: `0x168b`
- name: `Microsoft.ReportingServices.Common.RSPerfCounterRes::get_MEMORYCACHEHITS`
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

- `0x1680`: `MEMORYCACHEHITS`

## pseudocode

```c

```

## disassembly

```asm
0x1680  ldstr    aMemorycachehit// "MEMORYCACHEHITS"
0x1685  call     string Keys::GetString(string key)
0x168a  ret
```
