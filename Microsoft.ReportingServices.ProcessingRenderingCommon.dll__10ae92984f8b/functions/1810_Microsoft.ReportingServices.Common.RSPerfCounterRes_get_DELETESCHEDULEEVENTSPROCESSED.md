# Microsoft.ReportingServices.Common.RSPerfCounterRes::get_DELETESCHEDULEEVENTSPROCESSED

- ea: `0x1810`
- end: `0x181b`
- name: `Microsoft.ReportingServices.Common.RSPerfCounterRes::get_DELETESCHEDULEEVENTSPROCESSED`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x2050`

## callees

- `0x15520`

## string_xrefs

- `0x1810`: `DELETESCHEDULEEVENTSPROCESSED`

## pseudocode

```c

```

## disassembly

```asm
0x1810  ldstr    aDeleteschedule// "DELETESCHEDULEEVENTSPROCESSED"
0x1815  call     string Keys::GetString(string key)
0x181a  ret
```
