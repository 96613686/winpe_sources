# Microsoft.ReportingServices.Diagnostics.ScheduleStrings::MinutesScheduleDescription

- ea: `0xfb30`
- end: `0xfb49`
- name: `Microsoft.ReportingServices.Diagnostics.ScheduleStrings::MinutesScheduleDescription`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x10f50`

## string_xrefs

- `0xfb30`: `MinutesScheduleDescription`

## pseudocode

```c

```

## disassembly

```asm
0xfb30  ldstr    aMinutesschedul// "MinutesScheduleDescription"
0xfb35  ldarg.0
0xfb36  box      [mscorlib]System.Int32
0xfb3b  ldarg.1
0xfb3c  box      [mscorlib]System.Int32
0xfb41  ldarg.2
0xfb42  ldarg.3
0xfb43  call     string Keys::GetString(string key, object arg0, object arg1, object arg2, object arg3)
0xfb48  ret
```
