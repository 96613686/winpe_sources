# Microsoft.ReportingServices.Diagnostics.ScheduleStrings::MinutesScheduleDescription

- ea: `0x10550`
- end: `0x10569`
- name: `Microsoft.ReportingServices.Diagnostics.ScheduleStrings::MinutesScheduleDescription`
- size: `25`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x164c0`

## string_xrefs

- `0x10550`: `MinutesScheduleDescription`

## pseudocode

```c

```

## disassembly

```asm
0x10550  ldstr    aMinutesschedul// "MinutesScheduleDescription"
0x10555  ldarg.0
0x10556  box      [mscorlib]System.Int32
0x1055b  ldarg.1
0x1055c  box      [mscorlib]System.Int32
0x10561  ldarg.2
0x10562  ldarg.3
0x10563  call     string Keys::GetString(string key, object arg0, object arg1, object arg2, object arg3)
0x10568  ret
```
