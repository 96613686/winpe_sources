# Microsoft.ReportingServices.Library.SqlAgentScheduler::CreateCategoryID

- ea: `0x6240`
- end: `0x62de`
- name: `Microsoft.ReportingServices.Library.SqlAgentScheduler::CreateCategoryID`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x61a0`

## callees

- `0x61e0`
- `0x6240`
- `0x6c00`
- `0x70e0`
- `0x7320`
- `0x8270`

## pseudocode

```c

```

## disassembly

```asm
0x6240  ldarg.0
0x6241  ldstr    aMsdbDboSpAddCa// "msdb.dbo.sp_add_category"
0x6246  ldnull
0x6247  callvirt instance class Microsoft.ReportingServices.Library.InstrumentedSqlCommand Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string storedProcedureName, [opt] class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection connection)
0x624c  stloc.0
0x624d  ldstr    aClass// "@class"
0x6252  ldc.i4.s 0x16
0x6254  ldc.i4.8
0x6255  newobj   instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x625a  stloc.1
0x625b  ldloc.1
0x625c  ldstr    aJob// "JOB"
0x6261  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x6266  ldloc.0
0x6267  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x626c  ldloc.1
0x626d  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter)
0x6272  pop
0x6273  ldstr    aType_0// "@type"
0x6278  ldc.i4.s 0x16
0x627a  ldc.i4.s 0xC
0x627c  newobj   instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x6281  stloc.1
0x6282  ldloc.1
0x6283  ldstr    aLocal// "LOCAL"
0x6288  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x628d  ldloc.0
0x628e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x6293  ldloc.1
0x6294  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter)
0x6299  pop
0x629a  ldstr    aName_1// "@name"
0x629f  ldc.i4.s 0xC
0x62a1  ldc.i4   0x80
0x62a6  newobj   instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::.ctor(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x62ab  stloc.1
0x62ac  ldloc.1
0x62ad  call     string Microsoft.ReportingServices.Library.RepLibRes::get_ReportServiceCategoryName()
0x62b2  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x62b7  ldloc.0
0x62b8  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x62bd  ldloc.1
0x62be  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter)
0x62c3  pop
0x62c4  ldloc.0
0x62c5  callvirt instance int32 Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x62ca  pop
0x62cb  leave.s  loc_62D7
0x62cd  ldloc.0
0x62ce  brfalse.s loc_62D6
0x62d0  ldloc.0
0x62d1  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x62d6  endfinally
0x62d7  ldarg.0
0x62d8  call     instance void Microsoft.ReportingServices.Library.SqlAgentScheduler::GetCategoryIDFromMSDB()
0x62dd  ret
```
