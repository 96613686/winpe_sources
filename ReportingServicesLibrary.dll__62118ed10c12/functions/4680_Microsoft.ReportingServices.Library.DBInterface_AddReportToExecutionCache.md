# Microsoft.ReportingServices.Library.DBInterface::AddReportToExecutionCache

- ea: `0x4680`
- end: `0x4829`
- name: `Microsoft.ReportingServices.Library.DBInterface::AddReportToExecutionCache`
- size: `425`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x2eca0`

## callees

- `0x4680`
- `0xf310`
- `0xf320`
- `0x47f90`
- `0x5f8b0`
- `0x5f8c0`
- `0x637b0`

## string_xrefs

- `0x4681`: `AddReportToCache`
- `0x4713`: `@CacheLimit`

## pseudocode

```c

```

## disassembly

```asm
0x4680  ldarg.0
0x4681  ldstr    aAddreporttocac// "AddReportToCache"
0x4686  ldnull
0x4687  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x468c  stloc.0
0x468d  ldloc.0
0x468e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x4693  ldstr    aReportid// "@ReportID"
0x4698  ldarg.1
0x4699  box      [mscorlib]System.Guid
0x469e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x46a3  ldc.i4.s 0xE
0x46a5  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x46aa  ldloc.0
0x46ab  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x46b0  ldstr    aSnapshotdataid// "@SnapshotDataID"
0x46b5  ldc.i4.s 0xE
0x46b7  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x46bc  dup
0x46bd  ldarg.2
0x46be  callvirt instance valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.SnapshotBase::get_SnapshotDataID()
0x46c3  box      [mscorlib]System.Guid
0x46c8  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x46cd  ldloc.0
0x46ce  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x46d3  ldstr    aExecutiondate// "@ExecutionDate"
0x46d8  ldarg.3
0x46d9  box      [mscorlib]System.DateTime
0x46de  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x46e3  ldc.i4.4
0x46e4  callvirt instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter::set_SqlDbType(valuetype [System.Data]System.Data.SqlDbType)
0x46e9  ldarg.s  4
0x46eb  brfalse.s loc_472D
0x46ed  ldloc.0
0x46ee  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x46f3  ldstr    aEditsessiontim// "@EditSessionTimeout"
0x46f8  ldc.i4.8
0x46f9  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x46fe  call     int32 Microsoft.ReportingServices.Library.Global::get_EditSessionTimeoutMinutes()
0x4703  box      [mscorlib]System.Int32
0x4708  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x470d  ldloc.0
0x470e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x4713  ldstr    aCachelimit// "@CacheLimit"
0x4718  ldc.i4.8
0x4719  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x471e  call     int32 Microsoft.ReportingServices.Library.Global::get_EditSessionCacheLimit()
0x4723  box      [mscorlib]System.Int32
0x4728  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x472d  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x4732  ldarg.2
0x4733  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ParameterInfoCollection Microsoft.ReportingServices.Library.ServerSnapshot::get_SnapshotParameters()
0x4738  ldnull
0x4739  cgt.un
0x473b  ldstr    aSnapshotParame// "snapshot parameters"
0x4740  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x4745  ldloc.0
0x4746  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x474b  ldstr    aQueryparamshas// "@QueryParamsHash"
0x4750  ldc.i4.8
0x4751  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x4756  ldarg.2
0x4757  callvirt instance int32 Microsoft.ReportingServices.Library.ServerSnapshot::get_SnapshotQueryParametersHash()
0x475c  box      [mscorlib]System.Int32
0x4761  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x4766  ldloc.0
0x4767  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x476c  ldstr    aExpirationdate// "@ExpirationDate"
0x4771  ldc.i4.4
0x4772  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x4777  stloc.1
0x4778  ldloc.1
0x4779  ldc.i4.2
0x477a  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x477f  ldloc.0
0x4780  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x4785  ldstr    aScheduleid// "@ScheduleID"
0x478a  ldc.i4.s 0xE
0x478c  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x4791  stloc.2
0x4792  ldloc.2
0x4793  ldc.i4.2
0x4794  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Direction(valuetype [System.Data]System.Data.ParameterDirection)
0x4799  ldloc.0
0x479a  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x479f  pop
0x47a0  callvirt instance object [System.Data]System.Data.Common.DbParameter::get_Value()
0x47a5  unbox.any [mscorlib]System.Guid
0x47aa  pop
0x47ab  ldarg.s  5
0x47ad  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x47b2  stobj    [mscorlib]System.DateTime
0x47b7  ldloc.1
0x47b8  callvirt instance object [System.Data]System.Data.Common.DbParameter::get_Value()
0x47bd  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x47c2  beq.s    loc_47D6
0x47c4  ldarg.s  5
0x47c6  ldloc.1
0x47c7  callvirt instance object [System.Data]System.Data.Common.DbParameter::get_Value()
0x47cc  unbox.any [mscorlib]System.DateTime
0x47d1  stobj    [mscorlib]System.DateTime
0x47d6  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x47db  stloc.3
0x47dc  ldloc.2
0x47dd  callvirt instance object [System.Data]System.Data.Common.DbParameter::get_Value()
0x47e2  ldsfld   class [mscorlib]System.DBNull [mscorlib]System.DBNull::Value
0x47e7  beq.s    loc_47F5
0x47e9  ldloc.2
0x47ea  callvirt instance object [System.Data]System.Data.Common.DbParameter::get_Value()
0x47ef  unbox.any [mscorlib]System.Guid
0x47f4  stloc.3
0x47f5  ldloc.3
0x47f6  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x47fb  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4800  brfalse.s loc_481C
0x4802  ldarg.s  5
0x4804  ldarg.0
0x4805  ldfld    class Microsoft.ReportingServices.Library.SchedulingDBInterface Microsoft.ReportingServices.Library.DBInterface::m_scheduleDB
0x480a  ldloc.3
0x480b  ldarg.s  5
0x480d  ldobj    [mscorlib]System.DateTime
0x4812  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.SchedulingDBInterface::CheckNextRunTime(valuetype [mscorlib]System.Guid scheduleID, valuetype [mscorlib]System.DateTime nextRunTime)
0x4817  stobj    [mscorlib]System.DateTime
0x481c  leave.s  loc_4828
0x481e  ldloc.0
0x481f  brfalse.s loc_4827
0x4821  ldloc.0
0x4822  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4827  endfinally
0x4828  ret
```
