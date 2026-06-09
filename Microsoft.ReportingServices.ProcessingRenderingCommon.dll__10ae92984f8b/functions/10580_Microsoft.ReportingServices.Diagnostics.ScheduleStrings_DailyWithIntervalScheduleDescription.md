# Microsoft.ReportingServices.Diagnostics.ScheduleStrings::DailyWithIntervalScheduleDescription

- ea: `0x10580`
- end: `0x10593`
- name: `Microsoft.ReportingServices.Diagnostics.ScheduleStrings::DailyWithIntervalScheduleDescription`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x164a0`

## string_xrefs

- `0x10580`: `DailyWithIntervalScheduleDescription`

## pseudocode

```c

```

## disassembly

```asm
0x10580  ldstr    aDailywithinter// "DailyWithIntervalScheduleDescription"
0x10585  ldarg.0
0x10586  ldarg.1
0x10587  box      [mscorlib]System.Int64
0x1058c  ldarg.2
0x1058d  call     string Keys::GetString(string key, object arg0, object arg1, object arg2)
0x10592  ret
```
