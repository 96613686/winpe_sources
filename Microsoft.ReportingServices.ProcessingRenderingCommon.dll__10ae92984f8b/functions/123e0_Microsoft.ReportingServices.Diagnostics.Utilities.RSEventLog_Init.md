# Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::Init

- ea: `0x123e0`
- end: `0x12441`
- name: `Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::Init`
- size: `97`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x6130`
- `0x10150`
- `0x122b0`
- `0x123e0`
- `0x12450`

## string_xrefs

- `0x123ee`: `RSEvent log class being used and diaganostic dll was not initialized correctly.`

## pseudocode

```c

```

## disassembly

```asm
0x123e0  call     class Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_Configuration()
0x123e5  callvirt instance valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration::get_CurrentApplication()
0x123ea  ldc.i4.s 0xB
0x123ec  bne.un.s loc_123F9
0x123ee  ldstr    aRseventLogClas// "RSEvent log class being used and diagan"...
0x123f3  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x123f8  throw
0x123f9  ldarg.0
0x123fa  ldfld    bool Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::m_initialized
0x123ff  brfalse.s loc_12402
0x12401  ret
0x12402  ldarg.0
0x12403  ldarg.1
0x12404  stfld    class Microsoft.ReportingServices.Diagnostics.Utilities.IRSEventLogProvider Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::m_provider
0x12409  ldarg.0
0x1240a  ldarg.0
0x1240b  ldfld    class Microsoft.ReportingServices.Diagnostics.Utilities.IRSEventLogProvider Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::m_provider
0x12410  call     class Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_Configuration()
0x12415  callvirt instance valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration::get_CurrentApplication()
0x1241a  callvirt instance string Microsoft.ReportingServices.Diagnostics.Utilities.IRSEventLogProvider::GetEventSourceName(valuetype [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.RunningApplication application)
0x1241f  stfld    string Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::m_sourceName
0x12424  ldarg.0
0x12425  ldfld    string Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::m_sourceName
0x1242a  brtrue.s loc_12433
0x1242c  ldarg.0
0x1242d  ldc.i4.0
0x1242e  stfld    bool Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::m_writeEvents
0x12433  ldarg.0
0x12434  call     instance void Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::EnsureEventLogSourceInstalled()
0x12439  ldarg.0
0x1243a  ldc.i4.1
0x1243b  stfld    bool Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::m_initialized
0x12440  ret
```
