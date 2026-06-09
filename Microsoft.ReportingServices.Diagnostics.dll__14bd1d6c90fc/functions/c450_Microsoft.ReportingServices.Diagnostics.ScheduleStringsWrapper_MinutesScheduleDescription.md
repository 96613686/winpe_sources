# Microsoft.ReportingServices.Diagnostics.ScheduleStringsWrapper::MinutesScheduleDescription

- ea: `0xc450`
- end: `0xc469`
- name: `Microsoft.ReportingServices.Diagnostics.ScheduleStringsWrapper::MinutesScheduleDescription`
- size: `25`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xbdb0`

## callees

- `0x10c40`

## string_xrefs

- `0xc450`: `MinutesScheduleDescription`

## pseudocode

```c

```

## disassembly

```asm
0xc450  ldstr    aMinutesschedul// "MinutesScheduleDescription"
0xc455  ldarg.0
0xc456  box      [mscorlib]System.Int32
0xc45b  ldarg.1
0xc45c  box      [mscorlib]System.Int32
0xc461  ldarg.2
0xc462  ldarg.3
0xc463  call     string Keys::GetString(string key, object arg0, object arg1, object arg2, object arg3)
0xc468  ret
```
