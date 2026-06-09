# Microsoft.ReportingServices.Library.DatabaseSessionStorage::SetSessionData_1

- ea: `0x5c460`
- end: `0x5c8c2`
- name: `Microsoft.ReportingServices.Library.DatabaseSessionStorage::SetSessionData_1`
- size: `1122`
- prototype: ``
- caller_count: `1`
- callee_count: `26`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x5c3f0`

## callees

- `0xf570`
- `0x5c460`
- `0x5dfd0`
- `0x5e010`
- `0x5e070`
- `0x5e090`
- `0x5e0d0`
- `0x5ea50`
- `0x5ea70`
- `0x5ea80`
- `0x5ea90`
- `0x5eab0`
- `0x5ead0`
- `0x5eaf0`
- `0x5eb20`
- `0x5eb70`
- `0x5ebf0`
- `0x5ec20`
- `0x5ec30`
- `0x5ec50`
- `0x5ed00`
- `0x5ede0`
- `0x60db0`
- `0x60e00`
- `0x637b0`
- `0x637c0`

## string_xrefs

- `0x5c61a`: `@OwnerSid`
- `0x5c472`: `Adding report with path '{0}' to session DB`
- `0x5c558`: `@ReportPath`

## pseudocode

```c

```

## disassembly

```asm
0x5c460  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_SessionTrace()
0x5c465  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x5c46a  brfalse.s loc_5C495
0x5c46c  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_SessionTrace()
0x5c471  ldc.i4.4
0x5c472  ldstr    aAddingReportWi// "Adding report with path '{0}' to sessio"...
0x5c477  ldc.i4.1
0x5c478  newarr   [mscorlib]System.Object
0x5c47d  dup
0x5c47e  ldc.i4.0
0x5c47f  ldarg.0
0x5c480  callvirt instance class Microsoft.ReportingServices.Library.ReportItem Microsoft.ReportingServices.Library.SessionReportItem::get_Report()
0x5c485  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath Microsoft.ReportingServices.Library.ReportItem::get_ItemPath()
0x5c48a  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_FullEditSessionIdentifier()
0x5c48f  stelem.ref
0x5c490  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x5c495  ldarg.0
0x5c496  callvirt instance valuetype SaveAction Microsoft.ReportingServices.Library.SessionReportItem::get_SaveFlags()
0x5c49b  ldc.i4.2
0x5c49c  bne.un.s loc_5C4CF
0x5c49e  ldarg.0
0x5c49f  callvirt instance class Microsoft.ReportingServices.Library.ISnapshotTransactionFactory Microsoft.ReportingServices.Library.SessionReportItem::get_SnapshotTransactionFactory()
0x5c4a4  callvirt instance class Microsoft.ReportingServices.Library.ISnapshotTransaction Microsoft.ReportingServices.Library.ISnapshotTransactionFactory::EnterTransactionContext()
0x5c4a9  stloc.0
0x5c4aa  ldarg.0
0x5c4ab  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.OnDemandProcessingResult Microsoft.ReportingServices.Library.SessionReportItem::get_ProcessingResult()
0x5c4b0  brfalse.s loc_5C4BD
0x5c4b2  ldarg.0
0x5c4b3  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.OnDemandProcessingResult Microsoft.ReportingServices.Library.SessionReportItem::get_ProcessingResult()
0x5c4b8  callvirt instance void [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.OnDemandProcessingResult::Save()
0x5c4bd  ldloc.0
0x5c4be  callvirt instance void Microsoft.ReportingServices.Library.ISnapshotTransaction::Commit()
0x5c4c3  leave.s  loc_5C4CF
0x5c4c5  ldloc.0
0x5c4c6  brfalse.s loc_5C4CE
0x5c4c8  ldloc.0
0x5c4c9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5c4ce  endfinally
0x5c4cf  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_SessionTrace()
0x5c4d4  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x5c4d9  brfalse.s loc_5C4EB
0x5c4db  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_SessionTrace()
0x5c4e0  ldc.i4.4
0x5c4e1  ldstr    aFinishedSerial// "Finished serializing report"
0x5c4e6  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x5c4eb  nop
0x5c4ec  ldarg.0
0x5c4ed  callvirt instance class Microsoft.ReportingServices.Library.ReportItem Microsoft.ReportingServices.Library.SessionReportItem::get_Report()
0x5c4f2  stloc.1
0x5c4f3  ldarg.1
0x5c4f4  callvirt instance class [mscorlib]System.IDisposable [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::EnterThreadSafeContext()
0x5c4f9  stloc.2
0x5c4fa  ldarg.1
0x5c4fb  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::get_Connection()
0x5c500  stloc.3
0x5c501  ldarg.1
0x5c502  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::get_Transaction()
0x5c507  stloc.s  4
0x5c509  ldstr    aSetsessiondata// "SetSessionData"
0x5c50e  ldloc.3
0x5c50f  ldloc.s  4
0x5c511  newobj   instance void [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand::.ctor(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlTransaction)
0x5c516  call     class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::GetInstrumentedSqlCommand(class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlCommand)
0x5c51b  stloc.s  5
0x5c51d  ldloc.s  5
0x5c51f  ldc.i4.4
0x5c520  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x5c525  ldloc.s  5
0x5c527  call     int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.ConnectionManager::get_SqlCommandTimeoutSeconds()
0x5c52c  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_CommandTimeout(int32)
0x5c531  ldloc.s  5
0x5c533  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5c538  ldstr    aSessionid_0// "@SessionID"
0x5c53d  ldc.i4.s 0x16
0x5c53f  ldc.i4.s 0x20
0x5c541  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x5c546  ldarg.0
0x5c547  callvirt instance string Microsoft.ReportingServices.Library.SessionReportItem::get_SessionId()
0x5c54c  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5c551  ldloc.s  5
0x5c553  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5c558  ldstr    aReportpath// "@ReportPath"
0x5c55d  ldc.i4.s 0xC
0x5c55f  ldc.i4   0x1B8
0x5c564  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x5c569  ldarg.0
0x5c56a  callvirt instance class Microsoft.ReportingServices.Library.ReportItem Microsoft.ReportingServices.Library.SessionReportItem::get_Report()
0x5c56f  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath Microsoft.ReportingServices.Library.ReportItem::get_ItemPath()
0x5c574  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_FullEditSessionIdentifier()
0x5c579  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5c57e  ldarg.0
0x5c57f  callvirt instance class Microsoft.ReportingServices.Library.ReportItem Microsoft.ReportingServices.Library.SessionReportItem::get_Report()
0x5c584  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.ReportItem::get_HistoryDate()
0x5c589  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x5c58e  call     bool [mscorlib]System.DateTime::op_Inequality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x5c593  brfalse.s loc_5C5BC
0x5c595  ldloc.s  5
0x5c597  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5c59c  ldstr    aHistorydate// "@HistoryDate"
0x5c5a1  ldc.i4.4
0x5c5a2  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5c5a7  ldarg.0
0x5c5a8  callvirt instance class Microsoft.ReportingServices.Library.ReportItem Microsoft.ReportingServices.Library.SessionReportItem::get_Report()
0x5c5ad  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.ReportItem::get_HistoryDate()
0x5c5b2  box      [mscorlib]System.DateTime
0x5c5b7  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5c5bc  ldarg.0
0x5c5bd  callvirt instance int32 Microsoft.ReportingServices.Library.SessionReportItem::get_Timeout()
0x5c5c2  stloc.s  6
0x5c5c4  ldloc.s  6
0x5c5c6  brtrue.s loc_5C5D3
0x5c5c8  ldstr    aUnexpectedValu_1// "unexpected value for session timeout: 0"
0x5c5cd  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x5c5d2  throw
0x5c5d3  ldloc.s  5
0x5c5d5  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5c5da  ldstr    aTimeout// "@Timeout"
0x5c5df  ldc.i4.8
0x5c5e0  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5c5e5  ldloc.s  6
0x5c5e7  box      [mscorlib]System.Int32
0x5c5ec  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5c5f1  ldloc.s  5
0x5c5f3  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5c5f8  ldstr    aAutorefreshsec// "@AutoRefreshSeconds"
0x5c5fd  ldc.i4.8
0x5c5fe  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5c603  ldarg.0
0x5c604  callvirt instance int32 Microsoft.ReportingServices.Library.SessionReportItem::get_AutoRefreshSeconds()
0x5c609  box      [mscorlib]System.Int32
0x5c60e  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5c613  ldloc.s  5
0x5c615  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5c61a  ldstr    aOwnersid// "@OwnerSid"
0x5c61f  ldc.i4.s 0x15
0x5c621  ldc.i4.s 0x55
0x5c623  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x5c628  ldarg.0
0x5c629  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.SessionReportItem::get_UserContext()
0x5c62e  call     unsigned int8[] Microsoft.ReportingServices.Library.Global::NameToSid(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext user)
0x5c633  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5c638  ldloc.s  5
0x5c63a  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5c63f  ldstr    aOwnername// "@OwnerName"
0x5c644  ldc.i4.s 0xC
0x5c646  ldc.i4   0x104
0x5c64b  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x5c650  ldarg.0
0x5c651  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.SessionReportItem::get_UserContext()
0x5c656  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_UserName()
0x5c65b  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5c660  ldloc.s  5
0x5c662  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5c667  ldstr    aAuthtype// "@AuthType"
0x5c66c  ldc.i4.8
0x5c66d  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5c672  ldarg.0
0x5c673  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.SessionReportItem::get_UserContext()
0x5c678  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AuthenticationType()
0x5c67d  box      [mscorlib]System.Int32
0x5c682  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5c687  ldloc.s  5
0x5c689  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5c68e  ldstr    aHasinteractivi// "@HasInteractivity"
0x5c693  ldc.i4.2
0x5c694  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5c699  ldarg.0
0x5c69a  callvirt instance bool Microsoft.ReportingServices.Library.SessionReportItem::get_HasInteractivity()
0x5c69f  box      [mscorlib]System.Boolean
0x5c6a4  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5c6a9  ldloc.1
0x5c6aa  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ParameterInfoCollection Microsoft.ReportingServices.Library.ReportItem::get_EffectiveParams()
0x5c6af  brfalse.s loc_5C6CF
0x5c6b1  ldloc.s  5
0x5c6b3  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5c6b8  ldstr    aEffectiveparam// "@EffectiveParams"
0x5c6bd  ldc.i4.s 0xB
0x5c6bf  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5c6c4  ldloc.1
0x5c6c5  callvirt instance string Microsoft.ReportingServices.Library.ReportItem::get_EffectiveParamsXml()
0x5c6ca  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5c6cf  ldarg.0
0x5c6d0  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.EventInformation Microsoft.ReportingServices.Library.SessionReportItem::get_EventInfo()
0x5c6d5  brfalse.s loc_5C6F9
0x5c6d7  ldloc.s  5
0x5c6d9  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5c6de  ldstr    aShowhideinfo// "@ShowHideInfo"
0x5c6e3  ldc.i4.7
0x5c6e4  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5c6e9  ldarg.0
0x5c6ea  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.EventInformation Microsoft.ReportingServices.Library.SessionReportItem::get_EventInfo()
0x5c6ef  callvirt instance unsigned int8[] [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.EventInformation::Serialize()
0x5c6f4  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5c6f9  ldarg.0
0x5c6fa  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.RuntimeDataSourceInfoCollection Microsoft.ReportingServices.Library.SessionReportItem::get_Datasources()
0x5c6ff  brfalse.s loc_5C723
0x5c701  ldloc.s  5
0x5c703  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5c708  ldstr    aDatasourceinfo_2// "@DataSourceInfo"
0x5c70d  ldc.i4.7
0x5c70e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5c713  ldarg.0
0x5c714  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.RuntimeDataSourceInfoCollection Microsoft.ReportingServices.Library.SessionReportItem::get_Datasources()
0x5c719  callvirt instance unsigned int8[] [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.RuntimeDataSourceInfoCollection::Serialize()
0x5c71e  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5c723  ldarg.0
0x5c724  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.RuntimeDataSetInfoCollection Microsoft.ReportingServices.Library.SessionReportItem::get_DataSets()
0x5c729  brfalse.s loc_5C74D
0x5c72b  ldloc.s  5
0x5c72d  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5c732  ldstr    aDatasetinfo// "@DataSetInfo"
0x5c737  ldc.i4.7
0x5c738  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5c73d  ldarg.0
0x5c73e  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.RuntimeDataSetInfoCollection Microsoft.ReportingServices.Library.SessionReportItem::get_DataSets()
0x5c743  callvirt instance unsigned int8[] [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.RuntimeDataSetInfoCollection::Serialize()
0x5c748  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5c74d  ldarg.0
0x5c74e  callvirt instance class Microsoft.ReportingServices.Library.ReportItem Microsoft.ReportingServices.Library.SessionReportItem::get_Report()
0x5c753  callvirt instance class Microsoft.ReportingServices.Library.ReportSnapshot Microsoft.ReportingServices.Library.ReportItem::get_SnapshotData()
0x5c758  brfalse.s loc_5C7D4
0x5c75a  ldloc.s  5
0x5c75c  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5c761  ldstr    aSnapshotdataid// "@SnapshotDataID"
0x5c766  ldc.i4.s 0xE
0x5c768  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5c76d  ldarg.0
0x5c76e  callvirt instance class Microsoft.ReportingServices.Library.ReportItem Microsoft.ReportingServices.Library.SessionReportItem::get_Report()
0x5c773  callvirt instance class Microsoft.ReportingServices.Library.ReportSnapshot Microsoft.ReportingServices.Library.ReportItem::get_SnapshotData()
0x5c778  callvirt instance valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Library.SnapshotBase::get_SnapshotDataID()
0x5c77d  box      [mscorlib]System.Guid
0x5c782  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5c787  ldloc.s  5
0x5c789  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5c78e  ldstr    aIspermanentsna// "@IsPermanentSnapshot"
0x5c793  ldc.i4.2
0x5c794  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5c799  ldarg.0
0x5c79a  callvirt instance class Microsoft.ReportingServices.Library.ReportItem Microsoft.ReportingServices.Library.SessionReportItem::get_Report()
0x5c79f  callvirt instance class Microsoft.ReportingServices.Library.ReportSnapshot Microsoft.ReportingServices.Library.ReportItem::get_SnapshotData()
0x5c7a4  callvirt instance bool Microsoft.ReportingServices.Library.SnapshotBase::get_IsPermanentSnapshot()
0x5c7a9  box      [mscorlib]System.Boolean
0x5c7ae  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5c7b3  ldloc.s  5
0x5c7b5  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5c7ba  ldstr    aSnapshottimeou_0// "@SnapshotTimeoutSeconds"
0x5c7bf  ldc.i4.8
0x5c7c0  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5c7c5  ldc.i4   0x5A0
0x5c7ca  box      [mscorlib]System.Int32
0x5c7cf  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5c7d4  ldarg.0
0x5c7d5  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.SessionReportItem::get_SnapshotExpirationDateTime()
0x5c7da  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x5c7df  call     bool [mscorlib]System.DateTime::op_Inequality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x5c7e4  brfalse.s loc_5C808
0x5c7e6  ldloc.s  5
0x5c7e8  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5c7ed  ldstr    aSnapshotexpira// "@SnapshotExpirationDate"
0x5c7f2  ldc.i4.4
0x5c7f3  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5c7f8  ldarg.0
0x5c7f9  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.SessionReportItem::get_SnapshotExpirationDateTime()
0x5c7fe  box      [mscorlib]System.DateTime
0x5c803  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5c808  ldloc.s  5
0x5c80a  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5c80f  ldstr    aAwaitingfirste// "@AwaitingFirstExecution"
0x5c814  ldc.i4.2
0x5c815  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType)
0x5c81a  ldarg.0
0x5c81b  callvirt instance bool Microsoft.ReportingServices.Library.SessionReportItem::get_AwaitingFirstExecution()
0x5c820  box      [mscorlib]System.Boolean
0x5c825  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5c82a  ldarg.0
0x5c82b  callvirt instance class Microsoft.ReportingServices.Library.ReportItem Microsoft.ReportingServices.Library.SessionReportItem::get_Report()
0x5c830  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath Microsoft.ReportingServices.Library.ReportItem::get_ItemPath()
0x5c835  callvirt instance bool [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_IsEditSession()
0x5c83a  brfalse.s loc_5C866
0x5c83c  ldloc.s  5
0x5c83e  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x5c843  ldstr    aEditsessionid// "@EditSessionID"
0x5c848  ldc.i4.s 0x16
0x5c84a  ldc.i4.s 0x20
0x5c84c  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::Add(string, valuetype [System.Data]System.Data.SqlDbType, int32)
0x5c851  ldarg.0
0x5c852  callvirt instance class Microsoft.ReportingServices.Library.ReportItem Microsoft.ReportingServices.Library.SessionReportItem::get_Report()
0x5c857  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath Microsoft.ReportingServices.Library.ReportItem::get_ItemPath()
0x5c85c  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_EditSessionID()
0x5c861  callvirt instance void [System.Data]System.Data.Common.DbParameter::set_Value(object)
0x5c866  ldloc.s  5
0x5c868  callvirt instance int32 [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::ExecuteNonQuery()
0x5c86d  pop
0x5c86e  ldarg.0
0x5c86f  ldc.i4.1
0x5c870  callvirt instance void Microsoft.ReportingServices.Library.SessionReportItem::set_IsDBInstance(bool value)
0x5c875  leave.s  loc_5C883
0x5c877  ldloc.s  5
0x5c879  brfalse.s loc_5C882
0x5c87b  ldloc.s  5
  ... truncated ...
```
