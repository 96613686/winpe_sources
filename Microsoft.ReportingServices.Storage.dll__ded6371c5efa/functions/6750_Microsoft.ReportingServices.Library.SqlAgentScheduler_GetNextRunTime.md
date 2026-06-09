# Microsoft.ReportingServices.Library.SqlAgentScheduler::GetNextRunTime

- ea: `0x6750`
- end: `0x68a3`
- name: `Microsoft.ReportingServices.Library.SqlAgentScheduler::GetNextRunTime`
- size: `339`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x3230`
- `0x52e0`
- `0x5300`
- `0x6750`
- `0x6a70`
- `0x6c00`
- `0x7120`
- `0x72a0`
- `0x7320`

## string_xrefs

- `0x6764`: `Get_sqlagent_job_status`

## pseudocode

```c

```

## disassembly

```asm
0x6750  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x6755  stloc.0
0x6756  ldc.i4.1
0x6757  stloc.1
0x6758  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x675d  stloc.2
0x675e  br       loc_6889
0x6763  ldarg.0
0x6764  ldstr    aGetSqlagentJob// "Get_sqlagent_job_status"
0x6769  ldnull
0x676a  callvirt instance class Microsoft.ReportingServices.Library.InstrumentedSqlCommand Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string storedProcedureName, [opt] class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection connection)
0x676f  stloc.s  4
0x6771  ldloc.s  4
0x6773  ldarg.0
0x6774  callvirt instance class Microsoft.ReportingServices.Library.ConnectionManager Microsoft.ReportingServices.Library.Storage::get_ConnectionManager()
0x6779  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction Microsoft.ReportingServices.Library.ConnectionManager::get_Transaction()
0x677e  callvirt instance void Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_Transaction(class [System.Data]System.Data.IDbTransaction value)
0x6783  ldloc.s  4
0x6785  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x678a  callvirt instance void [System.Data]System.Data.Common.DbParameterCollection::Clear()
0x678f  ldstr    aJobName// "@job_name"
0x6794  ldc.i4.s 0xC
0x6796  ldc.i4   0x80
0x679b  newobj   instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x67a0  stloc.s  5
0x67a2  ldloc.s  5
0x67a4  ldarga.s 1
0x67a6  constrained. [mscorlib]System.Guid
0x67ac  callvirt instance string [mscorlib]System.Object::ToString()
0x67b1  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x67b6  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0x67bb  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x67c0  ldloc.s  4
0x67c2  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x67c7  ldloc.s  5
0x67c9  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter)
0x67ce  pop
0x67cf  ldc.i4.0
0x67d0  stloc.3
0x67d1  ldloc.s  4
0x67d3  callvirt instance class [System.Data]System.Data.IDataReader Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteReader()
0x67d8  stloc.s  6
0x67da  ldloc.s  6
0x67dc  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x67e1  brfalse.s loc_6847
0x67e3  ldc.i4.1
0x67e4  stloc.3
0x67e5  ldloc.s  6
0x67e7  ldc.i4.3
0x67e8  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetInt32(int32)
0x67ed  stloc.s  7
0x67ef  ldloc.s  6
0x67f1  ldc.i4.4
0x67f2  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetInt32(int32)
0x67f7  stloc.s  8
0x67f9  ldloc.s  7
0x67fb  brfalse.s loc_6841
0x67fd  ldloc.s  7
0x67ff  call     valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.SqlScheduleHelper::GetSqlDays(int32 date)
0x6804  stloc.s  9
0x6806  ldloc.s  8
0x6808  call     valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.SqlScheduleHelper::GetSqlTime(int32 time)
0x680d  stloc.s  0xA
0x680f  ldloca.s 9
0x6811  call     instance int32 [mscorlib]System.DateTime::get_Year()
0x6816  ldloca.s 9
0x6818  call     instance int32 [mscorlib]System.DateTime::get_Month()
0x681d  ldloca.s 9
0x681f  call     instance int32 [mscorlib]System.DateTime::get_Day()
0x6824  ldloca.s 0xA
0x6826  call     instance int32 [mscorlib]System.DateTime::get_Hour()
0x682b  ldloca.s 0xA
0x682d  call     instance int32 [mscorlib]System.DateTime::get_Minute()
0x6832  ldloca.s 0xA
0x6834  call     instance int32 [mscorlib]System.DateTime::get_Second()
0x6839  newobj   instance void [mscorlib]System.DateTime::.ctor(int32, int32, int32, int32, int32, int32)
0x683e  stloc.2
0x683f  br.s     loc_6847
0x6841  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x6846  stloc.2
0x6847  leave.s  loc_6855
0x6849  ldloc.s  6
0x684b  brfalse.s loc_6854
0x684d  ldloc.s  6
0x684f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6854  endfinally
0x6855  leave.s  loc_6863
0x6857  ldloc.s  4
0x6859  brfalse.s loc_6862
0x685b  ldloc.s  4
0x685d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6862  endfinally
0x6863  ldloc.3
0x6864  brtrue.s loc_688F
0x6866  ldloc.0
0x6867  ldarg.0
0x6868  ldfld    valuetype [mscorlib]System.TimeSpan Microsoft.ReportingServices.Library.SqlAgentScheduler::_tolerance
0x686d  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x6872  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x6877  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x687c  brtrue.s loc_688F
0x687e  ldarg.0
0x687f  ldfld    valuetype [mscorlib]System.TimeSpan Microsoft.ReportingServices.Library.SqlAgentScheduler::_waitTime
0x6884  call     void [mscorlib]System.Threading.Thread::Sleep(valuetype [mscorlib]System.TimeSpan)
0x6889  ldloc.1
0x688a  brtrue   loc_6763
0x688f  leave.s  loc_68A1
0x6891  callvirt instance int32 [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ReportServerStorageException::get_SqlErrorNumber()
0x6896  ldc.i4   0x37B6
0x689b  beq.s    loc_689F
0x689d  rethrow
0x689f  leave.s  loc_68A1
0x68a1  ldloc.2
0x68a2  ret
```
