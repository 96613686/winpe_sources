# Microsoft.ReportingServices.Library.SchedulingDBInterface::ListTasks

- ea: `0x485f0`
- end: `0x486e4`
- name: `Microsoft.ReportingServices.Library.SchedulingDBInterface::ListTasks`
- size: `244`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x47230`

## callees

- `0x47d60`
- `0x47e60`
- `0x485f0`

## string_xrefs

- `0x4860e`: `@Path`
- `0x485fe`: `ListTasks`

## pseudocode

```c

```

## disassembly

```asm
0x485f0  ldarg.0
0x485f1  call     instance bool Microsoft.ReportingServices.Library.SchedulingDBInterface::IsSchedulerRunning()
0x485f6  stloc.0
0x485f7  newobj   instance void [mscorlib]System.Collections.ArrayList::.ctor()
0x485fc  stloc.1
0x485fd  ldarg.0
0x485fe  ldstr    aListtasks// "ListTasks"
0x48603  ldnull
0x48604  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x48609  stloc.2
0x4860a  ldarg.1
0x4860b  brfalse.s loc_48644
0x4860d  ldloc.2
0x4860e  ldstr    aPath// "@Path"
0x48613  ldc.i4.s 0xC
0x48615  ldarg.1
0x48616  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x4861b  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x48620  pop
0x48621  ldloc.2
0x48622  ldstr    aPrefix// "@Prefix"
0x48627  ldc.i4.s 0xC
0x48629  ldarg.1
0x4862a  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x4862f  call     string [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::EncodeForLike(string)
0x48634  ldstr    asc_92514// "/%"
0x48639  call     string [mscorlib]System.String::Concat(string, string)
0x4863e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x48643  pop
0x48644  ldloc.2
0x48645  callvirt instance class [System.Data]System.Data.IDataReader [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteReader()
0x4864a  stloc.3
0x4864b  br.s     loc_4867A
0x4864d  ldloc.3
0x4864e  ldc.i4.0
0x4864f  ldc.i4.1
0x48650  newobj   instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::.ctor(class [System.Data]System.Data.IDataRecord, int32, bool)
0x48655  stloc.s  4
0x48657  ldloc.0
0x48658  brtrue.s loc_48662
0x4865a  ldloc.s  4
0x4865c  ldc.i4.1
0x4865d  callvirt instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::set_IsFailing(bool)
0x48662  ldloc.s  4
0x48664  ldloc.3
0x48665  ldc.i4.s 0x19
0x48667  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetInt32(int32)
0x4866c  callvirt instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::set_ReportsCount(int32)
0x48671  ldloc.1
0x48672  ldloc.s  4
0x48674  callvirt instance int32 [mscorlib]System.Collections.ArrayList::Add(object)
0x48679  pop
0x4867a  ldloc.3
0x4867b  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x48680  brtrue.s loc_4864D
0x48682  leave.s  loc_48698
0x48684  ldloc.3
0x48685  brfalse.s loc_4868D
0x48687  ldloc.3
0x48688  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4868d  endfinally
0x4868e  ldloc.2
0x4868f  brfalse.s loc_48697
0x48691  ldloc.2
0x48692  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x48697  endfinally
0x48698  ldloc.1
0x48699  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.ArrayList::GetEnumerator()
0x4869e  stloc.s  5
0x486a0  br.s     loc_486C2
0x486a2  ldloc.s  5
0x486a4  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x486a9  castclass [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task
0x486ae  stloc.s  6
0x486b0  ldloc.s  6
0x486b2  callvirt instance valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskState [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_DatabaseState()
0x486b7  ldc.i4.1
0x486b8  bne.un.s loc_486C2
0x486ba  ldarg.0
0x486bb  ldloc.s  6
0x486bd  call     instance void Microsoft.ReportingServices.Library.SchedulingDBInterface::CheckTasksNextRunTime(class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task t)
0x486c2  ldloc.s  5
0x486c4  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x486c9  brtrue.s loc_486A2
0x486cb  leave.s  loc_486E2
0x486cd  ldloc.s  5
0x486cf  isinst   [mscorlib]System.IDisposable
0x486d4  stloc.s  7
0x486d6  ldloc.s  7
0x486d8  brfalse.s loc_486E1
0x486da  ldloc.s  7
0x486dc  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x486e1  endfinally
0x486e2  ldloc.1
0x486e3  ret
```
