# Microsoft.ReportingServices.Common.RSPerfCounterRes::get_UPDATESCHEDULEEVENTSPROCESSED

- ea: `0x1800`
- end: `0x180b`
- name: `Microsoft.ReportingServices.Common.RSPerfCounterRes::get_UPDATESCHEDULEEVENTSPROCESSED`
- size: `11`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x2050`

## callees

- `0x15520`

## string_xrefs

- `0x1800`: `UPDATESCHEDULEEVENTSPROCESSED`

## pseudocode

```c

```

## disassembly

```asm
0x1800  ldstr    aUpdateschedule// "UPDATESCHEDULEEVENTSPROCESSED"
0x1805  call     string Keys::GetString(string key)
0x180a  ret
```
