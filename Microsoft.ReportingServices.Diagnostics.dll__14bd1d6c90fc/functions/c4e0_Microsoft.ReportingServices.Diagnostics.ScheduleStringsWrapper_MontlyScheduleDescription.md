# Microsoft.ReportingServices.Diagnostics.ScheduleStringsWrapper::MontlyScheduleDescription

- ea: `0xc4e0`
- end: `0xc4ef`
- name: `Microsoft.ReportingServices.Diagnostics.ScheduleStringsWrapper::MontlyScheduleDescription`
- size: `15`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0xbe80`

## callees

- `0x10c40`

## string_xrefs

- `0xc4e0`: `MontlyScheduleDescription`

## pseudocode

```c

```

## disassembly

```asm
0xc4e0  ldstr    aMontlyschedule// "MontlyScheduleDescription"
0xc4e5  ldarg.0
0xc4e6  ldarg.1
0xc4e7  ldarg.2
0xc4e8  ldarg.3
0xc4e9  call     string Keys::GetString(string key, object arg0, object arg1, object arg2, object arg3)
0xc4ee  ret
```
