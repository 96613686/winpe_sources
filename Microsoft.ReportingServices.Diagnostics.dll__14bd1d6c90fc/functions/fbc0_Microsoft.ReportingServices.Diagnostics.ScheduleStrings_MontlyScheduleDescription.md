# Microsoft.ReportingServices.Diagnostics.ScheduleStrings::MontlyScheduleDescription

- ea: `0xfbc0`
- end: `0xfbcf`
- name: `Microsoft.ReportingServices.Diagnostics.ScheduleStrings::MontlyScheduleDescription`
- size: `15`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x10f50`

## string_xrefs

- `0xfbc0`: `MontlyScheduleDescription`

## pseudocode

```c

```

## disassembly

```asm
0xfbc0  ldstr    aMontlyschedule// "MontlyScheduleDescription"
0xfbc5  ldarg.0
0xfbc6  ldarg.1
0xfbc7  ldarg.2
0xfbc8  ldarg.3
0xfbc9  call     string Keys::GetString(string key, object arg0, object arg1, object arg2, object arg3)
0xfbce  ret
```
