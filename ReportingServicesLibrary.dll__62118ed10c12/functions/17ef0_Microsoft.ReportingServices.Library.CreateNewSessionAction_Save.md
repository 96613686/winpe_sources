# Microsoft.ReportingServices.Library.CreateNewSessionAction::Save

- ea: `0x17ef0`
- end: `0x180c9`
- name: `Microsoft.ReportingServices.Library.CreateNewSessionAction::Save`
- size: `473`
- prototype: ``
- caller_count: `3`
- callee_count: `22`
- tags: `service_task, broker_com_uri`

## callers

- `0x3e140`
- `0x6c280`
- `0x8c360`

## callees

- `0xf2d0`
- `0x17ef0`
- `0x18390`
- `0x183c0`
- `0x1e290`
- `0x1e990`
- `0x5bb20`
- `0x5dfc0`
- `0x5dfd0`
- `0x5e080`
- `0x5e0a0`
- `0x5e830`
- `0x5ea50`
- `0x5eb40`
- `0x5eb60`
- `0x5eba0`
- `0x5ebc0`
- `0x5ebe0`
- `0x5ec30`
- `0x5ec40`
- `0x5ec60`
- `0x6f450`

## string_xrefs

- `0x17ef0`: `CreateNewSessionAction.Save`
- `0x17f24`: `CreateNewSessionAction.Save - ExecuteStep`
- `0x1806d`: `CreateNewSessionAction.Save - AddNew`

## pseudocode

```c

```

## disassembly

```asm
0x17ef0  ldstr    aCreatenewsessi// "CreateNewSessionAction.Save"
0x17ef5  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x17efa  stloc.0
0x17efb  ldarg.0
0x17efc  ldfld    class Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Library.CreateNewSessionAction::m_service
0x17f01  callvirt instance class Microsoft.ReportingServices.Library.RSServiceHelper Microsoft.ReportingServices.Library.RSService::get_ServiceHelper()
0x17f06  ldarg.0
0x17f07  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext Microsoft.ReportingServices.Library.CreateNewSessionAction::m_reportContext
0x17f0c  callvirt instance var<u1> class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_ItemPath()
0x17f11  callvirt instance bool Microsoft.ReportingServices.Library.RSServiceHelper::SyncToRSCatalog(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath path)
0x17f16  pop
0x17f17  ldarg.0
0x17f18  ldfld    class Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Library.CreateNewSessionAction::m_service
0x17f1d  newobj   instance void Microsoft.ReportingServices.Library.GetDataForExecutionAction::.ctor(class Microsoft.ReportingServices.Library.RSService service)
0x17f22  stloc.s  9
0x17f24  ldstr    aCreatenewsessi_0// "CreateNewSessionAction.Save - ExecuteSt"...
0x17f29  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x17f2e  stloc.s  0xB
0x17f30  ldloc.s  9
0x17f32  ldarg.0
0x17f33  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext Microsoft.ReportingServices.Library.CreateNewSessionAction::m_reportContext
0x17f38  ldarg.0
0x17f39  ldfld    class Microsoft.ReportingServices.Library.ClientRequest Microsoft.ReportingServices.Library.CreateNewSessionAction::m_session
0x17f3e  ldloca.s 1
0x17f40  ldloca.s 3
0x17f42  ldloca.s 2
0x17f44  ldloca.s 4
0x17f46  ldloca.s 5
0x17f48  ldloca.s 6
0x17f4a  ldloca.s 7
0x17f4c  ldloca.s 8
0x17f4e  callvirt instance void Microsoft.ReportingServices.Library.GetDataForExecutionAction::ExecuteStep(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext reportContext, class Microsoft.ReportingServices.Library.ClientRequest session, [out] class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourcePromptCollection& prompts, [out] valuetype Microsoft.ReportingServices.Library.Soap.ExecutionSettingEnum& execSetting, [out] valuetype [mscorlib]System.DateTime& executionDateTime, [out] class Microsoft.ReportingServices.Library.ReportSnapshot& snapshotData, [out] int32& pageCount, [out] bool& hasDocMap, [out] class Microsoft.ReportingServices.Library.Soap2005.PageSettings& reportPageSettings, [out] valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.PaginationMode& paginationMode)
0x17f53  leave.s  loc_17F61
0x17f55  ldloc.s  0xB
0x17f57  brfalse.s loc_17F60
0x17f59  ldloc.s  0xB
0x17f5b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x17f60  endfinally
0x17f61  ldarg.0
0x17f62  ldfld    class Microsoft.ReportingServices.Library.ClientRequest Microsoft.ReportingServices.Library.CreateNewSessionAction::m_session
0x17f67  callvirt instance class Microsoft.ReportingServices.Library.SessionReportItem Microsoft.ReportingServices.Library.ClientRequest::get_SessionReport()
0x17f6c  ldloc.2
0x17f6d  callvirt instance void Microsoft.ReportingServices.Library.SessionReportItem::set_ExecutionDateTime(valuetype [mscorlib]System.DateTime value)
0x17f72  ldarg.0
0x17f73  ldfld    class Microsoft.ReportingServices.Library.ClientRequest Microsoft.ReportingServices.Library.CreateNewSessionAction::m_session
0x17f78  callvirt instance class Microsoft.ReportingServices.Library.SessionReportItem Microsoft.ReportingServices.Library.ClientRequest::get_SessionReport()
0x17f7d  call     int32 Microsoft.ReportingServices.Library.Global::get_SessionTimeoutSeconds()
0x17f82  callvirt instance void Microsoft.ReportingServices.Library.SessionReportItem::set_Timeout(int32 value)
0x17f87  ldarg.0
0x17f88  ldfld    class Microsoft.ReportingServices.Library.ClientRequest Microsoft.ReportingServices.Library.CreateNewSessionAction::m_session
0x17f8d  callvirt instance class Microsoft.ReportingServices.Library.SessionReportItem Microsoft.ReportingServices.Library.ClientRequest::get_SessionReport()
0x17f92  ldc.i4.0
0x17f93  callvirt instance void Microsoft.ReportingServices.Library.SessionReportItem::set_AutoRefreshSeconds(int32 value)
0x17f98  ldarg.0
0x17f99  ldfld    class Microsoft.ReportingServices.Library.ClientRequest Microsoft.ReportingServices.Library.CreateNewSessionAction::m_session
0x17f9e  callvirt instance class Microsoft.ReportingServices.Library.SessionReportItem Microsoft.ReportingServices.Library.ClientRequest::get_SessionReport()
0x17fa3  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x17fa8  stloc.s  0xC
0x17faa  ldloca.s 0xC
0x17fac  ldarg.0
0x17fad  ldfld    class Microsoft.ReportingServices.Library.ClientRequest Microsoft.ReportingServices.Library.CreateNewSessionAction::m_session
0x17fb2  callvirt instance class Microsoft.ReportingServices.Library.SessionReportItem Microsoft.ReportingServices.Library.ClientRequest::get_SessionReport()
0x17fb7  callvirt instance int32 Microsoft.ReportingServices.Library.SessionReportItem::get_Timeout()
0x17fbc  conv.r8
0x17fbd  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::AddSeconds(float64)
0x17fc2  callvirt instance void Microsoft.ReportingServices.Library.SessionReportItem::set_ExpirationDateTime(valuetype [mscorlib]System.DateTime value)
0x17fc7  ldarg.0
0x17fc8  ldfld    class Microsoft.ReportingServices.Library.ClientRequest Microsoft.ReportingServices.Library.CreateNewSessionAction::m_session
0x17fcd  callvirt instance class Microsoft.ReportingServices.Library.SessionReportItem Microsoft.ReportingServices.Library.ClientRequest::get_SessionReport()
0x17fd2  callvirt instance class Microsoft.ReportingServices.Library.ReportItem Microsoft.ReportingServices.Library.SessionReportItem::get_Report()
0x17fd7  ldloc.s  4
0x17fd9  callvirt instance void Microsoft.ReportingServices.Library.ReportItem::set_SnapshotData(class Microsoft.ReportingServices.Library.ReportSnapshot value)
0x17fde  ldarg.0
0x17fdf  ldfld    class Microsoft.ReportingServices.Library.ClientRequest Microsoft.ReportingServices.Library.CreateNewSessionAction::m_session
0x17fe4  callvirt instance class Microsoft.ReportingServices.Library.SessionReportItem Microsoft.ReportingServices.Library.ClientRequest::get_SessionReport()
0x17fe9  ldloc.s  5
0x17feb  callvirt instance void Microsoft.ReportingServices.Library.SessionReportItem::set_PageCount(int32 value)
0x17ff0  ldarg.0
0x17ff1  ldfld    class Microsoft.ReportingServices.Library.ClientRequest Microsoft.ReportingServices.Library.CreateNewSessionAction::m_session
0x17ff6  callvirt instance class Microsoft.ReportingServices.Library.SessionReportItem Microsoft.ReportingServices.Library.ClientRequest::get_SessionReport()
0x17ffb  ldloc.s  6
0x17ffd  callvirt instance void Microsoft.ReportingServices.Library.SessionReportItem::set_HasDocumentMap(bool value)
0x18002  ldarg.0
0x18003  ldfld    class Microsoft.ReportingServices.Library.ClientRequest Microsoft.ReportingServices.Library.CreateNewSessionAction::m_session
0x18008  callvirt instance class Microsoft.ReportingServices.Library.SessionReportItem Microsoft.ReportingServices.Library.ClientRequest::get_SessionReport()
0x1800d  ldloc.s  8
0x1800f  callvirt instance void Microsoft.ReportingServices.Library.SessionReportItem::set_PaginationMode(valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.PaginationMode value)
0x18014  ldarg.0
0x18015  ldfld    class Microsoft.ReportingServices.Library.ClientRequest Microsoft.ReportingServices.Library.CreateNewSessionAction::m_session
0x1801a  callvirt instance class Microsoft.ReportingServices.Library.SessionReportItem Microsoft.ReportingServices.Library.ClientRequest::get_SessionReport()
0x1801f  callvirt instance class Microsoft.ReportingServices.Library.ReportItem Microsoft.ReportingServices.Library.SessionReportItem::get_Report()
0x18024  ldarg.0
0x18025  ldfld    class Microsoft.ReportingServices.Library.ClientRequest Microsoft.ReportingServices.Library.CreateNewSessionAction::m_session
0x1802a  callvirt instance class Microsoft.ReportingServices.Library.SessionReportItem Microsoft.ReportingServices.Library.ClientRequest::get_SessionReport()
0x1802f  callvirt instance class Microsoft.ReportingServices.Library.ReportItem Microsoft.ReportingServices.Library.SessionReportItem::get_Report()
0x18034  callvirt instance class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ParameterInfoCollection Microsoft.ReportingServices.Library.ReportItem::get_EffectiveParams()
0x18039  callvirt instance void Microsoft.ReportingServices.Library.ReportItem::set_ParametersOnSnapshot(class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ParameterInfoCollection value)
0x1803e  ldarg.0
0x1803f  ldfld    class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContext Microsoft.ReportingServices.Library.CreateNewSessionAction::m_reportContext
0x18044  callvirt instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemContextBase`1<class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ExternalItemPath>::get_RSRequestParameters()
0x18049  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IRSRequestParameters::get_SnapshotParamValue()
0x1804e  ldc.i4.1
0x1804f  call     valuetype [mscorlib]System.DateTime [Microsoft.ReportingServices.Diagnostics]Microsoft.ReportingServices.Diagnostics.Globals::ParseSnapshotDateParameter(string, bool)
0x18054  stloc.s  0xA
0x18056  ldarg.0
0x18057  ldfld    class Microsoft.ReportingServices.Library.ClientRequest Microsoft.ReportingServices.Library.CreateNewSessionAction::m_session
0x1805c  callvirt instance class Microsoft.ReportingServices.Library.SessionReportItem Microsoft.ReportingServices.Library.ClientRequest::get_SessionReport()
0x18061  callvirt instance class Microsoft.ReportingServices.Library.ReportItem Microsoft.ReportingServices.Library.SessionReportItem::get_Report()
0x18066  ldloc.s  0xA
0x18068  callvirt instance void Microsoft.ReportingServices.Library.ReportItem::set_HistoryDate(valuetype [mscorlib]System.DateTime value)
0x1806d  ldstr    aCreatenewsessi_1// "CreateNewSessionAction.Save - AddNew"
0x18072  call     class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.MonitoredScope::New(string)
0x18077  stloc.s  0xB
0x18079  ldarg.0
0x1807a  ldfld    class Microsoft.ReportingServices.Library.ClientRequest Microsoft.ReportingServices.Library.CreateNewSessionAction::m_session
0x1807f  callvirt instance class Microsoft.ReportingServices.Library.SessionReportItem Microsoft.ReportingServices.Library.ClientRequest::get_SessionReport()
0x18084  callvirt instance void Microsoft.ReportingServices.Library.SessionReportItem::AddNew()
0x18089  leave.s  loc_18097
0x1808b  ldloc.s  0xB
0x1808d  brfalse.s loc_18096
0x1808f  ldloc.s  0xB
0x18091  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x18096  endfinally
0x18097  ldarg.0
0x18098  ldarg.0
0x18099  ldfld    class Microsoft.ReportingServices.Library.ClientRequest Microsoft.ReportingServices.Library.CreateNewSessionAction::m_session
0x1809e  ldloc.3
0x1809f  ldloc.1
0x180a0  ldloc.s  7
0x180a2  ldarg.0
0x180a3  ldfld    class Microsoft.ReportingServices.Library.RSService Microsoft.ReportingServices.Library.CreateNewSessionAction::m_service
0x180a8  call     class Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo3 Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo::NewExecutionInfo3(class Microsoft.ReportingServices.Library.ClientRequest session, valuetype Microsoft.ReportingServices.Library.Soap.ExecutionSettingEnum executionSettings, class [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.DataExtensions.DataSourcePromptCollection promptCollection, class Microsoft.ReportingServices.Library.Soap2005.PageSettings reportPageSettings, class Microsoft.ReportingServices.Library.RSService service)
0x180ad  stfld    class Microsoft.ReportingServices.Library.Soap2005.ExecutionInfo3 Microsoft.ReportingServices.Library.CreateNewSessionAction::m_result
0x180b2  leave.s  loc_180C8
0x180b4  pop
0x180b5  rethrow
0x180b7  ldnull
0x180b8  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(class [mscorlib]System.Exception, string)
0x180bd  throw
0x180be  ldloc.0
0x180bf  brfalse.s loc_180C7
0x180c1  ldloc.0
0x180c2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x180c7  endfinally
0x180c8  ret
```
