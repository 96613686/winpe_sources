# Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::WriteLog

- ea: `0x125c0`
- end: `0x125fa`
- name: `Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::WriteLog`
- size: `58`
- prototype: ``
- caller_count: `4`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x12480`
- `0x12490`
- `0x124a0`
- `0x124b0`

## callees

- `0x122c0`
- `0x124c0`
- `0x125c0`
- `0x12600`

## pseudocode

```c

```

## disassembly

```asm
0x125c0  ldarg.0
0x125c1  ldfld    bool Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::m_initialized
0x125c6  brtrue.s loc_125C9
0x125c8  ret
0x125c9  ldarg.0
0x125ca  ldfld    bool Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::m_writeEvents
0x125cf  brtrue.s loc_125D2
0x125d1  ret
0x125d2  ldarg.0
0x125d3  ldarg.2
0x125d4  call     instance bool Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::CanWrite(valuetype Microsoft.ReportingServices.Diagnostics.Event id)
0x125d9  brtrue.s loc_125DC
0x125db  ret
0x125dc  ldarg.0
0x125dd  ldarg.2
0x125de  call     instance valuetype Category Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::GetCategory(valuetype Microsoft.ReportingServices.Diagnostics.Event id)
0x125e3  stloc.0
0x125e4  ldarg.0
0x125e5  ldfld    class Microsoft.ReportingServices.Diagnostics.Utilities.IRSEventLogProvider Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::m_provider
0x125ea  ldarg.0
0x125eb  ldfld    string Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::m_sourceName
0x125f0  ldarg.1
0x125f1  ldarg.2
0x125f2  ldloc.0
0x125f3  ldarg.3
0x125f4  callvirt instance void Microsoft.ReportingServices.Diagnostics.Utilities.IRSEventLogProvider::WriteLog(string sourceName, valuetype [System]System.Diagnostics.EventLogEntryType type, valuetype Microsoft.ReportingServices.Diagnostics.Event evt, valuetype Category category, object[] args)
0x125f9  ret
```
