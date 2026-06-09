# Microsoft.ReportingServices.Diagnostics.ScheduleStrings::MontlyDOWScheduleDescription

- ea: `0xfbd0`
- end: `0xfbe1`
- name: `Microsoft.ReportingServices.Diagnostics.ScheduleStrings::MontlyDOWScheduleDescription`
- size: `17`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x10f90`

## string_xrefs

- `0xfbd0`: `MontlyDOWScheduleDescription`

## pseudocode

```c

```

## disassembly

```asm
0xfbd0  ldstr    aMontlydowsched// "MontlyDOWScheduleDescription"
0xfbd5  ldarg.0
0xfbd6  ldarg.1
0xfbd7  ldarg.2
0xfbd8  ldarg.3
0xfbd9  ldarg.s  4
0xfbdb  call     string Keys::GetString(string key, object arg0, object arg1, object arg2, object arg3, object arg4)
0xfbe0  ret
```
