# Microsoft.ReportingServices.Common.RSPerfCounterRes::get_MEMORYCACHEMISSES

- ea: `0x16a0`
- end: `0x16ab`
- name: `Microsoft.ReportingServices.Common.RSPerfCounterRes::get_MEMORYCACHEMISSES`
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

- `0x16a0`: `MEMORYCACHEMISSES`

## pseudocode

```c

```

## disassembly

```asm
0x16a0  ldstr    aMemorycachemis// "MEMORYCACHEMISSES"
0x16a5  call     string Keys::GetString(string key)
0x16aa  ret
```
