# Microsoft.ReportingServices.Common.RSPerfCounterRes::get_CREATESCHEDULEEVENTSPROCESSED

- ea: `0x17f0`
- end: `0x17fb`
- name: `Microsoft.ReportingServices.Common.RSPerfCounterRes::get_CREATESCHEDULEEVENTSPROCESSED`
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

- `0x17f0`: `CREATESCHEDULEEVENTSPROCESSED`

## pseudocode

```c

```

## disassembly

```asm
0x17f0  ldstr    aCreateschedule// "CREATESCHEDULEEVENTSPROCESSED"
0x17f5  call     string Keys::GetString(string key)
0x17fa  ret
```
