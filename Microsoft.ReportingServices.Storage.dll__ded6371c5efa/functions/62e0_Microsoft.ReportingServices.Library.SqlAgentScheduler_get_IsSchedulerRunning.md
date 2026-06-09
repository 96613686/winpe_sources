# Microsoft.ReportingServices.Library.SqlAgentScheduler::get_IsSchedulerRunning

- ea: `0x62e0`
- end: `0x63aa`
- name: `Microsoft.ReportingServices.Library.SqlAgentScheduler::get_IsSchedulerRunning`
- size: `202`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callees

- `0x62e0`
- `0x6c00`
- `0x70e0`
- `0x7320`

## string_xrefs

- `0x62e3`: `master.dbo.xp_sqlagent_notify`

## pseudocode

```c

```

## disassembly

```asm
0x62e0  ldc.i4.1
0x62e1  stloc.0
0x62e2  ldarg.0
0x62e3  ldstr    aMasterDboXpSql// "master.dbo.xp_sqlagent_notify"
0x62e8  ldnull
0x62e9  callvirt instance class Microsoft.ReportingServices.Library.InstrumentedSqlCommand Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string storedProcedureName, [opt] class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection connection)
0x62ee  stloc.2
0x62ef  ldloc.2
0x62f0  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x62f5  ldstr    aOpType// "@op_type"
0x62fa  ldstr    aG// "G"
0x62ff  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x6304  pop
0x6305  ldloc.2
0x6306  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x630b  ldstr    aJobId// "@job_id"
0x6310  ldnull
0x6311  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x6316  pop
0x6317  ldloc.2
0x6318  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x631d  ldstr    aScheduleId// "@schedule_id"
0x6322  ldnull
0x6323  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x6328  pop
0x6329  ldloc.2
0x632a  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x632f  ldstr    aAlertId// "@alert_id"
0x6334  ldnull
0x6335  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x633a  pop
0x633b  ldloc.2
0x633c  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x6341  ldstr    aActionType// "@action_type"
0x6346  ldnull
0x6347  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x634c  pop
0x634d  ldloc.2
0x634e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x6353  ldstr    aRetval// "@retval"
0x6358  ldc.i4.0
0x6359  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x635e  dup
0x635f  ldc.i4.6
0x6360  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x6365  ldloc.2
0x6366  callvirt instance int32 Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x636b  pop
0x636c  callvirt instance object [System.Data]System.Data.Common.DbParameter::get_Value()
0x6371  unbox.any [mscorlib]System.Int32
0x6376  stloc.1
0x6377  leave.s  loc_6383
0x6379  ldloc.2
0x637a  brfalse.s loc_6382
0x637c  ldloc.2
0x637d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6382  endfinally
0x6383  ldloc.1
0x6384  ldc.i4.1
0x6385  bne.un.s loc_639C
0x6387  ldc.i4.0
0x6388  stloc.0
0x6389  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::get_Current()
0x638e  ldc.i4.s 0x6A
0x6390  call     T0x2B000001
0x6395  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::WriteError(valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Event, object[])
0x639a  br.s     loc_63A8
0x639c  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::get_Current()
0x63a1  ldc.i4.s 0x6A
0x63a3  callvirt instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Utilities.RSEventLog::ResetWriteOnceEvent(valuetype [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Event)
0x63a8  ldloc.0
0x63a9  ret
```
