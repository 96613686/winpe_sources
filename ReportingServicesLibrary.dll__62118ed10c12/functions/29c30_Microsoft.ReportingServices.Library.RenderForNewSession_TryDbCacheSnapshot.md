# Microsoft.ReportingServices.Library.RenderForNewSession::TryDbCacheSnapshot

- ea: `0x29c30`
- end: `0x29cc9`
- name: `Microsoft.ReportingServices.Library.RenderForNewSession::TryDbCacheSnapshot`
- size: `153`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `service_task, broker_com_uri`

## callees

- `0xcc30`
- `0x23bb0`
- `0x28bc0`
- `0x297a0`
- `0x29880`
- `0x298a0`
- `0x29c30`
- `0x2a820`
- `0x2a840`
- `0x2a880`
- `0x2a8a0`
- `0x2c690`
- `0x5fd60`
- `0x609c0`

## string_xrefs

- `0x29c47`: `Unable to cache report due to user dependency in query.`
- `0x29c5f`: `Unable to cache report due to data source option.`
- `0x29c7d`: `Adding report to execution cache.`

## pseudocode

```c

```

## disassembly

```asm
0x29c30  ldarg.1
0x29c31  callvirt instance class Microsoft.ReportingServices.Library.SnapshotManager Microsoft.ReportingServices.Library.RenderStrategyBase::get_SnapshotManager()
0x29c36  callvirt instance class Microsoft.ReportingServices.Library.ReportSnapshot Microsoft.ReportingServices.Library.SnapshotManager::get_ChunkTargetSnapshot()
0x29c3b  stloc.0
0x29c3c  ldarg.1
0x29c3d  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.UserProfileState Microsoft.ReportingServices.Library.RenderStrategyBase::get_UsedUserProfile()
0x29c42  ldc.i4.1
0x29c43  and
0x29c44  ldc.i4.1
0x29c45  bne.un.s loc_29C52
0x29c47  ldstr    aUnableToCacheR// "Unable to cache report due to user depe"...
0x29c4c  call     void Microsoft.ReportingServices.Library.ExecTrace::TraceVerbose(string message)
0x29c51  ret
0x29c52  ldarg.1
0x29c53  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.RuntimeDataSourceInfoCollection Microsoft.ReportingServices.Library.RenderStrategyBase::get_RuntimeDataSources()
0x29c58  call     bool Microsoft.ReportingServices.Library.DataSourceCatalogItem::GoodForUnattendedExecution(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.RuntimeDataSourceInfoCollection dataSources)
0x29c5d  brtrue.s loc_29C6A
0x29c5f  ldstr    aUnableToCacheR_0// "Unable to cache report due to data sour"...
0x29c64  call     void Microsoft.ReportingServices.Library.ExecTrace::TraceVerbose(string message)
0x29c69  ret
0x29c6a  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x29c6f  ldloc.0
0x29c70  ldnull
0x29c71  cgt.un
0x29c73  ldstr    aTargetsnapshot// "targetSnapshot"
0x29c78  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x29c7d  ldstr    aAddingReportTo// "Adding report to execution cache."
0x29c82  call     void Microsoft.ReportingServices.Library.ExecTrace::TraceVerbose(string message)
0x29c87  ldarg.1
0x29c88  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.UserProfileState Microsoft.ReportingServices.Library.RenderStrategyBase::get_UsedUserProfile()
0x29c8d  ldc.i4.2
0x29c8e  and
0x29c8f  brfalse.s loc_29CA1
0x29c91  ldstr    aMarkingSnapsho// "Marking snapshot as dependent on user."
0x29c96  call     void Microsoft.ReportingServices.Library.ExecTrace::TraceVerbose(string message)
0x29c9b  ldloc.0
0x29c9c  callvirt instance void Microsoft.ReportingServices.Library.ReportSnapshot::MarkAsDependentOnUser()
0x29ca1  ldarg.0
0x29ca2  call     instance class Microsoft.ReportingServices.Library.IExecutionDataProvider Microsoft.ReportingServices.Library.ReportExecutionBase::get_DataProvider()
0x29ca7  callvirt instance class Microsoft.ReportingServices.Library.IDBInterface Microsoft.ReportingServices.Library.IExecutionDataProvider::get_Storage()
0x29cac  ldarg.0
0x29cad  callvirt instance valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.ReportExecutionBase::get_ReportId()
0x29cb2  ldloc.0
0x29cb3  ldarg.0
0x29cb4  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.ReportExecutionBase::get_ExecutionDateTime()
0x29cb9  ldc.i4.0
0x29cba  ldloca.s 1
0x29cbc  callvirt instance void Microsoft.ReportingServices.Library.IDBInterface::AddReportToExecutionCache(valuetype [mscorlib]System.Guid reportId, class Microsoft.ReportingServices.Library.ReportSnapshot snapshotData, valuetype [mscorlib]System.DateTime executionDateTime, bool useEditSessionTimeout, [out] valuetype [mscorlib]System.DateTime& expirationDateTime)
0x29cc1  ldarg.1
0x29cc2  ldc.i4.1
0x29cc3  callvirt instance void Microsoft.ReportingServices.Library.RenderStrategyBase::set_SnapshotWasCached(bool value)
0x29cc8  ret
```
