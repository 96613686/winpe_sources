# Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::LogExecutionLogInfo

- ea: `0x6650`
- end: `0x6738`
- name: `Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::LogExecutionLogInfo`
- size: `232`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x6640`

## callees

- `0x1e10`
- `0x6650`
- `0x126e0`

## pseudocode

```c

```

## disassembly

```asm
0x6650  ldc.i4.0
0x6651  ldc.i4   0x1000
0x6656  newobj   instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::.ctor(valuetype [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionTransactionType, valuetype [System.Data]System.Data.IsolationLevel)
0x665b  stloc.0
0x665c  ldloc.0
0x665d  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::WillDisconnectStorage()
0x6662  ldarg.1
0x6663  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::get_UserContext()
0x6668  newobj   instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.DBInterface::.ctor(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext)
0x666d  dup
0x666e  ldloc.0
0x666f  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::set_ConnectionManager(class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager)
0x6674  ldarg.0
0x6675  call     string [mscorlib]System.Environment::get_MachineName()
0x667a  call     instance string Microsoft.ReportingServices.Portal.Repositories.CatalogItemRepository::GetInstanceName(string machineName)
0x667f  stloc.1
0x6680  ldarg.2
0x6681  callvirt instance string [Microsoft.ReportingServices.Portal.Interfaces]Model.ExecutionLogInfo::get_ItemPath()
0x6686  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath::.ctor(string)
0x668b  stloc.2
0x668c  ldarg.1
0x668d  ldloc.2
0x668e  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath [ReportingServicesLibrary]Microsoft.ReportingServices.Library.RSService::ExternalToCatalogItemPath(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath)
0x6693  stloc.3
0x6694  ldarg.2
0x6695  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ReportExecutionInfo Microsoft.ReportingServices.Portal.Services.Extensions.ExecutionLogInfoExtensions::ToReportExecutionLog(class [Microsoft.ReportingServices.Portal.Interfaces]Model.ExecutionLogInfo executionLog)
0x669a  stloc.s  4
0x669c  ldarg.2
0x669d  callvirt instance int64 [Microsoft.ReportingServices.Portal.Interfaces]Model.ExecutionLogInfo::get_Status()
0x66a2  ldc.i4.m1
0x66a3  conv.i8
0x66a4  bne.un.s loc_66B2
0x66a6  ldloc.s  4
0x66a8  ldc.i4   0xD3
0x66ad  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ReportExecutionInfo::set_Status(valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode)
0x66b2  dup
0x66b3  ldloc.1
0x66b4  ldloc.3
0x66b5  ldc.i4.0
0x66b6  ldloc.s  4
0x66b8  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ReportExecutionInfo::get_Format()
0x66bd  ldloc.s  4
0x66bf  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ReportExecutionInfo::get_Parameters()
0x66c4  ldarg.2
0x66c5  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.ReportingServices.Portal.Interfaces]Model.ExecutionLogInfo::get_StartTime()
0x66ca  ldarg.2
0x66cb  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.ReportingServices.Portal.Interfaces]Model.ExecutionLogInfo::get_EndTime()
0x66d0  ldarg.2
0x66d1  callvirt instance int32 [Microsoft.ReportingServices.Portal.Interfaces]Model.ExecutionLogInfo::get_DataRetrievalTime()
0x66d6  ldarg.2
0x66d7  callvirt instance int32 [Microsoft.ReportingServices.Portal.Interfaces]Model.ExecutionLogInfo::get_ProcessingTime()
0x66dc  ldarg.2
0x66dd  callvirt instance int32 [Microsoft.ReportingServices.Portal.Interfaces]Model.ExecutionLogInfo::get_RenderingTime()
0x66e2  ldloc.s  4
0x66e4  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExecutionLogExecType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ReportExecutionInfo::get_Source()
0x66e9  ldloc.s  4
0x66eb  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ReportExecutionInfo::get_Status()
0x66f0  stloc.s  5
0x66f2  ldloca.s 5
0x66f4  constrained. [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Diagnostics.Utilities.ErrorCode
0x66fa  callvirt instance string [mscorlib]System.Object::ToString()
0x66ff  ldloc.s  4
0x6701  callvirt instance int64 [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ReportExecutionInfo::get_ByteCount()
0x6706  ldloc.s  4
0x6708  callvirt instance int64 [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ReportExecutionInfo::get_RowCount()
0x670d  ldloc.s  4
0x670f  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ReportExecutionInfo::get_ExecutionId()
0x6714  ldloc.s  4
0x6716  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ReportEventType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ReportExecutionInfo::get_EventType()
0x671b  conv.u1
0x671c  ldloc.s  4
0x671e  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ReportExecutionInfo::GetAdditionalInfoXml()
0x6723  callvirt instance void [ReportingServicesLibrary]Microsoft.ReportingServices.Library.DBInterface::AddExecutionLogEntry(string, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath, valuetype [ReportingServicesLibrary]Microsoft.ReportingServices.Library.DBInterface/RequestType, string, string, valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime, int32, int32, int32, valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExecutionLogExecType, string, int64, int64, string, unsigned int8, string)
0x6728  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::Commit()
0x672d  leave.s  loc_6736
0x672f  ldloc.0
0x6730  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::DisconnectStorage()
0x6735  endfinally
0x6736  ldc.i4.1
0x6737  ret
```
