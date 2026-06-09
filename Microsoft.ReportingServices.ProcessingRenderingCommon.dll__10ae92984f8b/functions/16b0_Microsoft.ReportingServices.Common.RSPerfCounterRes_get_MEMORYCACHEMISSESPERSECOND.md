# Microsoft.ReportingServices.Common.RSPerfCounterRes::get_MEMORYCACHEMISSESPERSECOND

- ea: `0x16b0`
- end: `0x16bb`
- name: `Microsoft.ReportingServices.Common.RSPerfCounterRes::get_MEMORYCACHEMISSESPERSECOND`
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

- `0x16b0`: `MEMORYCACHEMISSESPERSECOND`

## pseudocode

```c

```

## disassembly

```asm
0x16b0  ldstr    aMemorycachemis_0// "MEMORYCACHEMISSESPERSECOND"
0x16b5  call     string Keys::GetString(string key)
0x16ba  ret
```
