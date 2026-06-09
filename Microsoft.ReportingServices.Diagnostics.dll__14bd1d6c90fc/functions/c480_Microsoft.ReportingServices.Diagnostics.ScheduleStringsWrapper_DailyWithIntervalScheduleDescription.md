# Microsoft.ReportingServices.Diagnostics.ScheduleStringsWrapper::DailyWithIntervalScheduleDescription

- ea: `0xc480`
- end: `0xc493`
- name: `Microsoft.ReportingServices.Diagnostics.ScheduleStringsWrapper::DailyWithIntervalScheduleDescription`
- size: `19`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xbdf0`

## callees

- `0x10c20`

## string_xrefs

- `0xc480`: `DailyWithIntervalScheduleDescription`

## pseudocode

```c

```

## disassembly

```asm
0xc480  ldstr    aDailywithinter// "DailyWithIntervalScheduleDescription"
0xc485  ldarg.0
0xc486  ldarg.1
0xc487  box      [mscorlib]System.Int64
0xc48c  ldarg.2
0xc48d  call     string Keys::GetString(string key, object arg0, object arg1, object arg2)
0xc492  ret
```
