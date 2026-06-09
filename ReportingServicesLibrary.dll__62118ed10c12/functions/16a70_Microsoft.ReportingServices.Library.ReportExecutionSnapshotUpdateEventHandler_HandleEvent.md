# Microsoft.ReportingServices.Library.ReportExecutionSnapshotUpdateEventHandler::HandleEvent

- ea: `0x16a70`
- end: `0x16acc`
- name: `Microsoft.ReportingServices.Library.ReportExecutionSnapshotUpdateEventHandler::HandleEvent`
- size: `92`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x16a70`

## string_xrefs

- `0x16a81`: `Creating notifications for report execution snapshot update event for report {0}`
- `0x16a95`: `CreateCacheUpdateNotifications`

## pseudocode

```c

```

## disassembly

```asm
0x16a70  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ScheduleTracer()
0x16a75  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceInfo()
0x16a7a  brfalse.s loc_16A95
0x16a7c  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ScheduleTracer()
0x16a81  ldstr    aCreatingNotifi// "Creating notifications for report execu"...
0x16a86  ldc.i4.1
0x16a87  newarr   [mscorlib]System.Object
0x16a8c  dup
0x16a8d  ldc.i4.0
0x16a8e  ldarg.3
0x16a8f  stelem.ref
0x16a90  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(string, object[])
0x16a95  ldstr    aCreatecacheupd// "CreateCacheUpdateNotifications"
0x16a9a  stloc.0
0x16a9b  newobj   instance void [mscorlib]System.Collections.Hashtable::.ctor()
0x16aa0  stloc.1
0x16aa1  ldloc.1
0x16aa2  ldstr    aReportid// "@ReportID"
0x16aa7  ldarg.3
0x16aa8  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x16aad  ldloc.1
0x16aae  ldstr    aLastruntime// "@LastRunTime"
0x16ab3  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x16ab8  box      [mscorlib]System.DateTime
0x16abd  callvirt instance void [mscorlib]System.Collections.Hashtable::Add(object, object)
0x16ac2  ldarg.1
0x16ac3  ldloc.0
0x16ac4  ldloc.1
0x16ac5  ldc.i4.4
0x16ac6  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Extensions.ICatalogQuery::ExecuteNonQuery(string, class [mscorlib]System.Collections.Hashtable, valuetype [System.Data]System.Data.CommandType)
0x16acb  ret
```
