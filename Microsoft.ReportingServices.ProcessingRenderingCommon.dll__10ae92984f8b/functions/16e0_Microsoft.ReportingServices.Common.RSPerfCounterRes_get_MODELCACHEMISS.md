# Microsoft.ReportingServices.Common.RSPerfCounterRes::get_MODELCACHEMISS

- ea: `0x16e0`
- end: `0x16eb`
- name: `Microsoft.ReportingServices.Common.RSPerfCounterRes::get_MODELCACHEMISS`
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

- `0x16e0`: `MODELCACHEMISS`

## pseudocode

```c

```

## disassembly

```asm
0x16e0  ldstr    aModelcachemiss// "MODELCACHEMISS"
0x16e5  call     string Keys::GetString(string key)
0x16ea  ret
```
