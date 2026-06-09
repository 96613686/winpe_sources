# Microsoft.SharePoint.WebControls.ClientSidePageBase::ProcessRequest

- ea: `0x43d4e0`
- end: `0x43d91d`
- name: `Microsoft.SharePoint.WebControls.ClientSidePageBase::ProcessRequest`
- size: `1085`
- prototype: ``
- caller_count: `0`
- callee_count: `28`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callees

- `0x1871a0`
- `0x18f1a0`
- `0x1903b0`
- `0x232050`
- `0x3192a0`
- `0x42f150`
- `0x42f160`
- `0x42f180`
- `0x42f190`
- `0x42f1b0`
- `0x4379d0`
- `0x439630`
- `0x43d460`
- `0x43d490`
- `0x43d4e0`
- `0x43d920`
- `0x472c20`
- `0x4cd8e0`
- `0x678580`
- `0x6c9890`
- `0x7be4d0`
- `0x7be4f0`
- `0x7be550`
- `0x7beb50`
- `0x8ecdb0`
- `0x93dab0`
- `0x93e240`
- `0x957470`

## string_xrefs

- `0x43d51b`: `ClientSideBasePage::ProcessRequest : No ASPX controls allowed on client side page.`
- `0x43d525`: `The ASPX page should not contain child controls for client side application.`
- `0x43d534`: `RenderClientSideBasePage`
- `0x43d58d`: `RenderClientSideBasePage`
- `0x43d5b5`: `RenderClientSideBasePage`
- `0x43d577`: `Client side base page load`
- `0x43d5ec`: `RenderClientSideBasePageFromEmail`
- `0x43d624`: `Use RacerUtility instead of calling CompMgrRoot.`
- `0x43d630`: `Microsoft.SharePoint.ClientSideFramework.ClientSidePageGenerator`
- `0x43d64f`: `[ClientSidePageBase.ProcessRequest] Cannot instantiate ClientSidePageGenerator. Racer DLL not configured correctly.`
- `0x43d659`: `Cannot instantiate ClientSidePageGenerator.`
- `0x43d669`: `ClientSidePageBase.ProcessRequest`
- `0x43d67c`: `Initialize client side page`
- `0x43d6bb`: `Use HtmlTextWriter to render.`
- `0x43d6c7`: `Render Client side page`
- `0x43d735`: `Render Client side page`
- `0x43d7ab`: `ClientSideBasePage::PostProcessRequest : HttpException. Ex = {0}, HR = {1}`
- `0x43d84f`: `ClientSideBasePage::PostProcessRequest : ClientSideComponentException. Ex = {0}`
- `0x43d8c5`: `ClientSideBasePage::ProcessRequest : Exception occurred. Ex = `

## pseudocode

```c

```

## disassembly

```asm
0x43d4e0  ldarg.1
0x43d4e1  brfalse.s loc_43D501
0x43d4e3  ldarg.1
0x43d4e4  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x43d4e9  call     bool Microsoft.SharePoint.Utilities.SPUtility::IsSearchRequest(class [System.Web]System.Web.HttpRequest request)
0x43d4ee  brfalse.s loc_43D501
0x43d4f0  ldarg.1
0x43d4f1  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x43d4f6  ldstr    aHtmlHtml// "<html></html>"
0x43d4fb  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x43d500  ret
0x43d501  ldarg.0
0x43d502  callvirt instance class [System.Web]System.Web.UI.ControlCollection [System.Web]System.Web.UI.Control::get_Controls()
0x43d507  callvirt instance int32 [System.Web]System.Web.UI.ControlCollection::get_Count()
0x43d50c  ldc.i4.0
0x43d50d  ble.s    loc_43D530
0x43d50f  ldc.i4   0x11194CF
0x43d514  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x43d519  ldc.i4.s 0xA
0x43d51b  ldstr    aClientsidebase// "ClientSideBasePage::ProcessRequest : No"...
0x43d520  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x43d525  ldstr    aTheAspxPageSho// "The ASPX page should not contain child "...
0x43d52a  newobj   instance void [mscorlib]System.NotSupportedException::.ctor(string)
0x43d52f  throw
0x43d530  ldnull
0x43d531  stloc.0
0x43d532  ldc.i4.1
0x43d533  stloc.1
0x43d534  ldstr    aRenderclientsi// "RenderClientSideBasePage"
0x43d539  ldc.i4   0x11194D0
0x43d53e  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x43d543  ldc.i4   0x11194D1
0x43d548  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x43d54d  ldc.i4   0x11194D2
0x43d552  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x43d557  ldc.i4.s 0x27
0x43d559  box      Microsoft.SharePoint.GlobalEnums.SPComponentId
0x43d55e  ldc.i4.s 0x6F
0x43d560  box      Microsoft.SharePoint.GlobalEnums.SPFeatureId
0x43d565  ldc.i4   0x40C
0x43d56a  box      Microsoft.SharePoint.GlobalEnums.SPOperationId
0x43d56f  ldc.i4.0
0x43d570  ldnull
0x43d571  newobj   instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitor::.ctor(string scenarioName, unsigned int32 startTag, unsigned int32 successTag, unsigned int32 unexpectedFailureTag, class [mscorlib]System.Enum component, class [mscorlib]System.Enum feature, class [mscorlib]System.Enum operation, [opt] valuetype Microsoft.SharePoint.Administration.SPLogType logType, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x43d576  stloc.2
0x43d577  ldstr    aClientSideBase// "Client side base page load"
0x43d57c  ldc.i4.s 0x32
0x43d57e  ldc.i4.0
0x43d57f  newarr   Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x43d584  newobj   instance void Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string name, valuetype Microsoft.SharePoint.Administration.TraceSeverity traceLevel, class Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[] monitors)
0x43d589  stloc.3
0x43d58a  ldnull
0x43d58b  stloc.s  4
0x43d58d  ldstr    aRenderclientsi// "RenderClientSideBasePage"
0x43d592  ldnull
0x43d593  call     void Microsoft.SharePoint.Administration.SPUserEngagement::WriteLog(string engagementName, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x43d598  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::InternalWorkloadAppTitleKillSwitchId
0x43d59d  ldstr    a592017// "5/9/2017"
0x43d5a2  ldstr    aInternalworklo// "InternalWorkloadAppTitleKillSwitchId"
0x43d5a7  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x43d5ac  brtrue.s loc_43D5BF
0x43d5ae  call     bool Microsoft.SharePoint.SPGlobal::get_IsSPO()
0x43d5b3  brfalse.s loc_43D5BF
0x43d5b5  ldstr    aRenderclientsi// "RenderClientSideBasePage"
0x43d5ba  call     void Microsoft.SharePoint.Utilities.SPUtility::SetRequestUsageSharePointWorkloadAppTitle(string appTitle)
0x43d5bf  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.WebControls.ClientSidePageBase::UserEngagementFromEmailKillSwitch
0x43d5c4  ldstr    a3132017// "3/13/2017"
0x43d5c9  ldstr    aSoxRichsharing// "SOX_RichSharing_UserEngagementFromEmail"
0x43d5ce  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x43d5d3  brtrue.s loc_43D5F7
0x43d5d5  ldarg.1
0x43d5d6  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x43d5db  ldstr    aFrom// "from"
0x43d5e0  call     T0x2B0003A1
0x43d5e5  stloc.s  5
0x43d5e7  ldloc.s  5
0x43d5e9  ldc.i4.1
0x43d5ea  bne.un.s loc_43D5F7
0x43d5ec  ldstr    aRenderclientsi_0// "RenderClientSideBasePageFromEmail"
0x43d5f1  ldnull
0x43d5f2  call     void Microsoft.SharePoint.Administration.SPUserEngagement::WriteLog(string engagementName, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x43d5f7  call     class Microsoft.SharePoint.SPContext Microsoft.SharePoint.SPContext::get_Current()
0x43d5fc  brtrue.s loc_43D609
0x43d5fe  ldstr    aCurrentSpconte// "Current SPContext is not set."
0x43d603  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x43d608  throw
0x43d609  call     class Microsoft.SharePoint.SPContext Microsoft.SharePoint.SPContext::get_Current()
0x43d60e  ldc.i4   0xBE4
0x43d613  call     bool Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsExpFeatureToggleEnabled(class Microsoft.SharePoint.SPContext spContext, valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId featureId)
0x43d618  brfalse.s loc_43D676
0x43d61a  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.WebControls.ClientSidePageBase::RacerUtilityKillSwitch
0x43d61f  ldstr    a5152017// "5/15/2017"
0x43d624  ldstr    aUseRacerutilit// "Use RacerUtility instead of calling Com"...
0x43d629  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x43d62e  brfalse.s loc_43D664
0x43d630  ldstr    aMicrosoftShare_86// "Microsoft.SharePoint.ClientSideFramewor"...
0x43d635  call     object [Microsoft.SharePoint.Client.ServerRuntime]Microsoft.SharePoint.Client.CompMgrRoot::CreateInstance(string)
0x43d63a  isinst   Microsoft.SharePoint.ClientSideComponent.IClientSidePageGenerator
0x43d63f  stloc.0
0x43d640  ldloc.0
0x43d641  brtrue.s loc_43D67C
0x43d643  ldc.i4   0x15638DF
0x43d648  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x43d64d  ldc.i4.s 0xA
0x43d64f  ldstr    aClientsidepage_1// "[ClientSidePageBase.ProcessRequest] Can"...
0x43d654  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x43d659  ldstr    aCannotInstanti// "Cannot instantiate ClientSidePageGenera"...
0x43d65e  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x43d663  throw
0x43d664  ldsfld   string Microsoft.SharePoint.WebControls.ClientSidePageBase::ClientSidePageGeneratorClassName
0x43d669  ldstr    aClientsidepage_2// "ClientSidePageBase.ProcessRequest"
0x43d66e  call     T0x2B0003A2
0x43d673  stloc.0
0x43d674  br.s     loc_43D67C
0x43d676  newobj   instance void Microsoft.SharePoint.ClientSideComponent.ClientSidePageGenerator::.ctor()
0x43d67b  stloc.0
0x43d67c  ldstr    aInitializeClie// "Initialize client side page"
0x43d681  ldc.i4.s 0x32
0x43d683  ldc.i4.0
0x43d684  newarr   Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x43d689  newobj   instance void Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string name, valuetype Microsoft.SharePoint.Administration.TraceSeverity traceLevel, class Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[] monitors)
0x43d68e  stloc.s  6
0x43d690  ldloc.0
0x43d691  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x43d696  ldnull
0x43d697  ldarg.1
0x43d698  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x43d69d  ldnull
0x43d69e  callvirt instance void Microsoft.SharePoint.ClientSideComponent.IClientSidePageGenerator::Initialize([opt] valuetype [mscorlib]System.Guid appComponentId, [opt] class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid> componentIds, [opt] class [System.Web]System.Web.HttpResponse response, [opt] class Microsoft.SharePoint.ClientSideComponent.IClientSideDevCookie devCookie)
0x43d6a3  leave.s  loc_43D6B1
0x43d6a5  ldloc.s  6
0x43d6a7  brfalse.s loc_43D6B0
0x43d6a9  ldloc.s  6
0x43d6ab  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x43d6b0  endfinally
0x43d6b1  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.WebControls.ClientSidePageBase::RenderingUsingWriterKillSwitch
0x43d6b6  ldstr    a03162017// "03/16/2017"
0x43d6bb  ldstr    aUseHtmltextwri// "Use HtmlTextWriter to render."
0x43d6c0  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x43d6c5  brtrue.s loc_43D72E
0x43d6c7  ldstr    aRenderClientSi// "Render Client side page"
0x43d6cc  ldc.i4.s 0x32
0x43d6ce  ldc.i4.0
0x43d6cf  newarr   Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x43d6d4  newobj   instance void Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string name, valuetype Microsoft.SharePoint.Administration.TraceSeverity traceLevel, class Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[] monitors)
0x43d6d9  stloc.s  7
0x43d6db  ldarg.1
0x43d6dc  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x43d6e1  call     bool Microsoft.SharePoint.WebControls.ClientSidePageBase::IsJsonRequest(class [System.Web]System.Web.HttpRequest request)
0x43d6e6  brfalse.s loc_43D6F2
0x43d6e8  ldloc.0
0x43d6e9  callvirt instance void Microsoft.SharePoint.ClientSideComponent.IClientSidePageGenerator::RenderJson()
0x43d6ee  ldc.i4.0
0x43d6ef  stloc.1
0x43d6f0  br.s     loc_43D720
0x43d6f2  ldarg.1
0x43d6f3  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x43d6f8  callvirt instance class [mscorlib]System.IO.Stream [System.Web]System.Web.HttpResponse::get_OutputStream()
0x43d6fd  newobj   instance void [mscorlib]System.IO.StreamWriter::.ctor(class [mscorlib]System.IO.Stream)
0x43d702  ldnull
0x43d703  newobj   instance void [System.Web]System.Web.UI.HtmlTextWriter::.ctor(class [mscorlib]System.IO.TextWriter, string)
0x43d708  stloc.s  8
0x43d70a  ldloc.0
0x43d70b  ldloc.s  8
0x43d70d  callvirt instance void Microsoft.SharePoint.ClientSideComponent.IClientSidePageGenerator::Render(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x43d712  leave.s  loc_43D720
0x43d714  ldloc.s  8
0x43d716  brfalse.s loc_43D71F
0x43d718  ldloc.s  8
0x43d71a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x43d71f  endfinally
0x43d720  leave.s  loc_43D778
0x43d722  ldloc.s  7
0x43d724  brfalse.s loc_43D72D
0x43d726  ldloc.s  7
0x43d728  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x43d72d  endfinally
0x43d72e  call     bool Microsoft.SharePoint.WebControls.ClientSidePageBase::get_PreloadEnabled()
0x43d733  brfalse.s loc_43D763
0x43d735  ldstr    aRenderClientSi// "Render Client side page"
0x43d73a  ldc.i4.s 0x32
0x43d73c  ldc.i4.0
0x43d73d  newarr   Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x43d742  newobj   instance void Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string name, valuetype Microsoft.SharePoint.Administration.TraceSeverity traceLevel, class Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[] monitors)
0x43d747  stloc.s  9
0x43d749  ldloc.0
0x43d74a  ldarg.1
0x43d74b  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x43d750  callvirt instance void Microsoft.SharePoint.ClientSideComponent.IClientSidePageGenerator::Render(class [System.Web]System.Web.HttpResponse response)
0x43d755  leave.s  loc_43D778
0x43d757  ldloc.s  9
0x43d759  brfalse.s loc_43D762
0x43d75b  ldloc.s  9
0x43d75d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x43d762  endfinally
0x43d763  ldloc.0
0x43d764  callvirt instance string Microsoft.SharePoint.ClientSideComponent.IClientSidePageGenerator::GetHtmlDocument()
0x43d769  stloc.s  4
0x43d76b  ldarg.1
0x43d76c  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x43d771  ldloc.s  4
0x43d773  callvirt instance void [System.Web]System.Web.HttpResponse::Write(string)
0x43d778  ldloc.2
0x43d779  ldnull
0x43d77a  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::Success([opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x43d77f  leave    loc_43D8F4
0x43d784  stloc.s  0xA
0x43d786  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.WebControls.ClientSidePageBase::ClosedConnectionKillSwitch
0x43d78b  ldstr    a9182017// "9/18/2017"
0x43d790  ldstr    aRefiningFailur// "refining failure handling"
0x43d795  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x43d79a  brtrue   loc_43D824
0x43d79f  ldc.i4   0x17D18E1
0x43d7a4  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x43d7a9  ldloc.s  0xA
0x43d7ab  ldstr    aClientsidebase_0// "ClientSideBasePage::PostProcessRequest "...
0x43d7b0  ldc.i4.2
0x43d7b1  newarr   [mscorlib]System.Object
0x43d7b6  stloc.s  0xD
0x43d7b8  ldloc.s  0xD
0x43d7ba  ldc.i4.0
0x43d7bb  ldloc.s  0xA
0x43d7bd  callvirt instance string [mscorlib]System.Exception::get_Message()
0x43d7c2  stelem.ref
0x43d7c3  ldloc.s  0xD
0x43d7c5  ldc.i4.1
0x43d7c6  ldloc.s  0xA
0x43d7c8  callvirt instance int32 [mscorlib]System.Exception::get_HResult()
0x43d7cd  box      [mscorlib]System.UInt32
0x43d7d2  stelem.ref
0x43d7d3  ldloc.s  0xD
0x43d7d5  call     void Microsoft.SharePoint.Diagnostics.ULS::SendExceptionTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, class [mscorlib]System.Exception ex, string output, object[] data)
0x43d7da  ldloc.s  0xA
0x43d7dc  callvirt instance int32 [mscorlib]System.Exception::get_HResult()
0x43d7e1  ldc.i4   0x80070057
0x43d7e6  bne.un.s loc_43D822
0x43d7e8  ldloc.2
0x43d7e9  ldc.i4   0x17D18E2
0x43d7ee  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x43d7f3  ldloc.s  0xA
0x43d7f5  ldnull
0x43d7f6  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::ExpectedFailure(unsigned int32 tag, class [mscorlib]System.Exception ex, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x43d7fb  ldc.i4   0x17C2344
0x43d800  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x43d805  ldc.i4.s 0x32
0x43d807  ldstr    aConnectionClos// "Connection closed by remote host"
0x43d80c  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x43d811  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x43d816  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x43d81b  callvirt instance void [System.Web]System.Web.HttpResponse::End()
0x43d820  br.s     loc_43D826
0x43d822  rethrow
0x43d824  rethrow
0x43d826  leave    loc_43D8F4
0x43d82b  stloc.s  0xB
0x43d82d  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.WebControls.ClientSidePageBase::ClosedConnectionKillSwitch
0x43d832  ldstr    a9182017// "9/18/2017"
0x43d837  ldstr    aRefiningFailur// "refining failure handling"
0x43d83c  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x43d841  brtrue.s loc_43D8A0
0x43d843  ldc.i4   0x17D18E3
0x43d848  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x43d84d  ldloc.s  0xB
0x43d84f  ldstr    aClientsidebase_1// "ClientSideBasePage::PostProcessRequest "...
0x43d854  ldc.i4.1
0x43d855  newarr   [mscorlib]System.Object
0x43d85a  stloc.s  0xE
0x43d85c  ldloc.s  0xE
0x43d85e  ldc.i4.0
0x43d85f  ldloc.s  0xB
0x43d861  callvirt instance string [mscorlib]System.Exception::get_Message()
0x43d866  stelem.ref
0x43d867  ldloc.s  0xE
0x43d869  call     void Microsoft.SharePoint.Diagnostics.ULS::SendExceptionTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, class [mscorlib]System.Exception ex, string output, object[] data)
0x43d86e  ldloc.s  0xB
0x43d870  callvirt instance valuetype ErrorType Microsoft.SharePoint.ClientSideComponent.ClientSideComponentException::get_Error()
0x43d875  ldc.i4.5
0x43d876  bne.un.s loc_43D89E
0x43d878  ldloc.2
0x43d879  ldc.i4   0x17D2000
0x43d87e  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x43d883  ldloc.s  0xB
0x43d885  ldnull
0x43d886  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::ExpectedFailure(unsigned int32 tag, class [mscorlib]System.Exception ex, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x43d88b  ldc.i4.0
0x43d88c  stloc.1
0x43d88d  ldloc.s  0xB
0x43d88f  callvirt instance string [mscorlib]System.Exception::get_Message()
0x43d894  ldnull
0x43d895  ldnull
0x43d896  ldarg.1
0x43d897  call     void Microsoft.SharePoint.Utilities.SPUtility::RedirectToErrorPage(string message, string linkText, string linkUrl, class [System.Web]System.Web.HttpContext context)
0x43d89c  br.s     loc_43D8A2
0x43d89e  rethrow
0x43d8a0  rethrow
0x43d8a2  leave.s  loc_43D8F4
0x43d8a4  stloc.s  0xC
0x43d8a6  ldloc.2
0x43d8a7  ldc.i4   0x11194D4
0x43d8ac  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
  ... truncated ...
```
