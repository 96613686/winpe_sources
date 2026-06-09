# Microsoft.ReportingServices.Diagnostics.ScheduleStrings::WeeklyWithIntervalScheduleDescription

- ea: `0x105b0`
- end: `0x105c4`
- name: `Microsoft.ReportingServices.Diagnostics.ScheduleStrings::WeeklyWithIntervalScheduleDescription`
- size: `20`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x164c0`

## string_xrefs

- `0x105b0`: `WeeklyWithIntervalScheduleDescription`

## pseudocode

```c

```

## disassembly

```asm
0x105b0  ldstr    aWeeklywithinte// "WeeklyWithIntervalScheduleDescription"
0x105b5  ldarg.0
0x105b6  ldarg.1
0x105b7  ldarg.2
0x105b8  box      [mscorlib]System.Int64
0x105bd  ldarg.3
0x105be  call     string Keys::GetString(string key, object arg0, object arg1, object arg2, object arg3)
0x105c3  ret
```
