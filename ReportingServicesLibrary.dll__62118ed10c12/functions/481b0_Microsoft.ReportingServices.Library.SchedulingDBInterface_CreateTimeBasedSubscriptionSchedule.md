# Microsoft.ReportingServices.Library.SchedulingDBInterface::CreateTimeBasedSubscriptionSchedule

- ea: `0x481b0`
- end: `0x482ea`
- name: `Microsoft.ReportingServices.Library.SchedulingDBInterface::CreateTimeBasedSubscriptionSchedule`
- size: `314`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x46d40`
- `0x533b0`

## callees

- `0xf570`
- `0x461a0`
- `0x47e70`
- `0x481b0`
- `0x48790`

## string_xrefs

- `0x481dd`: `@UserSid`
- `0x4827c`: `@Path`
- `0x481b7`: `CreateTimeBasedSubscriptionSchedule`
- `0x481c4`: `@ItemPath`

## pseudocode

```c

```

## disassembly

```asm
0x481b0  ldarg.0
0x481b1  call     instance void Microsoft.ReportingServices.Library.SchedulingDBInterface::ThrowIfSchedulerNotRunning()
0x481b6  ldarg.0
0x481b7  ldstr    aCreatetimebase// "CreateTimeBasedSubscriptionSchedule"
0x481bc  ldnull
0x481bd  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x481c2  stloc.0
0x481c3  ldloc.0
0x481c4  ldstr    aItempath_2// "@ItemPath"
0x481c9  ldc.i4.s 0xC
0x481cb  ldarg.1
0x481cc  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x481d1  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x481d6  pop
0x481d7  ldloc.0
0x481d8  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x481dd  ldstr    aUsersid// "@UserSid"
0x481e2  ldarg.s  4
0x481e4  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Creator()
0x481e9  call     unsigned int8[] Microsoft.ReportingServices.Library.Global::NameToSid(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext user)
0x481ee  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x481f3  pop
0x481f4  ldloc.0
0x481f5  ldstr    aUsername_0// "@UserName"
0x481fa  ldc.i4.s 0xC
0x481fc  ldarg.s  4
0x481fe  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Creator()
0x48203  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_UserName()
0x48208  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x4820d  pop
0x4820e  ldloc.0
0x4820f  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x48214  ldstr    aAuthtype// "@AuthType"
0x48219  ldarg.s  4
0x4821b  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Creator()
0x48220  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AuthenticationType()
0x48225  box      [mscorlib]System.Int32
0x4822a  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x4822f  pop
0x48230  ldloc.0
0x48231  ldstr    aScheduleName// "@Schedule_Name"
0x48236  ldc.i4.s 0xC
0x48238  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x4823d  stloc.1
0x4823e  ldloca.s 1
0x48240  constrained. [mscorlib]System.Guid
0x48246  callvirt instance string [mscorlib]System.Object::ToString()
0x4824b  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x48250  pop
0x48251  ldloc.0
0x48252  ldstr    aEventdata// "@EventData"
0x48257  ldc.i4.s 0xC
0x48259  ldarg.s  4
0x4825b  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_EventData()
0x48260  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x48265  pop
0x48266  ldloc.0
0x48267  ldstr    aEventtype_0// "@EventType"
0x4826c  ldc.i4.s 0xC
0x4826e  ldarg.s  4
0x48270  callvirt instance string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_EventType()
0x48275  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x4827a  pop
0x4827b  ldloc.0
0x4827c  ldstr    aPath// "@Path"
0x48281  ldc.i4.s 0xC
0x48283  ldarg.s  4
0x48285  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Path()
0x4828a  call     string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::SafeValue(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase)
0x4828f  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x48294  pop
0x48295  ldloc.0
0x48296  ldstr    aAction// "@Action"
0x4829b  ldc.i4.8
0x4829c  ldarg.3
0x4829d  box      Microsoft.ReportingServices.Library.ReportScheduleActions
0x482a2  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x482a7  pop
0x482a8  ldloc.0
0x482a9  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x482ae  ldstr    aSubscriptionid// "@SubscriptionID"
0x482b3  ldarg.2
0x482b4  box      [mscorlib]System.Guid
0x482b9  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x482be  pop
0x482bf  ldarg.0
0x482c0  ldloc.0
0x482c1  ldarg.s  4
0x482c3  ldc.i4.1
0x482c4  call     instance void Microsoft.ReportingServices.Library.SchedulingDBInterface::SetSqlParameters(class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand command, class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task task, bool resetNextRuntime)
0x482c9  ldloc.0
0x482ca  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x482cf  pop
0x482d0  leave.s  loc_482DC
0x482d2  ldloc.0
0x482d3  brfalse.s loc_482DB
0x482d5  ldloc.0
0x482d6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x482db  endfinally
0x482dc  ldarg.0
0x482dd  ldfld    class Microsoft.ReportingServices.Library.SqlAgentScheduler Microsoft.ReportingServices.Library.SchedulingDBInterface::m_sqlSchedule
0x482e2  ldarg.s  4
0x482e4  callvirt instance void Microsoft.ReportingServices.Library.SqlAgentScheduler::CreateTask(class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task task)
0x482e9  ret
```
