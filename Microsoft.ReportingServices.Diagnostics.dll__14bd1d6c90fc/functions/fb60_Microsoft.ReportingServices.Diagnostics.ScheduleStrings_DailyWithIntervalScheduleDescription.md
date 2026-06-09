# Microsoft.ReportingServices.Diagnostics.ScheduleStrings::DailyWithIntervalScheduleDescription

- ea: `0xfb60`
- end: `0xfb73`
- name: `Microsoft.ReportingServices.Diagnostics.ScheduleStrings::DailyWithIntervalScheduleDescription`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x10f30`

## string_xrefs

- `0xfb60`: `DailyWithIntervalScheduleDescription`

## pseudocode

```c

```

## disassembly

```asm
0xfb60  ldstr    aDailywithinter// "DailyWithIntervalScheduleDescription"
0xfb65  ldarg.0
0xfb66  ldarg.1
0xfb67  box      [mscorlib]System.Int64
0xfb6c  ldarg.2
0xfb6d  call     string Keys::GetString(string key, object arg0, object arg1, object arg2)
0xfb72  ret
```
