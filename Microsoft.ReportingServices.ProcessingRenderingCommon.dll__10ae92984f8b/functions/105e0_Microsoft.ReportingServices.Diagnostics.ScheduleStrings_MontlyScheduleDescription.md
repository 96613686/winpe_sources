# Microsoft.ReportingServices.Diagnostics.ScheduleStrings::MontlyScheduleDescription

- ea: `0x105e0`
- end: `0x105ef`
- name: `Microsoft.ReportingServices.Diagnostics.ScheduleStrings::MontlyScheduleDescription`
- size: `15`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x164c0`

## string_xrefs

- `0x105e0`: `MontlyScheduleDescription`

## pseudocode

```c

```

## disassembly

```asm
0x105e0  ldstr    aMontlyschedule// "MontlyScheduleDescription"
0x105e5  ldarg.0
0x105e6  ldarg.1
0x105e7  ldarg.2
0x105e8  ldarg.3
0x105e9  call     string Keys::GetString(string key, object arg0, object arg1, object arg2, object arg3)
0x105ee  ret
```
