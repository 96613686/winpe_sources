# Microsoft.ReportingServices.Library.DatabaseUsernameSIDRefreshTimer::DoTimerAction

- ea: `0xfe30`
- end: `0xfe80`
- name: `Microsoft.ReportingServices.Library.DatabaseUsernameSIDRefreshTimer::DoTimerAction`
- size: `80`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x45d0`
- `0x7550`
- `0xfe30`

## string_xrefs

- `0xfe36`: `Starting catalog refresh of the username based on the SID timer`
- `0xfe75`: `Catalog refresh of the username based on the SID timer executed`

## pseudocode

```c

```

## disassembly

```asm
0xfe30  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.Global::m_Tracer
0xfe35  ldc.i4.4
0xfe36  ldstr    aStartingCatalo_0// "Starting catalog refresh of the usernam"...
0xfe3b  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xfe40  ldc.i4.1
0xfe41  ldc.i4   0x1000
0xfe46  newobj   instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::.ctor(valuetype [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionTransactionType, valuetype [System.Data]System.Data.IsolationLevel)
0xfe4b  stloc.0
0xfe4c  ldloc.0
0xfe4d  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::WillDisconnectStorage()
0xfe52  newobj   instance void Microsoft.ReportingServices.Library.DBInterface::.ctor()
0xfe57  dup
0xfe58  ldloc.0
0xfe59  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::set_ConnectionManager(class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager)
0xfe5e  callvirt instance void Microsoft.ReportingServices.Library.DBInterface::UpdateUsernameFromSID()
0xfe63  leave.s  loc_FE6F
0xfe65  ldloc.0
0xfe66  brfalse.s loc_FE6E
0xfe68  ldloc.0
0xfe69  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::DisconnectStorage()
0xfe6e  endfinally
0xfe6f  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.Global::m_Tracer
0xfe74  ldc.i4.4
0xfe75  ldstr    aCatalogRefresh// "Catalog refresh of the username based o"...
0xfe7a  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xfe7f  ret
```
