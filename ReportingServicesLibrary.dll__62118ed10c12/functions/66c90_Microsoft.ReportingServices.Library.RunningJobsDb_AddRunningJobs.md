# Microsoft.ReportingServices.Library.RunningJobsDb::AddRunningJobs

- ea: `0x66c90`
- end: `0x66edf`
- name: `Microsoft.ReportingServices.Library.RunningJobsDb::AddRunningJobs`
- size: `591`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x66a80`

## callees

- `0xf570`
- `0x66c90`

## string_xrefs

- `0x66d8b`: `@UserSid`
- `0x66d2c`: `@ComputerName`
- `0x66d68`: `@RequestPath`

## pseudocode

```c

```

## disassembly

```asm
0x66c90  ldc.i4.0
0x66c91  stloc.0
0x66c92  ldarg.0
0x66c93  callvirt instance int32 [mscorlib]System.Collections.Hashtable::get_Count()
0x66c98  brtrue.s loc_66C9C
0x66c9a  ldloc.0
0x66c9b  ret
0x66c9c  ldc.i4.1
0x66c9d  ldc.i4   0x1000
0x66ca2  newobj   instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::.ctor(valuetype [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionTransactionType, valuetype [System.Data]System.Data.IsolationLevel)
0x66ca7  stloc.1
0x66ca8  ldloc.1
0x66ca9  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::WillDisconnectStorage()
0x66cae  ldarg.0
0x66caf  callvirt instance class [mscorlib]System.Collections.ICollection [mscorlib]System.Collections.Hashtable::get_Values()
0x66cb4  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x66cb9  stloc.2
0x66cba  br       loc_66EA7
0x66cbf  ldloc.2
0x66cc0  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x66cc5  castclass [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.RunningJobContext
0x66cca  stloc.3
0x66ccb  ldstr    aAddrunningjob// "AddRunningJob"
0x66cd0  ldloc.1
0x66cd1  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::get_Connection()
0x66cd6  newobj   instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::.ctor(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x66cdb  stloc.s  4
0x66cdd  ldloc.s  4
0x66cdf  ldc.i4.4
0x66ce0  callvirt instance void [System.Data]System.Data.Common.DbCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x66ce5  ldloc.s  4
0x66ce7  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::get_Parameters()
0x66cec  ldstr    aJobid_0// "@JobID"
0x66cf1  ldloc.3
0x66cf2  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.RunningJobContext::get_JobId()
0x66cf7  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x66cfc  ldc.i4.s 0xC
0x66cfe  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x66d03  ldloc.s  4
0x66d05  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::get_Parameters()
0x66d0a  ldstr    aStartdate// "@StartDate"
0x66d0f  ldloc.3
0x66d10  callvirt instance valuetype [mscorlib]System.DateTime [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.RunningJobContext::get_StartDate()
0x66d15  box      [mscorlib]System.DateTime
0x66d1a  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x66d1f  ldc.i4.4
0x66d20  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x66d25  ldloc.s  4
0x66d27  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::get_Parameters()
0x66d2c  ldstr    aComputername// "@ComputerName"
0x66d31  ldloc.3
0x66d32  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.RunningJobContext::get_Machine()
0x66d37  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x66d3c  ldc.i4.s 0xC
0x66d3e  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x66d43  ldloc.s  4
0x66d45  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::get_Parameters()
0x66d4a  ldstr    aRequestname// "@RequestName"
0x66d4f  ldloc.3
0x66d50  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.RunningJobContext::get_Name()
0x66d55  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x66d5a  ldc.i4.s 0xC
0x66d5c  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x66d61  ldloc.s  4
0x66d63  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::get_Parameters()
0x66d68  ldstr    aRequestpath// "@RequestPath"
0x66d6d  ldloc.3
0x66d6e  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.RunningJobContext::get_Path()
0x66d73  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x66d78  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x66d7d  ldc.i4.s 0xC
0x66d7f  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x66d84  ldloc.s  4
0x66d86  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::get_Parameters()
0x66d8b  ldstr    aUsersid// "@UserSid"
0x66d90  ldloc.3
0x66d91  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.RunningJobContext::get_UserContext()
0x66d96  call     unsigned int8[] Microsoft.ReportingServices.Library.Global::NameToSid(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext user)
0x66d9b  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x66da0  ldc.i4.s 0x15
0x66da2  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x66da7  ldloc.s  4
0x66da9  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::get_Parameters()
0x66dae  ldstr    aUsername_0// "@UserName"
0x66db3  ldloc.3
0x66db4  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.RunningJobContext::get_UserContext()
0x66db9  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_UserName()
0x66dbe  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x66dc3  ldc.i4.s 0xC
0x66dc5  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x66dca  ldloc.s  4
0x66dcc  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::get_Parameters()
0x66dd1  ldstr    aAuthtype// "@AuthType"
0x66dd6  ldloc.3
0x66dd7  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.RunningJobContext::get_UserContext()
0x66ddc  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AuthenticationType()
0x66de1  box      [mscorlib]System.Int32
0x66de6  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x66deb  ldc.i4.8
0x66dec  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x66df1  ldloc.3
0x66df2  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.RunningJobContext::get_Description()
0x66df7  brfalse.s loc_66E17
0x66df9  ldloc.s  4
0x66dfb  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::get_Parameters()
0x66e00  ldstr    aDescription// "@Description"
0x66e05  ldloc.3
0x66e06  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.RunningJobContext::get_Description()
0x66e0b  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x66e10  ldc.i4.s 0xB
0x66e12  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x66e17  ldloc.s  4
0x66e19  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::get_Parameters()
0x66e1e  ldstr    aTimeout// "@Timeout"
0x66e23  ldloc.3
0x66e24  callvirt instance int32 [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.RunningJobContext::get_Timeout()
0x66e29  box      [mscorlib]System.Int32
0x66e2e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x66e33  ldc.i4.8
0x66e34  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x66e39  ldloc.s  4
0x66e3b  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::get_Parameters()
0x66e40  ldstr    aJobaction// "@JobAction"
0x66e45  ldloc.3
0x66e46  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.JobActionEnum [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.RunningJobContext::get_Action()
0x66e4b  box      [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.JobActionEnum
0x66e50  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x66e55  ldc.i4.s 0x10
0x66e57  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x66e5c  ldloc.s  4
0x66e5e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::get_Parameters()
0x66e63  ldstr    aJobtype// "@JobType"
0x66e68  ldloc.3
0x66e69  callvirt instance valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.JobTypeEnum [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.RunningJobContext::get_Type()
0x66e6e  box      [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.JobTypeEnum
0x66e73  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x66e78  ldc.i4.s 0x10
0x66e7a  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x66e7f  ldloc.s  4
0x66e81  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::get_Parameters()
0x66e86  ldstr    aJobstatus// "@JobStatus"
0x66e8b  ldc.i4.1
0x66e8c  box      [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.JobStatusEnum
0x66e91  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x66e96  ldc.i4.s 0x10
0x66e98  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x66e9d  ldloc.0
0x66e9e  ldloc.s  4
0x66ea0  callvirt instance int32 [System.Data]System.Data.Common.DbCommand::ExecuteNonQuery()
0x66ea5  add
0x66ea6  stloc.0
0x66ea7  ldloc.2
0x66ea8  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x66ead  brtrue   loc_66CBF
0x66eb2  leave.s  loc_66EC8
0x66eb4  ldloc.2
0x66eb5  isinst   [mscorlib]System.IDisposable
0x66eba  stloc.s  5
0x66ebc  ldloc.s  5
0x66ebe  brfalse.s loc_66EC7
0x66ec0  ldloc.s  5
0x66ec2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x66ec7  endfinally
0x66ec8  leave.s  loc_66EDD
0x66eca  ldloc.1
0x66ecb  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::AbortTransaction()
0x66ed0  newobj   instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ReportServerDatabaseUnavailableException::.ctor(class [mscorlib]System.Exception)
0x66ed5  throw
0x66ed6  ldloc.1
0x66ed7  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::DisconnectStorage()
0x66edc  endfinally
0x66edd  ldloc.0
0x66ede  ret
```
