# Microsoft.ReportingServices.Library.SessionReportItem::Load

- ea: `0x5e300`
- end: `0x5e420`
- name: `Microsoft.ReportingServices.Library.SessionReportItem::Load`
- size: `288`
- prototype: ``
- caller_count: `3`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x435c0`
- `0x518e0`
- `0x67dd0`

## callees

- `0x5bbc0`
- `0x5dfd0`
- `0x5e090`
- `0x5e0d0`
- `0x5e300`
- `0x5ea50`
- `0x5eab0`

## string_xrefs

- `0x5e313`: `LoadSnapshot: Item with session: {0}, reportPath: {1}, userName: {2} not found in the database`
- `0x5e383`: `Report path doesn't match - starting new session`

## pseudocode

```c

```

## disassembly

```asm
0x5e300  ldarg.0
0x5e301  ldarg.1
0x5e302  ldarg.s  4
0x5e304  callvirt instance class Microsoft.ReportingServices.Library.SessionReportItem Microsoft.ReportingServices.Library.DatabaseSessionStorage::GetSessionData(string sessionId, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext userContext)
0x5e309  stloc.0
0x5e30a  ldloc.0
0x5e30b  brtrue.s loc_5E337
0x5e30d  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_SessionTrace()
0x5e312  ldc.i4.3
0x5e313  ldstr    aLoadsnapshotIt// "LoadSnapshot: Item with session: {0}, r"...
0x5e318  ldc.i4.3
0x5e319  newarr   [mscorlib]System.Object
0x5e31e  dup
0x5e31f  ldc.i4.0
0x5e320  ldarg.1
0x5e321  stelem.ref
0x5e322  dup
0x5e323  ldc.i4.1
0x5e324  ldarg.2
0x5e325  stelem.ref
0x5e326  dup
0x5e327  ldc.i4.2
0x5e328  ldarg.s  4
0x5e32a  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_UserName()
0x5e32f  stelem.ref
0x5e330  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x5e335  ldnull
0x5e336  ret
0x5e337  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_SessionTrace()
0x5e33c  ldc.i4.4
0x5e33d  ldstr    aFoundSessionFo// "Found session for sessionid {0}"
0x5e342  ldc.i4.1
0x5e343  newarr   [mscorlib]System.Object
0x5e348  dup
0x5e349  ldc.i4.0
0x5e34a  ldarg.1
0x5e34b  stelem.ref
0x5e34c  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x5e351  ldarg.2
0x5e352  brfalse.s loc_5E38F
0x5e354  ldloc.0
0x5e355  callvirt instance class Microsoft.ReportingServices.Library.ReportItem Microsoft.ReportingServices.Library.SessionReportItem::get_Report()
0x5e35a  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath Microsoft.ReportingServices.Library.ReportItem::get_ItemPath()
0x5e35f  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_FullEditSessionIdentifier()
0x5e364  ldarg.2
0x5e365  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_FullEditSessionIdentifier()
0x5e36a  call     int32 [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.Localization::CatalogCultureCompare(string, string)
0x5e36f  brfalse.s loc_5E38F
0x5e371  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_SessionTrace()
0x5e376  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x5e37b  brfalse.s loc_5E38D
0x5e37d  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_SessionTrace()
0x5e382  ldc.i4.4
0x5e383  ldstr    aReportPathDoes// "Report path doesn't match - starting ne"...
0x5e388  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x5e38d  ldnull
0x5e38e  ret
0x5e38f  ldarg.2
0x5e390  brfalse.s loc_5E3CD
0x5e392  ldloc.0
0x5e393  callvirt instance class Microsoft.ReportingServices.Library.ReportItem Microsoft.ReportingServices.Library.SessionReportItem::get_Report()
0x5e398  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Library.ReportItem::get_HistoryDate()
0x5e39d  call     string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::ToSnapshotDateFormat(valuetype [mscorlib]System.DateTime)
0x5e3a2  ldarg.3
0x5e3a3  call     string [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::ToSnapshotDateFormat(valuetype [mscorlib]System.DateTime)
0x5e3a8  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x5e3ad  brfalse.s loc_5E3CD
0x5e3af  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_SessionTrace()
0x5e3b4  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x5e3b9  brfalse.s loc_5E3CB
0x5e3bb  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_SessionTrace()
0x5e3c0  ldc.i4.4
0x5e3c1  ldstr    aReportHistoryI// "Report history id doesn't match - start"...
0x5e3c6  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x5e3cb  ldnull
0x5e3cc  ret
0x5e3cd  ldloc.0
0x5e3ce  callvirt instance class Microsoft.ReportingServices.Library.ReportItem Microsoft.ReportingServices.Library.SessionReportItem::get_Report()
0x5e3d3  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ParameterInfoCollection Microsoft.ReportingServices.Library.ReportItem::get_EffectiveParams()
0x5e3d8  ldarg.s  5
0x5e3da  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ParameterInfoCollection::SameReportParameters(string)
0x5e3df  brtrue.s loc_5E3FF
0x5e3e1  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_SessionTrace()
0x5e3e6  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x5e3eb  brfalse.s loc_5E3FD
0x5e3ed  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_SessionTrace()
0x5e3f2  ldc.i4.4
0x5e3f3  ldstr    aParameterDonTM// "Parameter don't match - starting new se"...
0x5e3f8  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x5e3fd  ldnull
0x5e3fe  ret
0x5e3ff  ldloc.0
0x5e400  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.RuntimeDataSourceInfoCollection Microsoft.ReportingServices.Library.SessionReportItem::get_Datasources()
0x5e405  brfalse.s loc_5E41E
0x5e407  ldloc.0
0x5e408  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.RuntimeDataSourceInfoCollection Microsoft.ReportingServices.Library.SessionReportItem::get_Datasources()
0x5e40d  ldarg.s  7
0x5e40f  ldc.i4.1
0x5e410  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IDataProtection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.DataProtection::get_Instance()
0x5e415  callvirt instance bool [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.RuntimeDataSourceInfoCollection::CredentialsAreSame(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.DatasourceCredentialsCollection, bool, class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IDataProtection)
0x5e41a  brtrue.s loc_5E41E
0x5e41c  ldnull
0x5e41d  ret
0x5e41e  ldloc.0
0x5e41f  ret
```
