# Microsoft.ReportingServices.Library.ReportExecutionCacheDb::SetCacheOptions

- ea: `0x655f0`
- end: `0x656cb`
- name: `Microsoft.ReportingServices.Library.ReportExecutionCacheDb::SetCacheOptions`
- size: `219`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x37dc0`
- `0x395c0`

## callees

- `0x655f0`
- `0x65830`

## string_xrefs

- `0x65603`: `@Path`
- `0x655f1`: `SetCacheOptions`
- `0x65620`: `@CacheReport`
- `0x65656`: `@CacheExpiration`

## pseudocode

```c

```

## disassembly

```asm
0x655f0  ldarg.0
0x655f1  ldstr    aSetcacheoption_0// "SetCacheOptions"
0x655f6  ldnull
0x655f7  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x655fc  stloc.0
0x655fd  ldloc.0
0x655fe  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x65603  ldstr    aPath// "@Path"
0x65608  ldarg.1
0x65609  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x6560e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x65613  ldc.i4.s 0xC
0x65615  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x6561a  ldloc.0
0x6561b  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x65620  ldstr    aCachereport// "@CacheReport"
0x65625  ldarg.3
0x65626  box      [mscorlib]System.Boolean
0x6562b  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x65630  ldc.i4.2
0x65631  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x65636  ldc.i4.1
0x65637  stloc.1
0x65638  ldc.i4.0
0x65639  stloc.2
0x6563a  ldarg.s  4
0x6563c  isinst   Microsoft.ReportingServices.Library.Soap.TimeExpiration
0x65641  brfalse.s loc_65650
0x65643  ldarg.s  4
0x65645  castclass Microsoft.ReportingServices.Library.Soap.TimeExpiration
0x6564a  ldfld    int32 Microsoft.ReportingServices.Library.Soap.TimeExpiration::Minutes
0x6564f  stloc.2
0x65650  ldloc.0
0x65651  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x65656  ldstr    aCacheexpiratio// "@CacheExpiration"
0x6565b  ldloc.2
0x6565c  box      [mscorlib]System.Int32
0x65661  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x65666  ldc.i4.8
0x65667  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x6566c  ldnull
0x6566d  stloc.3
0x6566e  ldarg.s  4
0x65670  isinst   Microsoft.ReportingServices.Library.Soap.ScheduleExpiration
0x65675  brfalse.s loc_65684
0x65677  ldarg.s  4
0x65679  castclass Microsoft.ReportingServices.Library.Soap.ScheduleExpiration
0x6567e  ldfld    class Microsoft.ReportingServices.Library.Soap.ScheduleDefinitionOrReference Microsoft.ReportingServices.Library.Soap.ScheduleExpiration::Schedule
0x65683  stloc.3
0x65684  ldarg.0
0x65685  ldarg.2
0x65686  ldloc.3
0x65687  ldc.i4.3
0x65688  call     instance valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.ReportExecutionCacheDb::SetReportSchedule(valuetype [mscorlib]System.Guid reportID, class Microsoft.ReportingServices.Library.Soap.ScheduleDefinitionOrReference scheduleData, valuetype Microsoft.ReportingServices.Library.ReportScheduleActions reportAction)
0x6568d  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x65692  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x65697  brfalse.s loc_6569B
0x65699  ldc.i4.2
0x6569a  stloc.1
0x6569b  ldloc.0
0x6569c  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x656a1  ldstr    aExpirationflag// "@ExpirationFlags"
0x656a6  ldloc.1
0x656a7  box      ExpirationFlags
0x656ac  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x656b1  ldc.i4.8
0x656b2  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x656b7  ldloc.0
0x656b8  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x656bd  pop
0x656be  leave.s  loc_656CA
0x656c0  ldloc.0
0x656c1  brfalse.s loc_656C9
0x656c3  ldloc.0
0x656c4  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x656c9  endfinally
0x656ca  ret
```
