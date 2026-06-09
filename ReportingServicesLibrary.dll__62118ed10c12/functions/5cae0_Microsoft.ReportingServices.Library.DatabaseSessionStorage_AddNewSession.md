# Microsoft.ReportingServices.Library.DatabaseSessionStorage::AddNewSession

- ea: `0x5cae0`
- end: `0x5cfe1`
- name: `Microsoft.ReportingServices.Library.DatabaseSessionStorage::AddNewSession`
- size: `1281`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x5e830`

## callees

- `0xf570`
- `0x5cae0`
- `0x5dfd0`
- `0x5e010`
- `0x5e070`
- `0x5e090`
- `0x5e0b0`
- `0x5e0d0`
- `0x5e0e0`
- `0x5ea50`
- `0x5ea70`
- `0x5ea80`
- `0x5eab0`
- `0x5ead0`
- `0x5ebf0`
- `0x5ec30`
- `0x5ec50`
- `0x5ed30`
- `0x5ed50`
- `0x5edc0`
- `0x637b0`
- `0x637c0`

## string_xrefs

- `0x5cc32`: `@OwnerSid`
- `0x5cb5c`: `@ReportPath`
- `0x5cb0e`: `CreateSession`
- `0x5cbae`: `@ReportDefinitionPath`
- `0x5ccae`: `@SitePath`
- `0x5cd05`: `@CompiledDefinition`

## pseudocode

```c

```

## disassembly

```asm
0x5cae0  newobj   instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::.ctor()
0x5cae5  stloc.0
0x5cae6  ldloc.0
0x5cae7  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::WillDisconnectStorage()
0x5caec  ldloc.0
0x5caed  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::BeginTransaction()
0x5caf2  ldloc.0
0x5caf3  callvirt instance class [mscorlib]System.IDisposable [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::EnterThreadSafeContext()
0x5caf8  stloc.1
0x5caf9  ldarg.0
0x5cafa  callvirt instance class Microsoft.ReportingServices.Library.ReportItem Microsoft.ReportingServices.Library.SessionReportItem::get_Report()
0x5caff  pop
0x5cb00  ldloc.0
0x5cb01  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::get_Connection()
0x5cb06  stloc.2
0x5cb07  ldloc.0
0x5cb08  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::get_Transaction()
0x5cb0d  stloc.3
0x5cb0e  ldstr    aCreatesession// "CreateSession"
0x5cb13  ldloc.2
0x5cb14  ldloc.3
0x5cb15  newobj   instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::.ctor(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction)
0x5cb1a  call     class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::GetInstrumentedSqlCommand(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand)
0x5cb1f  stloc.s  4
0x5cb21  ldloc.s  4
0x5cb23  ldc.i4.4
0x5cb24  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x5cb29  ldloc.s  4
0x5cb2b  call     int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::get_SqlCommandTimeoutSeconds()
0x5cb30  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_CommandTimeout(int32)
0x5cb35  ldloc.s  4
0x5cb37  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5cb3c  ldstr    aSessionid_0// "@SessionID"
0x5cb41  ldc.i4.s 0x16
0x5cb43  ldc.i4.s 0x20
0x5cb45  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x5cb4a  ldarg.0
0x5cb4b  callvirt instance string Microsoft.ReportingServices.Library.SessionReportItem::get_SessionId()
0x5cb50  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5cb55  ldloc.s  4
0x5cb57  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5cb5c  ldstr    aReportpath// "@ReportPath"
0x5cb61  ldc.i4.s 0xC
0x5cb63  ldc.i4   0x1D0
0x5cb68  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x5cb6d  ldarg.0
0x5cb6e  callvirt instance class Microsoft.ReportingServices.Library.ReportItem Microsoft.ReportingServices.Library.SessionReportItem::get_Report()
0x5cb73  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath Microsoft.ReportingServices.Library.ReportItem::get_ItemPath()
0x5cb78  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_FullEditSessionIdentifier()
0x5cb7d  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5cb82  ldarg.0
0x5cb83  callvirt instance class Microsoft.ReportingServices.Library.ReportItem Microsoft.ReportingServices.Library.SessionReportItem::get_Report()
0x5cb88  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath Microsoft.ReportingServices.Library.ReportItem::get_ItemPath()
0x5cb8d  ldarg.0
0x5cb8e  callvirt instance class Microsoft.ReportingServices.Library.ReportItem Microsoft.ReportingServices.Library.SessionReportItem::get_Report()
0x5cb93  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath Microsoft.ReportingServices.Library.ReportItem::get_ReportDefinitionPath()
0x5cb98  beq.s    loc_5CBD4
0x5cb9a  ldarg.0
0x5cb9b  callvirt instance class Microsoft.ReportingServices.Library.ReportItem Microsoft.ReportingServices.Library.SessionReportItem::get_Report()
0x5cba0  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath Microsoft.ReportingServices.Library.ReportItem::get_ReportDefinitionPath()
0x5cba5  brfalse.s loc_5CBD4
0x5cba7  ldloc.s  4
0x5cba9  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5cbae  ldstr    aReportdefiniti_0// "@ReportDefinitionPath"
0x5cbb3  ldc.i4.s 0xC
0x5cbb5  ldc.i4   0x1D0
0x5cbba  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x5cbbf  ldarg.0
0x5cbc0  callvirt instance class Microsoft.ReportingServices.Library.ReportItem Microsoft.ReportingServices.Library.SessionReportItem::get_Report()
0x5cbc5  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath Microsoft.ReportingServices.Library.ReportItem::get_ReportDefinitionPath()
0x5cbca  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_FullEditSessionIdentifier()
0x5cbcf  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5cbd4  ldarg.0
0x5cbd5  callvirt instance int32 Microsoft.ReportingServices.Library.SessionReportItem::get_Timeout()
0x5cbda  stloc.s  5
0x5cbdc  ldloc.s  5
0x5cbde  brtrue.s loc_5CBEB
0x5cbe0  ldstr    aUnexpectedValu_1// "unexpected value for session timeout: 0"
0x5cbe5  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x5cbea  throw
0x5cbeb  ldloc.s  4
0x5cbed  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5cbf2  ldstr    aTimeout// "@Timeout"
0x5cbf7  ldc.i4.8
0x5cbf8  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5cbfd  ldloc.s  5
0x5cbff  box      [mscorlib]System.Int32
0x5cc04  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5cc09  ldloc.s  4
0x5cc0b  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5cc10  ldstr    aAutorefreshsec// "@AutoRefreshSeconds"
0x5cc15  ldc.i4.8
0x5cc16  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5cc1b  ldarg.0
0x5cc1c  callvirt instance int32 Microsoft.ReportingServices.Library.SessionReportItem::get_AutoRefreshSeconds()
0x5cc21  box      [mscorlib]System.Int32
0x5cc26  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5cc2b  ldloc.s  4
0x5cc2d  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5cc32  ldstr    aOwnersid// "@OwnerSid"
0x5cc37  ldc.i4.s 0x15
0x5cc39  ldc.i4.s 0x55
0x5cc3b  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x5cc40  ldarg.0
0x5cc41  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.SessionReportItem::get_UserContext()
0x5cc46  call     unsigned int8[] Microsoft.ReportingServices.Library.Global::NameToSid(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext user)
0x5cc4b  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5cc50  ldloc.s  4
0x5cc52  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5cc57  ldstr    aOwnername// "@OwnerName"
0x5cc5c  ldc.i4.s 0xC
0x5cc5e  ldc.i4   0x104
0x5cc63  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x5cc68  ldarg.0
0x5cc69  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.SessionReportItem::get_UserContext()
0x5cc6e  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_UserName()
0x5cc73  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5cc78  ldloc.s  4
0x5cc7a  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5cc7f  ldstr    aAuthtype// "@AuthType"
0x5cc84  ldc.i4.8
0x5cc85  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5cc8a  ldarg.0
0x5cc8b  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.SessionReportItem::get_UserContext()
0x5cc90  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AuthenticationType()
0x5cc95  box      [mscorlib]System.Int32
0x5cc9a  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5cc9f  ldarg.0
0x5cca0  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath Microsoft.ReportingServices.Library.SessionReportItem::get_SitePath()
0x5cca5  brfalse.s loc_5CCCF
0x5cca7  ldloc.s  4
0x5cca9  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5ccae  ldstr    aSitepath// "@SitePath"
0x5ccb3  ldc.i4.s 0xC
0x5ccb5  ldc.i4   0x1B8
0x5ccba  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x5ccbf  ldarg.0
0x5ccc0  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath Microsoft.ReportingServices.Library.SessionReportItem::get_SitePath()
0x5ccc5  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x5ccca  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5cccf  ldloc.s  4
0x5ccd1  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5ccd6  ldstr    aSitezone// "@SiteZone"
0x5ccdb  ldc.i4.8
0x5ccdc  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5cce1  ldarg.0
0x5cce2  callvirt instance int32 Microsoft.ReportingServices.Library.SessionReportItem::get_SiteZone()
0x5cce7  box      [mscorlib]System.Int32
0x5ccec  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5ccf1  ldarg.0
0x5ccf2  callvirt instance class Microsoft.ReportingServices.Library.ReportItem Microsoft.ReportingServices.Library.SessionReportItem::get_Report()
0x5ccf7  callvirt instance class Microsoft.ReportingServices.Library.ReportSnapshot Microsoft.ReportingServices.Library.ReportItem::get_CompiledDefinition()
0x5ccfc  brfalse.s loc_5CD2B
0x5ccfe  ldloc.s  4
0x5cd00  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5cd05  ldstr    aCompileddefini_1// "@CompiledDefinition"
0x5cd0a  ldc.i4.s 0xE
0x5cd0c  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5cd11  ldarg.0
0x5cd12  callvirt instance class Microsoft.ReportingServices.Library.ReportItem Microsoft.ReportingServices.Library.SessionReportItem::get_Report()
0x5cd17  callvirt instance class Microsoft.ReportingServices.Library.ReportSnapshot Microsoft.ReportingServices.Library.ReportItem::get_CompiledDefinition()
0x5cd1c  callvirt instance valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.SnapshotBase::get_SnapshotDataID()
0x5cd21  box      [mscorlib]System.Guid
0x5cd26  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5cd2b  ldarg.0
0x5cd2c  callvirt instance class Microsoft.ReportingServices.Library.ReportItem Microsoft.ReportingServices.Library.SessionReportItem::get_Report()
0x5cd31  callvirt instance class Microsoft.ReportingServices.Library.ReportSnapshot Microsoft.ReportingServices.Library.ReportItem::get_SnapshotData()
0x5cd36  brfalse.s loc_5CD91
0x5cd38  ldloc.s  4
0x5cd3a  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5cd3f  ldstr    aSnapshotdataid// "@SnapshotDataID"
0x5cd44  ldc.i4.s 0xE
0x5cd46  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5cd4b  ldarg.0
0x5cd4c  callvirt instance class Microsoft.ReportingServices.Library.ReportItem Microsoft.ReportingServices.Library.SessionReportItem::get_Report()
0x5cd51  callvirt instance class Microsoft.ReportingServices.Library.ReportSnapshot Microsoft.ReportingServices.Library.ReportItem::get_SnapshotData()
0x5cd56  callvirt instance valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.SnapshotBase::get_SnapshotDataID()
0x5cd5b  box      [mscorlib]System.Guid
0x5cd60  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5cd65  ldloc.s  4
0x5cd67  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5cd6c  ldstr    aIspermanentsna// "@IsPermanentSnapshot"
0x5cd71  ldc.i4.2
0x5cd72  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5cd77  ldarg.0
0x5cd78  callvirt instance class Microsoft.ReportingServices.Library.ReportItem Microsoft.ReportingServices.Library.SessionReportItem::get_Report()
0x5cd7d  callvirt instance class Microsoft.ReportingServices.Library.ReportSnapshot Microsoft.ReportingServices.Library.ReportItem::get_SnapshotData()
0x5cd82  callvirt instance bool Microsoft.ReportingServices.Library.SnapshotBase::get_IsPermanentSnapshot()
0x5cd87  box      [mscorlib]System.Boolean
0x5cd8c  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5cd91  ldarg.0
0x5cd92  callvirt instance class Microsoft.ReportingServices.Library.ReportItem Microsoft.ReportingServices.Library.SessionReportItem::get_Report()
0x5cd97  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.ReportItem::get_HistoryDate()
0x5cd9c  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x5cda1  call     bool [mscorlib]System.DateTime::op_Inequality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x5cda6  brfalse.s loc_5CDCF
0x5cda8  ldloc.s  4
0x5cdaa  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5cdaf  ldstr    aHistorydate// "@HistoryDate"
0x5cdb4  ldc.i4.4
0x5cdb5  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5cdba  ldarg.0
0x5cdbb  callvirt instance class Microsoft.ReportingServices.Library.ReportItem Microsoft.ReportingServices.Library.SessionReportItem::get_Report()
0x5cdc0  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.ReportItem::get_HistoryDate()
0x5cdc5  box      [mscorlib]System.DateTime
0x5cdca  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5cdcf  ldarg.0
0x5cdd0  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.RuntimeDataSourceInfoCollection Microsoft.ReportingServices.Library.SessionReportItem::get_Datasources()
0x5cdd5  brfalse.s loc_5CDF9
0x5cdd7  ldloc.s  4
0x5cdd9  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5cdde  ldstr    aDatasourceinfo_2// "@DataSourceInfo"
0x5cde3  ldc.i4.7
0x5cde4  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5cde9  ldarg.0
0x5cdea  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.RuntimeDataSourceInfoCollection Microsoft.ReportingServices.Library.SessionReportItem::get_Datasources()
0x5cdef  callvirt instance unsigned int8[] [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.RuntimeDataSourceInfoCollection::Serialize()
0x5cdf4  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5cdf9  ldarg.0
0x5cdfa  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.RuntimeDataSetInfoCollection Microsoft.ReportingServices.Library.SessionReportItem::get_DataSets()
0x5cdff  brfalse.s loc_5CE23
0x5ce01  ldloc.s  4
0x5ce03  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5ce08  ldstr    aDatasetinfo// "@DataSetInfo"
0x5ce0d  ldc.i4.7
0x5ce0e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5ce13  ldarg.0
0x5ce14  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.RuntimeDataSetInfoCollection Microsoft.ReportingServices.Library.SessionReportItem::get_DataSets()
0x5ce19  callvirt instance unsigned int8[] [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.RuntimeDataSetInfoCollection::Serialize()
0x5ce1e  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5ce23  ldarg.0
0x5ce24  callvirt instance class Microsoft.ReportingServices.Library.ReportItem Microsoft.ReportingServices.Library.SessionReportItem::get_Report()
0x5ce29  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ParameterInfoCollection Microsoft.ReportingServices.Library.ReportItem::get_EffectiveParams()
0x5ce2e  brfalse.s loc_5CE53
0x5ce30  ldloc.s  4
0x5ce32  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5ce37  ldstr    aEffectiveparam// "@EffectiveParams"
0x5ce3c  ldc.i4.s 0xB
0x5ce3e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5ce43  ldarg.0
0x5ce44  callvirt instance class Microsoft.ReportingServices.Library.ReportItem Microsoft.ReportingServices.Library.SessionReportItem::get_Report()
0x5ce49  callvirt instance string Microsoft.ReportingServices.Library.ReportItem::get_EffectiveParamsXml()
0x5ce4e  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5ce53  ldarg.0
0x5ce54  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.PageProperties Microsoft.ReportingServices.Library.SessionReportItem::get_PageProperties()
0x5ce59  brfalse  loc_5CF48
0x5ce5e  ldloc.s  4
0x5ce60  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5ce65  ldstr    aPageheight_0// "@PageHeight"
0x5ce6a  ldc.i4.6
0x5ce6b  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5ce70  ldarg.0
0x5ce71  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.PageProperties Microsoft.ReportingServices.Library.SessionReportItem::get_PageProperties()
0x5ce76  callvirt instance float64 [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.PageProperties::get_PageHeight()
0x5ce7b  box      [mscorlib]System.Double
0x5ce80  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5ce85  ldloc.s  4
0x5ce87  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5ce8c  ldstr    aPagewidth_0// "@PageWidth"
0x5ce91  ldc.i4.6
0x5ce92  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5ce97  ldarg.0
0x5ce98  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.PageProperties Microsoft.ReportingServices.Library.SessionReportItem::get_PageProperties()
0x5ce9d  callvirt instance float64 [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.PageProperties::get_PageWidth()
0x5cea2  box      [mscorlib]System.Double
0x5cea7  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5ceac  ldloc.s  4
0x5ceae  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5ceb3  ldstr    aTopmargin_0// "@TopMargin"
0x5ceb8  ldc.i4.6
0x5ceb9  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5cebe  ldarg.0
0x5cebf  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.PageProperties Microsoft.ReportingServices.Library.SessionReportItem::get_PageProperties()
0x5cec4  callvirt instance float64 [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.PageProperties::get_TopMargin()
0x5cec9  box      [mscorlib]System.Double
0x5cece  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5ced3  ldloc.s  4
0x5ced5  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5ceda  ldstr    aBottommargin_0// "@BottomMargin"
0x5cedf  ldc.i4.6
0x5cee0  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5cee5  ldarg.0
0x5cee6  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.PageProperties Microsoft.ReportingServices.Library.SessionReportItem::get_PageProperties()
0x5ceeb  callvirt instance float64 [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.PageProperties::get_BottomMargin()
0x5cef0  box      [mscorlib]System.Double
0x5cef5  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5cefa  ldloc.s  4
0x5cefc  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5cf01  ldstr    aLeftmargin_0// "@LeftMargin"
0x5cf06  ldc.i4.6
0x5cf07  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5cf0c  ldarg.0
0x5cf0d  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.PageProperties Microsoft.ReportingServices.Library.SessionReportItem::get_PageProperties()
0x5cf12  callvirt instance float64 [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.PageProperties::get_LeftMargin()
0x5cf17  box      [mscorlib]System.Double
0x5cf1c  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5cf21  ldloc.s  4
0x5cf23  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5cf28  ldstr    aRightmargin_0// "@RightMargin"
0x5cf2d  ldc.i4.6
  ... truncated ...
```
