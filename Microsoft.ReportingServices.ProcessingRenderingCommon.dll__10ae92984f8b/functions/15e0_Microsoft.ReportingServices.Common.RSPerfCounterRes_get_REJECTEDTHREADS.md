# Microsoft.ReportingServices.Common.RSPerfCounterRes::get_REJECTEDTHREADS

- ea: `0x15e0`
- end: `0x15eb`
- name: `Microsoft.ReportingServices.Common.RSPerfCounterRes::get_REJECTEDTHREADS`
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

- `0x15e0`: `REJECTEDTHREADS`

## pseudocode

```c

```

## disassembly

```asm
0x15e0  ldstr    aRejectedthread// "REJECTEDTHREADS"
0x15e5  call     string Keys::GetString(string key)
0x15ea  ret
```
