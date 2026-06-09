# Microsoft.ReportingServices.Library.SqlAgentScheduler::GetTask

- ea: `0x6970`
- end: `0x6a1c`
- name: `Microsoft.ReportingServices.Library.SqlAgentScheduler::GetTask`
- size: `172`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x4e10`
- `0x4e20`
- `0x4e30`
- `0x6970`
- `0x6c00`
- `0x7120`
- `0x7310`
- `0x7320`

## pseudocode

```c

```

## disassembly

```asm
0x6970  ldnull
0x6971  stloc.0
0x6972  ldarg.0
0x6973  ldstr    aMsdbDboSpHelpJ// "msdb.dbo.sp_help_jobschedule"
0x6978  ldnull
0x6979  callvirt instance class Microsoft.ReportingServices.Library.InstrumentedSqlCommand Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string storedProcedureName, [opt] class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection connection)
0x697e  stloc.1
0x697f  ldloc.1
0x6980  ldc.i4.4
0x6981  callvirt instance void Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType value)
0x6986  ldstr    aJobName// "@job_name"
0x698b  ldc.i4.s 0xC
0x698d  ldc.i4   0x80
0x6992  newobj   instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x6997  stloc.2
0x6998  ldloc.2
0x6999  ldarga.s 1
0x699b  constrained. [mscorlib]System.Guid
0x69a1  callvirt instance string [mscorlib]System.Object::ToString()
0x69a6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x69ab  callvirt instance string [mscorlib]System.String::ToUpper(class [mscorlib]System.Globalization.CultureInfo)
0x69b0  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x69b5  ldloc.1
0x69b6  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x69bb  ldloc.2
0x69bc  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter)
0x69c1  pop
0x69c2  ldloc.1
0x69c3  callvirt instance class [System.Data]System.Data.IDataReader Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteReader()
0x69c8  stloc.3
0x69c9  ldarg.1
0x69ca  newobj   instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::.ctor(valuetype [mscorlib]System.Guid)
0x69cf  stloc.0
0x69d0  ldloc.0
0x69d1  newobj   instance void Microsoft.ReportingServices.Library.SqlScheduleHelper::.ctor(class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task task)
0x69d6  dup
0x69d7  ldloc.3
0x69d8  callvirt instance void Microsoft.ReportingServices.Library.SqlScheduleHelper::PopulateSchedule(class [System.Data]System.Data.IDataReader reader)
0x69dd  callvirt instance class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task Microsoft.ReportingServices.Library.SqlScheduleHelper::get_Task()
0x69e2  stloc.0
0x69e3  leave.s  loc_69EF
0x69e5  ldloc.3
0x69e6  brfalse.s loc_69EE
0x69e8  ldloc.3
0x69e9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x69ee  endfinally
0x69ef  leave.s  loc_69FB
0x69f1  ldloc.1
0x69f2  brfalse.s loc_69FA
0x69f4  ldloc.1
0x69f5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x69fa  endfinally
0x69fb  leave.s  loc_6A1A
0x69fd  stloc.s  4
0x69ff  ldloc.s  4
0x6a01  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ReportServerStorageException::get_IsSqlException()
0x6a06  brfalse.s loc_6A16
0x6a08  ldloc.s  4
0x6a0a  callvirt instance int32 [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ReportServerStorageException::get_SqlErrorNumber()
0x6a0f  ldc.i4   0x37B6
0x6a14  beq.s    loc_6A18
0x6a16  rethrow
0x6a18  leave.s  loc_6A1A
0x6a1a  ldloc.0
0x6a1b  ret
```
