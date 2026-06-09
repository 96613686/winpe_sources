# Microsoft.ReportingServices.Library.SqlAgentScheduler::GetCategoryIDFromMSDB

- ea: `0x61e0`
- end: `0x623c`
- name: `Microsoft.ReportingServices.Library.SqlAgentScheduler::GetCategoryIDFromMSDB`
- size: `92`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x61a0`
- `0x6240`

## callees

- `0x61e0`
- `0x6c00`
- `0x7120`
- `0x8270`

## pseudocode

```c

```

## disassembly

```asm
0x61e0  ldc.i4.0
0x61e1  stsfld   int32 Microsoft.ReportingServices.Library.SqlAgentScheduler::m_categoryId
0x61e6  ldarg.0
0x61e7  ldstr    aMsdbDboSpHelpC// "msdb.dbo.sp_help_category"
0x61ec  ldnull
0x61ed  callvirt instance class Microsoft.ReportingServices.Library.InstrumentedSqlCommand Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string storedProcedureName, [opt] class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection connection)
0x61f2  stloc.0
0x61f3  ldloc.0
0x61f4  callvirt instance class [System.Data]System.Data.IDataReader Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteReader()
0x61f9  stloc.1
0x61fa  br.s     loc_621D
0x61fc  ldloc.1
0x61fd  ldc.i4.2
0x61fe  callvirt instance string [System.Data]System.Data.IDataRecord::GetString(int32)
0x6203  call     string Microsoft.ReportingServices.Library.RepLibRes::get_ReportServiceCategoryName()
0x6208  call     bool [mscorlib]System.String::op_Equality(string, string)
0x620d  brfalse.s loc_621D
0x620f  ldloc.1
0x6210  ldc.i4.0
0x6211  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetInt32(int32)
0x6216  stsfld   int32 Microsoft.ReportingServices.Library.SqlAgentScheduler::m_categoryId
0x621b  leave.s  loc_623B
0x621d  ldloc.1
0x621e  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x6223  brtrue.s loc_61FC
0x6225  leave.s  loc_623B
0x6227  ldloc.1
0x6228  brfalse.s loc_6230
0x622a  ldloc.1
0x622b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x6230  endfinally
0x6231  ldloc.0
0x6232  brfalse.s loc_623A
0x6234  ldloc.0
0x6235  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x623a  endfinally
0x623b  ret
```
