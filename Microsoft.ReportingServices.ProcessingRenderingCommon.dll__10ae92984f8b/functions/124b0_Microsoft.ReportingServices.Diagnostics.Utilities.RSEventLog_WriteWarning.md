# Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::WriteWarning

- ea: `0x124b0`
- end: `0x124ba`
- name: `Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::WriteWarning`
- size: `10`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x11b10`
- `0x11c90`
- `0x16a10`
- `0x17200`
- `0x17260`

## callees

- `0x125c0`

## pseudocode

```c

```

## disassembly

```asm
0x124b0  ldarg.0
0x124b1  ldc.i4.2
0x124b2  ldarg.1
0x124b3  ldarg.2
0x124b4  call     instance void Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::WriteLog(valuetype [System]System.Diagnostics.EventLogEntryType type, valuetype Microsoft.ReportingServices.Diagnostics.Event evt, object[] args)
0x124b9  ret
```
