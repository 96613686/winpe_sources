# Microsoft.ReportingServices.Library.ReportExecutionCacheDb::GetCacheOptions

- ea: `0x65530`
- end: `0x655e7`
- name: `Microsoft.ReportingServices.Library.ReportExecutionCacheDb::GetCacheOptions`
- size: `183`
- prototype: ``
- caller_count: `5`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x1dbf0`
- `0x25520`
- `0x314f0`
- `0x37dc0`
- `0x38a00`

## callees

- `0x65530`
- `0x716f0`
- `0x71710`
- `0x71c10`
- `0x71cc0`

## string_xrefs

- `0x65549`: `@Path`
- `0x65537`: `GetCacheOptions`

## pseudocode

```c

```

## disassembly

```asm
0x65530  ldarg.2
0x65531  ldc.i4.0
0x65532  stind.i1
0x65533  ldarg.3
0x65534  ldnull
0x65535  stind.ref
0x65536  ldarg.0
0x65537  ldstr    aGetcacheoption_0// "GetCacheOptions"
0x6553c  ldnull
0x6553d  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x65542  stloc.0
0x65543  ldloc.0
0x65544  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x65549  ldstr    aPath// "@Path"
0x6554e  ldarg.1
0x6554f  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x65554  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x65559  ldc.i4.s 0xC
0x6555b  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x65560  ldloc.0
0x65561  callvirt instance class [System.Data]System.Data.IDataReader [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteReader()
0x65566  stloc.1
0x65567  ldloc.1
0x65568  callvirt instance bool [System.Data]System.Data.IDataReader::Read()
0x6556d  brtrue.s loc_65571
0x6556f  leave.s  loc_655E6
0x65571  ldarg.2
0x65572  ldc.i4.1
0x65573  stind.i1
0x65574  ldloc.1
0x65575  ldc.i4.0
0x65576  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetInt32(int32)
0x6557b  dup
0x6557c  ldc.i4.1
0x6557d  bne.un.s loc_65595
0x6557f  newobj   instance void Microsoft.ReportingServices.Library.Soap.TimeExpiration::.ctor()
0x65584  stloc.2
0x65585  ldloc.2
0x65586  ldloc.1
0x65587  ldc.i4.1
0x65588  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetInt32(int32)
0x6558d  stfld    int32 Microsoft.ReportingServices.Library.Soap.TimeExpiration::Minutes
0x65592  ldarg.3
0x65593  ldloc.2
0x65594  stind.ref
0x65595  ldc.i4.2
0x65596  bne.un.s loc_655D0
0x65598  newobj   instance void Microsoft.ReportingServices.Library.Soap.ScheduleExpiration::.ctor()
0x6559d  stloc.3
0x6559e  ldloc.1
0x6559f  ldc.i4.2
0x655a0  ldc.i4.0
0x655a1  newobj   instance void [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::.ctor(class [System.Data]System.Data.IDataRecord, int32, bool)
0x655a6  stloc.s  4
0x655a8  ldloc.s  4
0x655aa  callvirt instance valuetype [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.ScheduleType [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task::get_Type()
0x655af  brtrue.s loc_655C0
0x655b1  ldloc.3
0x655b2  ldloc.s  4
0x655b4  call     class Microsoft.ReportingServices.Library.Soap.ScheduleReference Microsoft.ReportingServices.Library.Soap.ScheduleReference::TaskToThis(class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task task)
0x655b9  stfld    class Microsoft.ReportingServices.Library.Soap.ScheduleDefinitionOrReference Microsoft.ReportingServices.Library.Soap.ScheduleExpiration::Schedule
0x655be  br.s     loc_655CD
0x655c0  ldloc.3
0x655c1  ldloc.s  4
0x655c3  call     class Microsoft.ReportingServices.Library.Soap.ScheduleDefinition Microsoft.ReportingServices.Library.Soap.ScheduleDefinition::TaskToThis(class [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Task task)
0x655c8  stfld    class Microsoft.ReportingServices.Library.Soap.ScheduleDefinitionOrReference Microsoft.ReportingServices.Library.Soap.ScheduleExpiration::Schedule
0x655cd  ldarg.3
0x655ce  ldloc.3
0x655cf  stind.ref
0x655d0  leave.s  loc_655E6
0x655d2  ldloc.1
0x655d3  brfalse.s loc_655DB
0x655d5  ldloc.1
0x655d6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x655db  endfinally
0x655dc  ldloc.0
0x655dd  brfalse.s loc_655E5
0x655df  ldloc.0
0x655e0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x655e5  endfinally
0x655e6  ret
```
