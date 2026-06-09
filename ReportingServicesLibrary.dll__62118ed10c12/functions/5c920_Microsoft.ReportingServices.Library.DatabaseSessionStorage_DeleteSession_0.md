# Microsoft.ReportingServices.Library.DatabaseSessionStorage::DeleteSession_0

- ea: `0x5c920`
- end: `0x5cad1`
- name: `Microsoft.ReportingServices.Library.DatabaseSessionStorage::DeleteSession_0`
- size: `433`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x5c360`
- `0x5c8d0`

## callees

- `0xf570`
- `0x5c920`
- `0x5e0d0`
- `0x5ea50`
- `0x5ea70`
- `0x5ea80`

## string_xrefs

- `0x5c9fc`: `@OwnerSid`
- `0x5c9cf`: `@ReportPath`
- `0x5c932`: `Removing report with path '{0}' from session DB`
- `0x5c981`: `RemoveReportFromSession`
- `0x5caac`: `Sql Error in RemoveReportFromDB: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x5c920  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_SessionTrace()
0x5c925  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x5c92a  brfalse.s loc_5C955
0x5c92c  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_SessionTrace()
0x5c931  ldc.i4.4
0x5c932  ldstr    aRemovingReport// "Removing report with path '{0}' from se"...
0x5c937  ldc.i4.1
0x5c938  newarr   [mscorlib]System.Object
0x5c93d  dup
0x5c93e  ldc.i4.0
0x5c93f  ldarg.0
0x5c940  callvirt instance class Microsoft.ReportingServices.Library.ReportItem Microsoft.ReportingServices.Library.SessionReportItem::get_Report()
0x5c945  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath Microsoft.ReportingServices.Library.ReportItem::get_ItemPath()
0x5c94a  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_FullEditSessionIdentifier()
0x5c94f  stelem.ref
0x5c950  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x5c955  newobj   instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::.ctor()
0x5c95a  stloc.0
0x5c95b  ldloc.0
0x5c95c  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::WillDisconnectStorage()
0x5c961  ldloc.0
0x5c962  callvirt instance class [mscorlib]System.IDisposable [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::EnterThreadSafeContext()
0x5c967  stloc.1
0x5c968  ldloc.0
0x5c969  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::get_Connection()
0x5c96e  stloc.2
0x5c96f  ldloc.0
0x5c970  ldc.i4   0x1000
0x5c975  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::BeginTransaction(valuetype [System.Data]System.Data.IsolationLevel)
0x5c97a  ldloc.0
0x5c97b  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::get_Transaction()
0x5c980  stloc.3
0x5c981  ldstr    aRemovereportfr// "RemoveReportFromSession"
0x5c986  ldloc.2
0x5c987  ldloc.3
0x5c988  newobj   instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::.ctor(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction)
0x5c98d  call     class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::GetInstrumentedSqlCommand(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand)
0x5c992  stloc.s  4
0x5c994  ldloc.s  4
0x5c996  ldc.i4.4
0x5c997  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x5c99c  ldloc.s  4
0x5c99e  call     int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::get_SqlCommandTimeoutSeconds()
0x5c9a3  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_CommandTimeout(int32)
0x5c9a8  ldloc.s  4
0x5c9aa  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5c9af  ldstr    aSessionid_0// "@SessionID"
0x5c9b4  ldc.i4.s 0x16
0x5c9b6  ldc.i4.s 0x20
0x5c9b8  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x5c9bd  ldarg.0
0x5c9be  callvirt instance string Microsoft.ReportingServices.Library.SessionReportItem::get_SessionId()
0x5c9c3  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5c9c8  ldloc.s  4
0x5c9ca  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5c9cf  ldstr    aReportpath// "@ReportPath"
0x5c9d4  ldc.i4.s 0xC
0x5c9d6  ldc.i4   0x1B8
0x5c9db  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x5c9e0  ldarg.0
0x5c9e1  callvirt instance class Microsoft.ReportingServices.Library.ReportItem Microsoft.ReportingServices.Library.SessionReportItem::get_Report()
0x5c9e6  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath Microsoft.ReportingServices.Library.ReportItem::get_ItemPath()
0x5c9eb  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_FullEditSessionIdentifier()
0x5c9f0  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5c9f5  ldloc.s  4
0x5c9f7  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5c9fc  ldstr    aOwnersid// "@OwnerSid"
0x5ca01  ldc.i4.s 0x15
0x5ca03  ldc.i4.s 0x55
0x5ca05  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x5ca0a  ldarg.0
0x5ca0b  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.SessionReportItem::get_UserContext()
0x5ca10  call     unsigned int8[] Microsoft.ReportingServices.Library.Global::NameToSid(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext user)
0x5ca15  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5ca1a  ldloc.s  4
0x5ca1c  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5ca21  ldstr    aOwnername// "@OwnerName"
0x5ca26  ldc.i4.s 0xC
0x5ca28  ldc.i4   0x104
0x5ca2d  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x5ca32  ldarg.0
0x5ca33  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.SessionReportItem::get_UserContext()
0x5ca38  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_UserName()
0x5ca3d  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5ca42  ldloc.s  4
0x5ca44  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5ca49  ldstr    aAuthtype// "@AuthType"
0x5ca4e  ldc.i4.8
0x5ca4f  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5ca54  ldarg.0
0x5ca55  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.SessionReportItem::get_UserContext()
0x5ca5a  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AuthenticationType()
0x5ca5f  box      [mscorlib]System.Int32
0x5ca64  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5ca69  ldloc.s  4
0x5ca6b  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x5ca70  pop
0x5ca71  leave.s  loc_5CA7F
0x5ca73  ldloc.s  4
0x5ca75  brfalse.s loc_5CA7E
0x5ca77  ldloc.s  4
0x5ca79  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5ca7e  endfinally
0x5ca7f  leave.s  loc_5CA8B
0x5ca81  ldloc.1
0x5ca82  brfalse.s loc_5CA8A
0x5ca84  ldloc.1
0x5ca85  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5ca8a  endfinally
0x5ca8b  ldloc.0
0x5ca8c  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::CommitTransaction()
0x5ca91  leave.s  loc_5CAD0
0x5ca93  callvirt instance string [mscorlib]System.Object::ToString()
0x5ca98  stloc.s  5
0x5ca9a  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_SessionTrace()
0x5ca9f  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x5caa4  brfalse.s loc_5CAC1
0x5caa6  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_SessionTrace()
0x5caab  ldc.i4.1
0x5caac  ldstr    aSqlErrorInRemo// "Sql Error in RemoveReportFromDB: {0}"
0x5cab1  ldc.i4.1
0x5cab2  newarr   [mscorlib]System.Object
0x5cab7  dup
0x5cab8  ldc.i4.0
0x5cab9  ldloc.s  5
0x5cabb  stelem.ref
0x5cabc  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x5cac1  ldloc.0
0x5cac2  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::AbortTransaction()
0x5cac7  rethrow
0x5cac9  ldloc.0
0x5caca  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::DisconnectStorage()
0x5cacf  endfinally
0x5cad0  ret
```
