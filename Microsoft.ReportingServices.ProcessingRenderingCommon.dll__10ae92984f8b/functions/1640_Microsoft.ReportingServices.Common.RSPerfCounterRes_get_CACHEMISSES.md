# Microsoft.ReportingServices.Common.RSPerfCounterRes::get_CACHEMISSES

- ea: `0x1640`
- end: `0x164b`
- name: `Microsoft.ReportingServices.Common.RSPerfCounterRes::get_CACHEMISSES`
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

- `0x1640`: `CACHEMISSES`

## pseudocode

```c

```

## disassembly

```asm
0x1640  ldstr    aCachemisses// "CACHEMISSES"
0x1645  call     string Keys::GetString(string key)
0x164a  ret
```
