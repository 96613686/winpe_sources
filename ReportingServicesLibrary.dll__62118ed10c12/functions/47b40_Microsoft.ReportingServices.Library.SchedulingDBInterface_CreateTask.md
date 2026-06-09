# Microsoft.ReportingServices.Library.SchedulingDBInterface::CreateTask

- ea: `0x47b40`
- end: `0x47ccb`
- name: `Microsoft.ReportingServices.Library.SchedulingDBInterface::CreateTask`
- size: `395`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x46be0`
- `0x46f50`

## callees

- `0xf570`
- `0x461a0`
- `0x47b40`
- `0x47e70`
- `0x48790`

## string_xrefs

- `0x47be2`: `@UserSid`
- `0x47c61`: `@Path`
- `0x47b47`: `CreateTask`
- `0x47c9a`: `Schedule already exists`

## pseudocode

```c

```

## disassembly

```asm
0x47b40  ldarg.0
0x47b41  call     instance void Microsoft.ReportingServices.Library.SchedulingDBInterface::ThrowIfSchedulerNotRunning()
0x47b46  ldarg.0
0x47b47  ldstr    aCreatetask// "CreateTask"
0x47b4c  ldnull
0x47b4d  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x47b52  stloc.0
0x47b53  ldarg.1
0x47b54  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Name()
0x47b59  brfalse.s loc_47B68
0x47b5b  ldarg.1
0x47b5c  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Name()
0x47b61  callvirt instance int32 [mscorlib]System.String::get_Length()
0x47b66  brtrue.s loc_47B99
0x47b68  ldsfld   class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Library.Global::m_Tracer
0x47b6d  ldarg.1
0x47b6e  callvirt instance valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.ScheduleType [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Type()
0x47b73  ldc.i4.1
0x47b74  ceq
0x47b76  ldstr    aOnlyScopedSche// "Only scoped schedules can not have name"...
0x47b7b  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x47b80  ldarg.1
0x47b81  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x47b86  stloc.1
0x47b87  ldloca.s 1
0x47b89  constrained. [mscorlib]System.Guid
0x47b8f  callvirt instance string [mscorlib]System.Object::ToString()
0x47b94  callvirt instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::set_Name(string)
0x47b99  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x47b9e  ldarg.1
0x47b9f  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Creator()
0x47ba4  ldnull
0x47ba5  cgt.un
0x47ba7  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool)
0x47bac  ldloc.0
0x47bad  ldstr    aName_0// "@Name"
0x47bb2  ldc.i4.s 0xC
0x47bb4  ldarg.1
0x47bb5  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Name()
0x47bba  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x47bbf  pop
0x47bc0  ldloc.0
0x47bc1  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x47bc6  ldstr    aType// "@Type"
0x47bcb  ldarg.1
0x47bcc  callvirt instance valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.ScheduleType [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Type()
0x47bd1  box      [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.ScheduleType
0x47bd6  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x47bdb  pop
0x47bdc  ldloc.0
0x47bdd  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x47be2  ldstr    aUsersid// "@UserSid"
0x47be7  ldarg.1
0x47be8  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Creator()
0x47bed  call     unsigned int8[] Microsoft.ReportingServices.Library.Global::NameToSid(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext user)
0x47bf2  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x47bf7  ldc.i4.s 0x15
0x47bf9  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x47bfe  ldloc.0
0x47bff  ldstr    aUsername_0// "@UserName"
0x47c04  ldc.i4.s 0xC
0x47c06  ldarg.1
0x47c07  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Creator()
0x47c0c  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_UserName()
0x47c11  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x47c16  pop
0x47c17  ldloc.0
0x47c18  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x47c1d  ldstr    aAuthtype// "@AuthType"
0x47c22  ldarg.1
0x47c23  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Creator()
0x47c28  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AuthenticationType()
0x47c2d  box      [mscorlib]System.Int32
0x47c32  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x47c37  pop
0x47c38  ldloc.0
0x47c39  ldstr    aEventdata// "@EventData"
0x47c3e  ldc.i4.s 0xC
0x47c40  ldarg.1
0x47c41  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_EventData()
0x47c46  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x47c4b  pop
0x47c4c  ldloc.0
0x47c4d  ldstr    aEventtype_0// "@EventType"
0x47c52  ldc.i4.s 0xC
0x47c54  ldarg.1
0x47c55  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_EventType()
0x47c5a  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x47c5f  pop
0x47c60  ldloc.0
0x47c61  ldstr    aPath// "@Path"
0x47c66  ldc.i4.s 0xC
0x47c68  ldarg.1
0x47c69  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Path()
0x47c6e  call     string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::SafeValue(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase)
0x47c73  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x47c78  pop
0x47c79  ldarg.0
0x47c7a  ldloc.0
0x47c7b  ldarg.1
0x47c7c  ldc.i4.1
0x47c7d  call     instance void Microsoft.ReportingServices.Library.SchedulingDBInterface::SetSqlParameters(class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand command, class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task task, bool resetNextRuntime)
0x47c82  ldloc.0
0x47c83  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x47c88  pop
0x47c89  leave.s  loc_47CBE
0x47c8b  stloc.2
0x47c8c  ldloc.2
0x47c8d  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ReportServerStorageException::get_IsSqlException()
0x47c92  brfalse.s loc_47CB2
0x47c94  ldloc.2
0x47c95  callvirt instance string [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ReportServerStorageException::get_SqlErrorMessage()
0x47c9a  ldstr    aScheduleAlread// "Schedule already exists"
0x47c9f  call     bool [mscorlib]System.String::op_Equality(string, string)
0x47ca4  brfalse.s loc_47CB2
0x47ca6  ldarg.1
0x47ca7  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Name()
0x47cac  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ScheduleAlreadyExists::.ctor(string)
0x47cb1  throw
0x47cb2  rethrow
0x47cb4  ldloc.0
0x47cb5  brfalse.s loc_47CBD
0x47cb7  ldloc.0
0x47cb8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x47cbd  endfinally
0x47cbe  ldarg.0
0x47cbf  ldfld    class Microsoft.ReportingServices.Library.SqlAgentScheduler Microsoft.ReportingServices.Library.SchedulingDBInterface::m_sqlSchedule
0x47cc4  ldarg.1
0x47cc5  callvirt instance void Microsoft.ReportingServices.Library.SqlAgentScheduler::CreateTask(class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task task)
0x47cca  ret
```
