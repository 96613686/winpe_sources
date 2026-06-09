# Microsoft.SharePoint.WebControls.SPClientSideAppLoader::Render

- ea: `0x8354b0`
- end: `0x835788`
- name: `Microsoft.SharePoint.WebControls.SPClientSideAppLoader::Render`
- size: `728`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x3192a0`
- `0x42f150`
- `0x42f160`
- `0x42f190`
- `0x42f1b0`
- `0x4379d0`
- `0x439630`
- `0x43d490`
- `0x6785e0`
- `0x6c9890`
- `0x7be4d0`
- `0x7be4f0`
- `0x7be540`
- `0x7beb40`
- `0x835470`
- `0x835490`
- `0x8354b0`
- `0x8ecdb0`
- `0x93dae0`
- `0x957470`

## string_xrefs

- `0x835693`: `Use HtmlTextWriter to render.`
- `0x8354b7`: `Render SPClientSideAppLoader`
- `0x8354f5`: `SPClientSideAppLoader.Render`
- `0x835536`: `[SPClientSideAppLoader.Render] AppId parameter couldn't be parsed. Input: '|0'`
- `0x835570`: `[SPClientSideAppLoader.Render] AppId is not defined`
- `0x835620`: `[SPClientSideAppLoader.Render] ComponentIds parameter couldn't be parsed. Input: '|0'`
- `0x83563e`: `ComponentIds is not a comma-separated list of Guids`
- `0x835643`: `ComponentIds`
- `0x835650`: `ClientSideAppLoaderControl`
- `0x83565e`: `ConfiguredAppId`
- `0x835738`: `ConfiguredAppId`
- `0x835762`: `ConfiguredAppId`
- `0x835720`: `ComponentErrorType`

## pseudocode

```c

```

## disassembly

```asm
0x8354b0  ldarg.0
0x8354b1  ldarg.1
0x8354b2  call     instance void [System.Web]System.Web.UI.Control::Render(class [System.Web]System.Web.UI.HtmlTextWriter)
0x8354b7  ldstr    aRenderSpclient// "Render SPClientSideAppLoader"
0x8354bc  ldc.i4   0x13541A2
0x8354c1  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x8354c6  ldc.i4   0x13541A3
0x8354cb  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x8354d0  ldc.i4   0x13541C0
0x8354d5  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x8354da  ldc.i4.1
0x8354db  ldnull
0x8354dc  newobj   instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitor::.ctor(string scenarioName, unsigned int32 startTag, unsigned int32 successTag, unsigned int32 unexpectedFailureTag, [opt] valuetype Microsoft.SharePoint.Administration.SPLogType logType, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x8354e1  stloc.0
0x8354e2  ldnull
0x8354e3  stloc.1
0x8354e4  ldc.i4   0xBE4
0x8354e9  call     bool Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId featureId)
0x8354ee  brfalse.s loc_835502
0x8354f0  ldsfld   string Microsoft.SharePoint.WebControls.SPClientSideAppLoader::ClientSidePageGeneratorClassName
0x8354f5  ldstr    aSpclientsideap// "SPClientSideAppLoader.Render"
0x8354fa  call     T0x2B0003A2
0x8354ff  stloc.1
0x835500  br.s     loc_835508
0x835502  newobj   instance void Microsoft.SharePoint.ClientSideComponent.ClientSidePageGenerator::.ctor()
0x835507  stloc.1
0x835508  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x83550d  stloc.2
0x83550e  ldarg.0
0x83550f  call     instance string Microsoft.SharePoint.WebControls.SPClientSideAppLoader::get_AppId()
0x835514  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x835519  brtrue.s loc_835564
0x83551b  ldarg.0
0x83551c  call     instance string Microsoft.SharePoint.WebControls.SPClientSideAppLoader::get_AppId()
0x835521  ldloca.s 2
0x835523  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x835528  brtrue.s loc_835599
0x83552a  ldc.i4   0x1542101
0x83552f  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x835534  ldc.i4.s 0xA
0x835536  ldstr    aSpclientsideap_0// "[SPClientSideAppLoader.Render] AppId pa"...
0x83553b  ldc.i4.1
0x83553c  newarr   [mscorlib]System.Object
0x835541  stloc.s  0xB
0x835543  ldloc.s  0xB
0x835545  ldc.i4.0
0x835546  ldarg.0
0x835547  call     instance string Microsoft.SharePoint.WebControls.SPClientSideAppLoader::get_AppId()
0x83554c  stelem.ref
0x83554d  ldloc.s  0xB
0x83554f  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x835554  ldstr    aAppidIsNotAGui// "AppId is not a Guid"
0x835559  ldstr    aAppid_1// "AppId"
0x83555e  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x835563  throw
0x835564  ldc.i4   0x1542102
0x835569  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x83556e  ldc.i4.s 0xA
0x835570  ldstr    aSpclientsideap_1// "[SPClientSideAppLoader.Render] AppId is"...
0x835575  ldc.i4.1
0x835576  newarr   [mscorlib]System.Object
0x83557b  stloc.s  0xC
0x83557d  ldloc.s  0xC
0x83557f  ldc.i4.0
0x835580  ldarg.0
0x835581  call     instance string Microsoft.SharePoint.WebControls.SPClientSideAppLoader::get_AppId()
0x835586  stelem.ref
0x835587  ldloc.s  0xC
0x835589  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x83558e  ldstr    aAppid_1// "AppId"
0x835593  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x835598  throw
0x835599  ldnull
0x83559a  stloc.3
0x83559b  ldarg.0
0x83559c  call     instance string Microsoft.SharePoint.WebControls.SPClientSideAppLoader::get_ComponentIds()
0x8355a1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x8355a6  brtrue   loc_835650
0x8355ab  ldarg.0
0x8355ac  call     instance string Microsoft.SharePoint.WebControls.SPClientSideAppLoader::get_ComponentIds()
0x8355b1  ldc.i4.1
0x8355b2  newarr   [mscorlib]System.Char
0x8355b7  stloc.s  0xD
0x8355b9  ldloc.s  0xD
0x8355bb  ldc.i4.0
0x8355bc  ldc.i4.s 0x2C
0x8355be  stelem.i2
0x8355bf  ldloc.s  0xD
0x8355c1  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x8355c6  ldsfld   class [mscorlib]System.Func`2<string, string> Microsoft.SharePoint.WebControls.SPClientSideAppLoader::CS$<>9__CachedAnonymousMethodDelegate5
0x8355cb  brtrue.s loc_8355DE
0x8355cd  ldnull
0x8355ce  ldftn    string Microsoft.SharePoint.WebControls.SPClientSideAppLoader::<Render>b__3(string id)
0x8355d4  newobj   instance void class [mscorlib]System.Func`2<string, string>::.ctor(object, native int)
0x8355d9  stsfld   class [mscorlib]System.Func`2<string, string> Microsoft.SharePoint.WebControls.SPClientSideAppLoader::CS$<>9__CachedAnonymousMethodDelegate5
0x8355de  ldsfld   class [mscorlib]System.Func`2<string, string> Microsoft.SharePoint.WebControls.SPClientSideAppLoader::CS$<>9__CachedAnonymousMethodDelegate5
0x8355e3  call     T0x2B000016
0x8355e8  ldsfld   class [mscorlib]System.Func`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.WebControls.SPClientSideAppLoader::CS$<>9__CachedAnonymousMethodDelegate6
0x8355ed  brtrue.s loc_835600
0x8355ef  ldnull
0x8355f0  ldftn    valuetype [mscorlib]System.Guid Microsoft.SharePoint.WebControls.SPClientSideAppLoader::<Render>b__4(string id)
0x8355f6  newobj   instance void class [mscorlib]System.Func`2<string, valuetype [mscorlib]System.Guid>::.ctor(object, native int)
0x8355fb  stsfld   class [mscorlib]System.Func`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.WebControls.SPClientSideAppLoader::CS$<>9__CachedAnonymousMethodDelegate6
0x835600  ldsfld   class [mscorlib]System.Func`2<string, valuetype [mscorlib]System.Guid> Microsoft.SharePoint.WebControls.SPClientSideAppLoader::CS$<>9__CachedAnonymousMethodDelegate6
0x835605  call     T0x2B00014D
0x83560a  call     T0x2B0000E5
0x83560f  stloc.3
0x835610  leave.s  loc_835650
0x835612  stloc.s  4
0x835614  ldc.i4   0x1542103
0x835619  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_General()
0x83561e  ldc.i4.s 0xA
0x835620  ldstr    aSpclientsideap_2// "[SPClientSideAppLoader.Render] Componen"...
0x835625  ldc.i4.1
0x835626  newarr   [mscorlib]System.Object
0x83562b  stloc.s  0xE
0x83562d  ldloc.s  0xE
0x83562f  ldc.i4.0
0x835630  ldarg.0
0x835631  call     instance string Microsoft.SharePoint.WebControls.SPClientSideAppLoader::get_ComponentIds()
0x835636  stelem.ref
0x835637  ldloc.s  0xE
0x835639  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x83563e  ldstr    aComponentidsIs_1// "ComponentIds is not a comma-separated l"...
0x835643  ldstr    aComponentids_1// "ComponentIds"
0x835648  ldloc.s  4
0x83564a  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string, class [mscorlib]System.Exception)
0x83564f  throw
0x835650  ldstr    aClientsideappl_13// "ClientSideAppLoaderControl"
0x835655  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x83565a  stloc.s  5
0x83565c  ldloc.s  5
0x83565e  ldstr    aConfiguredappi// "ConfiguredAppId"
0x835663  ldarg.0
0x835664  call     instance string Microsoft.SharePoint.WebControls.SPClientSideAppLoader::get_AppId()
0x835669  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x83566e  ldloc.s  5
0x835670  call     void Microsoft.SharePoint.Administration.SPUserEngagement::WriteLog(string engagementName, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x835675  ldloc.1
0x835676  ldloc.2
0x835677  ldloc.3
0x835678  ldarg.0
0x835679  callvirt instance class [System.Web]System.Web.HttpContext [System.Web]System.Web.UI.Control::get_Context()
0x83567e  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x835683  ldnull
0x835684  callvirt instance void Microsoft.SharePoint.ClientSideComponent.IClientSidePageGenerator::Initialize([opt] valuetype [mscorlib]System.Guid appComponentId, [opt] class [mscorlib]System.Collections.Generic.IEnumerable`1<valuetype [mscorlib]System.Guid> componentIds, [opt] class [System.Web]System.Web.HttpResponse response, [opt] class Microsoft.SharePoint.ClientSideComponent.IClientSideDevCookie devCookie)
0x835689  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.WebControls.ClientSidePageBase::RenderingUsingWriterKillSwitch
0x83568e  ldstr    a03162017// "03/16/2017"
0x835693  ldstr    aUseHtmltextwri// "Use HtmlTextWriter to render."
0x835698  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x83569d  brtrue.s loc_8356C2
0x83569f  ldarg.0
0x8356a0  callvirt instance class [System.Web]System.Web.HttpContext [System.Web]System.Web.UI.Control::get_Context()
0x8356a5  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x8356aa  call     bool Microsoft.SharePoint.WebControls.ClientSidePageBase::IsJsonRequest(class [System.Web]System.Web.HttpRequest request)
0x8356af  brfalse.s loc_8356B9
0x8356b1  ldloc.1
0x8356b2  callvirt instance void Microsoft.SharePoint.ClientSideComponent.IClientSidePageGenerator::RenderJson()
0x8356b7  br.s     loc_8356CE
0x8356b9  ldloc.1
0x8356ba  ldarg.1
0x8356bb  callvirt instance void Microsoft.SharePoint.ClientSideComponent.IClientSidePageGenerator::Render(class [System.Web]System.Web.UI.HtmlTextWriter writer)
0x8356c0  br.s     loc_8356CE
0x8356c2  ldarg.1
0x8356c3  ldloc.1
0x8356c4  callvirt instance string Microsoft.SharePoint.ClientSideComponent.IClientSidePageGenerator::GetHtmlDocument()
0x8356c9  callvirt instance void [mscorlib]System.IO.TextWriter::Write(string)
0x8356ce  ldloc.0
0x8356cf  ldnull
0x8356d0  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::Success([opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x8356d5  leave    loc_83577B
0x8356da  stloc.s  6
0x8356dc  ldc.i4.0
0x8356dd  stloc.s  7
0x8356df  ldloc.s  6
0x8356e1  isinst   Microsoft.SharePoint.ClientSideComponent.ClientSideComponentException
0x8356e6  stloc.s  8
0x8356e8  ldloc.s  8
0x8356ea  brfalse.s loc_835752
0x8356ec  ldloc.s  8
0x8356ee  callvirt instance valuetype ErrorType Microsoft.SharePoint.ClientSideComponent.ClientSideComponentException::get_Error()
0x8356f3  ldc.i4.3
0x8356f4  beq.s    loc_83570A
0x8356f6  ldloc.s  8
0x8356f8  callvirt instance valuetype ErrorType Microsoft.SharePoint.ClientSideComponent.ClientSideComponentException::get_Error()
0x8356fd  ldc.i4.4
0x8356fe  beq.s    loc_83570A
0x835700  ldloc.s  8
0x835702  callvirt instance valuetype ErrorType Microsoft.SharePoint.ClientSideComponent.ClientSideComponentException::get_Error()
0x835707  ldc.i4.5
0x835708  bne.un.s loc_835752
0x83570a  ldloc.0
0x83570b  ldc.i4   0x13541C1
0x835710  call     unsigned int32 Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32 iTag)
0x835715  ldloc.s  6
0x835717  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x83571c  stloc.s  9
0x83571e  ldloc.s  9
0x835720  ldstr    aComponenterror// "ComponentErrorType"
0x835725  ldloc.s  8
0x835727  callvirt instance valuetype ErrorType Microsoft.SharePoint.ClientSideComponent.ClientSideComponentException::get_Error()
0x83572c  box      ErrorType
0x835731  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x835736  ldloc.s  9
0x835738  ldstr    aConfiguredappi// "ConfiguredAppId"
0x83573d  ldarg.0
0x83573e  call     instance string Microsoft.SharePoint.WebControls.SPClientSideAppLoader::get_AppId()
0x835743  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x835748  ldloc.s  9
0x83574a  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::ExpectedFailure(unsigned int32 tag, class [mscorlib]System.Exception ex, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x83574f  ldc.i4.1
0x835750  stloc.s  7
0x835752  ldloc.s  7
0x835754  brtrue.s loc_835779
0x835756  ldloc.0
0x835757  ldloc.s  6
0x835759  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::.ctor()
0x83575e  stloc.s  0xA
0x835760  ldloc.s  0xA
0x835762  ldstr    aConfiguredappi// "ConfiguredAppId"
0x835767  ldarg.0
0x835768  call     instance string Microsoft.SharePoint.WebControls.SPClientSideAppLoader::get_AppId()
0x83576d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, object>::Add(var<u1>, !!T0)
0x835772  ldloc.s  0xA
0x835774  callvirt instance void Microsoft.SharePoint.Utilities.SPReliabilityMonitorBase::UnexpectedFailure(class [mscorlib]System.Exception ex, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, object> properties)
0x835779  rethrow
0x83577b  leave.s  loc_835787
0x83577d  ldloc.0
0x83577e  brfalse.s loc_835786
0x835780  ldloc.0
0x835781  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x835786  endfinally
0x835787  ret
```
