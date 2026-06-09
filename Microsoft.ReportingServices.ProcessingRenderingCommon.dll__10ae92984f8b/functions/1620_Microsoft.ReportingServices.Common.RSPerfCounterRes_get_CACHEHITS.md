# Microsoft.ReportingServices.Common.RSPerfCounterRes::get_CACHEHITS

- ea: `0x1620`
- end: `0x162b`
- name: `Microsoft.ReportingServices.Common.RSPerfCounterRes::get_CACHEHITS`
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

- `0x1620`: `CACHEHITS`

## pseudocode

```c

```

## disassembly

```asm
0x1620  ldstr    aCachehits// "CACHEHITS"
0x1625  call     string Keys::GetString(string key)
0x162a  ret
```
