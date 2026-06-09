# Microsoft.ReportingServices.Diagnostics.ScheduleStringsWrapper::MontlyDOWScheduleDescription

- ea: `0xc4f0`
- end: `0xc501`
- name: `Microsoft.ReportingServices.Diagnostics.ScheduleStringsWrapper::MontlyDOWScheduleDescription`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xbed0`

## callees

- `0x10c80`

## string_xrefs

- `0xc4f0`: `MontlyDOWScheduleDescription`

## pseudocode

```c

```

## disassembly

```asm
0xc4f0  ldstr    aMontlydowsched// "MontlyDOWScheduleDescription"
0xc4f5  ldarg.0
0xc4f6  ldarg.1
0xc4f7  ldarg.2
0xc4f8  ldarg.3
0xc4f9  ldarg.s  4
0xc4fb  call     string Keys::GetString(string key, object arg0, object arg1, object arg2, object arg3, object arg4)
0xc500  ret
```
