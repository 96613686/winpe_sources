# Microsoft.ReportingServices.Diagnostics.ScheduleStrings::MontlyDOWScheduleDescription

- ea: `0x105f0`
- end: `0x10601`
- name: `Microsoft.ReportingServices.Diagnostics.ScheduleStrings::MontlyDOWScheduleDescription`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x16500`

## string_xrefs

- `0x105f0`: `MontlyDOWScheduleDescription`

## pseudocode

```c

```

## disassembly

```asm
0x105f0  ldstr    aMontlydowsched// "MontlyDOWScheduleDescription"
0x105f5  ldarg.0
0x105f6  ldarg.1
0x105f7  ldarg.2
0x105f8  ldarg.3
0x105f9  ldarg.s  4
0x105fb  call     string Keys::GetString(string key, object arg0, object arg1, object arg2, object arg3, object arg4)
0x10600  ret
```
