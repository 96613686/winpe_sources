# Microsoft.ReportingServices.Library.SchedulingDBInterface::UpdateTaskProperties

- ea: `0x48430`
- end: `0x484b5`
- name: `Microsoft.ReportingServices.Library.SchedulingDBInterface::UpdateTaskProperties`
- size: `133`
- prototype: ``
- caller_count: `8`
- callee_count: `4`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x47130`
- `0x47780`
- `0x47870`
- `0x47900`
- `0x47dd0`
- `0x484c0`
- `0x48500`
- `0x533b0`

## callees

- `0x46710`
- `0x47e70`
- `0x48430`
- `0x48790`

## string_xrefs

- `0x48478`: `Schedule already exists`
- `0x48437`: `UpdateTask`

## pseudocode

```c

```

## disassembly

```asm
0x48430  ldarg.0
0x48431  call     instance void Microsoft.ReportingServices.Library.SchedulingDBInterface::ThrowIfSchedulerNotRunning()
0x48436  ldarg.0
0x48437  ldstr    aUpdatetask// "UpdateTask"
0x4843c  ldnull
0x4843d  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x48442  stloc.0
0x48443  ldloc.0
0x48444  ldstr    aName_0// "@Name"
0x48449  ldc.i4.s 0xC
0x4844b  ldarg.1
0x4844c  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Name()
0x48451  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x48456  pop
0x48457  ldarg.0
0x48458  ldloc.0
0x48459  ldarg.1
0x4845a  ldarg.2
0x4845b  call     instance void Microsoft.ReportingServices.Library.SchedulingDBInterface::SetSqlParameters(class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand command, class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task task, bool resetNextRuntime)
0x48460  ldloc.0
0x48461  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x48466  pop
0x48467  leave.s  loc_4849C
0x48469  stloc.1
0x4846a  ldloc.1
0x4846b  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ReportServerStorageException::get_IsSqlException()
0x48470  brfalse.s loc_48490
0x48472  ldloc.1
0x48473  callvirt instance string [mscorlib]System.Exception::get_Message()
0x48478  ldstr    aScheduleAlread// "Schedule already exists"
0x4847d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x48482  brfalse.s loc_48490
0x48484  ldarg.1
0x48485  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Name()
0x4848a  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ScheduleAlreadyExists::.ctor(string)
0x4848f  throw
0x48490  rethrow
0x48492  ldloc.0
0x48493  brfalse.s loc_4849B
0x48495  ldloc.0
0x48496  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4849b  endfinally
0x4849c  ldarg.2
0x4849d  brfalse.s loc_484B4
0x4849f  ldarg.1
0x484a0  callvirt instance valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.TaskState [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_ScheduleState()
0x484a5  ldc.i4.2
0x484a6  beq.s    loc_484B4
0x484a8  ldarg.0
0x484a9  ldfld    class Microsoft.ReportingServices.Library.SqlAgentScheduler Microsoft.ReportingServices.Library.SchedulingDBInterface::m_sqlSchedule
0x484ae  ldarg.1
0x484af  callvirt instance void Microsoft.ReportingServices.Library.SqlAgentScheduler::UpdateTask(class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task task)
0x484b4  ret
```
