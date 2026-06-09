# Microsoft.ReportingServices.Library.SchedulePollWorker::CheckScheduleConsistancy

- ea: `0x468c0`
- end: `0x46b40`
- name: `Microsoft.ReportingServices.Library.SchedulePollWorker::CheckScheduleConsistancy`
- size: `640`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x46170`
- `0x46670`
- `0x46710`
- `0x46730`
- `0x468c0`
- `0x47af0`
- `0x486f0`

## string_xrefs

- `0x4699b`: `Invalid SQL Agent Job {0} will be deleted and recreated`
- `0x46a55`: `Schedule ({0}) altered, being updated.`
- `0x46b16`: `Unhandled exception caught in Scheduling maintenance thread: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x468c0  call     void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.DBPoll::PollItemStart()
0x468c5  ldarg.0
0x468c6  ldc.i4.1
0x468c7  stfld    bool Microsoft.ReportingServices.Library.SchedulePollWorker::m_working
0x468cc  ldarg.0
0x468cd  ldstr    aClearschedulec// "ClearScheduleConsistancyFlags"
0x468d2  call     instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.PollWorker::ExecuteStoredProcedure(string)
0x468d7  br       loc_46AF4
0x468dc  newobj   instance void Microsoft.ReportingServices.Library.SchedulingDBInterface::.ctor()
0x468e1  stloc.0
0x468e2  ldloc.0
0x468e3  ldc.i4.1
0x468e4  ldc.i4   0x1000
0x468e9  newobj   instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::.ctor(valuetype [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionTransactionType, valuetype [System.Data]System.Data.IsolationLevel)
0x468ee  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::set_ConnectionManager(class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager)
0x468f3  ldloc.0
0x468f4  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::get_ConnectionManager()
0x468f9  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::WillDisconnectStorage()
0x468fe  ldnull
0x468ff  stloc.1
0x46900  ldloc.0
0x46901  callvirt instance class [mscorlib]System.Collections.ArrayList Microsoft.ReportingServices.Library.SchedulingDBInterface::ListTasksForMaintenance()
0x46906  stloc.1
0x46907  ldloc.0
0x46908  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::Commit()
0x4690d  leave.s  loc_46918
0x4690f  pop
0x46910  ldloc.0
0x46911  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::AbortTransaction()
0x46916  rethrow
0x46918  leave.s  loc_46921
0x4691a  ldloc.0
0x4691b  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::DisconnectStorage()
0x46920  endfinally
0x46921  ldloc.1
0x46922  callvirt instance int32 [mscorlib]System.Collections.ArrayList::get_Count()
0x46927  brfalse  loc_46AFF
0x4692c  newobj   instance void Microsoft.ReportingServices.Library.SqlAgentScheduler::.ctor()
0x46931  stloc.2
0x46932  ldloc.2
0x46933  ldloc.0
0x46934  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::get_ConnectionManager()
0x46939  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::set_ConnectionManager(class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager)
0x4693e  ldloc.1
0x4693f  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x46944  stloc.3
0x46945  br       loc_46AD3
0x4694a  ldloc.3
0x4694b  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x46950  castclass [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task
0x46955  stloc.s  4
0x46957  ldarg.0
0x46958  call     instance bool [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.PollWorker::get_ContinueWorking()
0x4695d  brfalse  loc_46ADE
0x46962  nop
0x46963  ldloc.s  4
0x46965  callvirt instance valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskState [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_ScheduleState()
0x4696a  ldc.i4.2
0x4696b  bne.un.s loc_46972
0x4696d  leave    loc_46AD3
0x46972  ldnull
0x46973  stloc.s  5
0x46975  ldloc.2
0x46976  ldloc.s  4
0x46978  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_ID()
0x4697d  callvirt instance class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task Microsoft.ReportingServices.Library.SqlAgentScheduler::GetTask(valuetype [mscorlib]System.Guid id)
0x46982  stloc.s  5
0x46984  leave.s  loc_469C9
0x46986  pop
0x46987  ldarg.0
0x46988  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.SchedulePollWorker::m_tracer
0x4698d  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x46992  brfalse.s loc_469BA
0x46994  ldarg.0
0x46995  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.SchedulePollWorker::m_tracer
0x4699a  ldc.i4.1
0x4699b  ldstr    aInvalidSqlAgen// "Invalid SQL Agent Job {0} will be delet"...
0x469a0  ldc.i4.1
0x469a1  newarr   [mscorlib]System.Object
0x469a6  dup
0x469a7  ldc.i4.0
0x469a8  ldloc.s  4
0x469aa  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_ID()
0x469af  box      [mscorlib]System.Guid
0x469b4  stelem.ref
0x469b5  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x469ba  ldloc.2
0x469bb  ldloc.s  4
0x469bd  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_ID()
0x469c2  callvirt instance void Microsoft.ReportingServices.Library.SqlAgentScheduler::DeleteTask(valuetype [mscorlib]System.Guid id)
0x469c7  leave.s  loc_469C9
0x469c9  ldloc.s  5
0x469cb  brtrue.s loc_46A37
0x469cd  ldarg.0
0x469ce  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.SchedulePollWorker::m_tracer
0x469d3  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceWarning()
0x469d8  brfalse.s loc_469FF
0x469da  ldarg.0
0x469db  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.SchedulePollWorker::m_tracer
0x469e0  ldstr    aSchedule0NotPr// "Schedule ({0}) not present, being added"...
0x469e5  ldc.i4.1
0x469e6  newarr   [mscorlib]System.Object
0x469eb  dup
0x469ec  ldc.i4.0
0x469ed  ldloc.s  4
0x469ef  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_ID()
0x469f4  box      [mscorlib]System.Guid
0x469f9  stelem.ref
0x469fa  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(string, object[])
0x469ff  ldloc.2
0x46a00  ldloc.s  4
0x46a02  callvirt instance void Microsoft.ReportingServices.Library.SqlAgentScheduler::UpdateTask(class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task task)
0x46a07  ldloc.2
0x46a08  ldloc.s  4
0x46a0a  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_ID()
0x46a0f  callvirt instance class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task Microsoft.ReportingServices.Library.SqlAgentScheduler::GetTask(valuetype [mscorlib]System.Guid id)
0x46a14  stloc.s  5
0x46a16  ldloc.s  5
0x46a18  ldloc.s  4
0x46a1a  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Path()
0x46a1f  callvirt instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::set_Path(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath)
0x46a24  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::get_Current()
0x46a29  ldc.i4.s 0x73
0x46a2b  call     T0x2B000001
0x46a30  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::WriteWarning(valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Event, object[])
0x46a35  br.s     loc_46AAA
0x46a37  ldloc.s  5
0x46a39  ldloc.s  4
0x46a3b  callvirt instance bool [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::EqualSqlSchedule(class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task)
0x46a40  brtrue.s loc_46AAA
0x46a42  ldarg.0
0x46a43  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.SchedulePollWorker::m_tracer
0x46a48  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceWarning()
0x46a4d  brfalse.s loc_46A74
0x46a4f  ldarg.0
0x46a50  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.SchedulePollWorker::m_tracer
0x46a55  ldstr    aSchedule0Alter// "Schedule ({0}) altered, being updated."
0x46a5a  ldc.i4.1
0x46a5b  newarr   [mscorlib]System.Object
0x46a60  dup
0x46a61  ldc.i4.0
0x46a62  ldloc.s  4
0x46a64  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_ID()
0x46a69  box      [mscorlib]System.Guid
0x46a6e  stelem.ref
0x46a6f  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(string, object[])
0x46a74  ldloc.2
0x46a75  ldloc.s  4
0x46a77  callvirt instance void Microsoft.ReportingServices.Library.SqlAgentScheduler::UpdateTask(class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task task)
0x46a7c  ldloc.2
0x46a7d  ldloc.s  4
0x46a7f  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_ID()
0x46a84  callvirt instance class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task Microsoft.ReportingServices.Library.SqlAgentScheduler::GetTask(valuetype [mscorlib]System.Guid id)
0x46a89  stloc.s  5
0x46a8b  ldloc.s  5
0x46a8d  ldloc.s  4
0x46a8f  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Path()
0x46a94  callvirt instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::set_Path(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath)
0x46a99  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::get_Current()
0x46a9e  ldc.i4.s 0x73
0x46aa0  call     T0x2B000001
0x46aa5  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::WriteWarning(valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Event, object[])
0x46aaa  ldloc.2
0x46aab  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::get_ConnectionManager()
0x46ab0  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::CommitTransaction()
0x46ab5  leave.s  loc_46AC5
0x46ab7  pop
0x46ab8  ldloc.2
0x46ab9  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::get_ConnectionManager()
0x46abe  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::AbortTransaction()
0x46ac3  rethrow
0x46ac5  leave.s  loc_46AD3
0x46ac7  ldloc.2
0x46ac8  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::get_ConnectionManager()
0x46acd  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::DisconnectStorage()
0x46ad2  endfinally
0x46ad3  ldloc.3
0x46ad4  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x46ad9  brtrue   loc_4694A
0x46ade  leave.s  loc_46AF4
0x46ae0  ldloc.3
0x46ae1  isinst   [mscorlib]System.IDisposable
0x46ae6  stloc.s  6
0x46ae8  ldloc.s  6
0x46aea  brfalse.s loc_46AF3
0x46aec  ldloc.s  6
0x46aee  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x46af3  endfinally
0x46af4  ldarg.0
0x46af5  call     instance bool [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.PollWorker::get_ContinueWorking()
0x46afa  brtrue   loc_468DC
0x46aff  leave.s  loc_46B3F
0x46b01  stloc.s  7
0x46b03  ldarg.0
0x46b04  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.SchedulePollWorker::m_tracer
0x46b09  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x46b0e  brfalse.s loc_46B30
0x46b10  ldarg.0
0x46b11  ldfld    class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.SchedulePollWorker::m_tracer
0x46b16  ldstr    aUnhandledExcep// "Unhandled exception caught in Schedulin"...
0x46b1b  ldc.i4.1
0x46b1c  newarr   [mscorlib]System.Object
0x46b21  dup
0x46b22  ldc.i4.0
0x46b23  ldloc.s  7
0x46b25  callvirt instance string [mscorlib]System.Object::ToString()
0x46b2a  stelem.ref
0x46b2b  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(string, object[])
0x46b30  leave.s  loc_46B3F
0x46b32  ldarg.0
0x46b33  ldc.i4.0
0x46b34  stfld    bool Microsoft.ReportingServices.Library.SchedulePollWorker::m_working
0x46b39  call     void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.DBPoll::PollItemEnd()
0x46b3e  endfinally
0x46b3f  ret
```
