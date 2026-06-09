# Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::System.Web.IHttpModule.Init

- ea: `0x410dc0`
- end: `0x411224`
- name: `Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::System.Web.IHttpModule.Init`
- size: `1124`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x30fef0`
- `0x30ffe0`
- `0x410dc0`
- `0x41a5a0`
- `0x41a5c0`
- `0x41e240`
- `0x424b40`
- `0x472c20`
- `0x4a8a20`
- `0x7bbc60`
- `0x93dab0`
- `0x93dae0`
- `0x957490`
- `0x957d10`

## string_xrefs

- `0x410e21`: `/clientaccesspolicy.xml`
- `0x410e2d`: `/crossdomain.xml`
- `0x411037`: `Microsoft_FileServices`
- `0x411062`: `Microsoft_FileServices`
- `0x411088`: `Microsoft_FileServices`
- `0x4110ae`: `Microsoft_FileServices`
- `0x4110d4`: `Microsoft_FileServices`
- `0x4110fa`: `Microsoft_FileServices`
- `0x411120`: `Microsoft_FileServices`
- `0x411146`: `Microsoft_FileServices`
- `0x41116c`: `Microsoft_FileServices`
- `0x411192`: `Microsoft_FileServices`
- `0x4111b8`: `Microsoft_FileServices`
- `0x4110b8`: `Http.PostResolveRequestCacheHandler`

## pseudocode

```c

```

## disassembly

```asm
0x410dc0  ldarg.1
0x410dc1  isinst   Microsoft.SharePoint.ApplicationRuntime.SPHttpApplication
0x410dc6  brfalse  loc_411223
0x410dcb  ldsfld   bool Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::s_virtualPathProviderInitialized
0x410dd0  brtrue   loc_410F2B
0x410dd5  ldc.i4.0
0x410dd6  stloc.s  8
0x410dd8  ldsfld   object Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::s_virtualServerDataInitializedSyncObject
0x410ddd  dup
0x410dde  stloc.s  9
0x410de0  ldloca.s 8
0x410de2  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x410de7  ldsfld   bool Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::s_virtualPathProviderInitialized
0x410dec  brtrue   loc_410F08
0x410df1  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_OrdinalIgnoreCase()
0x410df6  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype ExclusionAttributes>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x410dfb  stloc.0
0x410dfc  ldloc.0
0x410dfd  ldstr    aAppThemes// "/app_themes"
0x410e02  ldc.i4.2
0x410e03  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype ExclusionAttributes>::set_Item(var<u1>, !!T0)
0x410e08  ldloc.0
0x410e09  ldstr    aAppBrowsers_0// "/app_browsers"
0x410e0e  ldc.i4.2
0x410e0f  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype ExclusionAttributes>::set_Item(var<u1>, !!T0)
0x410e14  ldloc.0
0x410e15  ldstr    aDefaultwsdlhel// "/defaultwsdlhelpgenerator.aspx"
0x410e1a  ldc.i4.4
0x410e1b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype ExclusionAttributes>::set_Item(var<u1>, !!T0)
0x410e20  ldloc.0
0x410e21  ldstr    aClientaccesspo// "/clientaccesspolicy.xml"
0x410e26  ldc.i4.4
0x410e27  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype ExclusionAttributes>::set_Item(var<u1>, !!T0)
0x410e2c  ldloc.0
0x410e2d  ldstr    aCrossdomainXml// "/crossdomain.xml"
0x410e32  ldc.i4.4
0x410e33  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype ExclusionAttributes>::set_Item(var<u1>, !!T0)
0x410e38  call     class [System.Web]System.Web.Hosting.VirtualPathProvider [System.Web]System.Web.Hosting.HostingEnvironment::get_VirtualPathProvider()
0x410e3d  stloc.1
0x410e3e  ldloc.1
0x410e3f  brfalse  loc_410EEE
0x410e44  ldloc.1
0x410e45  ldstr    asc_C7604A// "/"
0x410e4a  callvirt instance bool [System.Web]System.Web.Hosting.VirtualPathProvider::DirectoryExists(string)
0x410e4f  brfalse  loc_410EEE
0x410e54  ldloc.1
0x410e55  ldstr    asc_C7604A// "/"
0x410e5a  callvirt instance class [System.Web]System.Web.Hosting.VirtualDirectory [System.Web]System.Web.Hosting.VirtualPathProvider::GetDirectory(string)
0x410e5f  stloc.2
0x410e60  ldloc.2
0x410e61  brfalse  loc_410EEE
0x410e66  ldloc.2
0x410e67  callvirt instance class [mscorlib]System.Collections.IEnumerable [System.Web]System.Web.Hosting.VirtualDirectory::get_Children()
0x410e6c  stloc.3
0x410e6d  ldloc.3
0x410e6e  brfalse.s loc_410EEE
0x410e70  ldloc.3
0x410e71  callvirt instance class [mscorlib]System.Collections.IEnumerator [mscorlib]System.Collections.IEnumerable::GetEnumerator()
0x410e76  stloc.s  0xA
0x410e78  br.s     loc_410ECE
0x410e7a  ldloc.s  0xA
0x410e7c  callvirt instance object [mscorlib]System.Collections.IEnumerator::get_Current()
0x410e81  castclass [System.Web]System.Web.Hosting.VirtualFileBase
0x410e86  stloc.s  4
0x410e88  ldloc.s  4
0x410e8a  callvirt instance string [System.Web]System.Web.Hosting.VirtualFileBase::get_VirtualPath()
0x410e8f  stloc.s  5
0x410e91  ldloc.s  5
0x410e93  ldc.i4.1
0x410e94  newarr   [mscorlib]System.Char
0x410e99  stloc.s  0xB
0x410e9b  ldloc.s  0xB
0x410e9d  ldc.i4.0
0x410e9e  ldc.i4.s 0x2F
0x410ea0  stelem.i2
0x410ea1  ldloc.s  0xB
0x410ea3  callvirt instance string [mscorlib]System.String::TrimEnd(char[])
0x410ea8  stloc.s  5
0x410eaa  ldc.i4.0
0x410eab  stloc.s  6
0x410ead  ldloc.s  4
0x410eaf  callvirt instance bool [System.Web]System.Web.Hosting.VirtualFileBase::get_IsDirectory()
0x410eb4  brfalse.s loc_410EBE
0x410eb6  ldloc.s  6
0x410eb8  ldc.i4.2
0x410eb9  or
0x410eba  stloc.s  6
0x410ebc  br.s     loc_410EC4
0x410ebe  ldloc.s  6
0x410ec0  ldc.i4.4
0x410ec1  or
0x410ec2  stloc.s  6
0x410ec4  ldloc.0
0x410ec5  ldloc.s  5
0x410ec7  ldloc.s  6
0x410ec9  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype ExclusionAttributes>::set_Item(var<u1>, !!T0)
0x410ece  ldloc.s  0xA
0x410ed0  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x410ed5  brtrue.s loc_410E7A
0x410ed7  leave.s  loc_410EEE
0x410ed9  ldloc.s  0xA
0x410edb  isinst   [mscorlib]System.IDisposable
0x410ee0  stloc.s  0xC
0x410ee2  ldloc.s  0xC
0x410ee4  brfalse.s loc_410EED
0x410ee6  ldloc.s  0xC
0x410ee8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x410eed  endfinally
0x410eee  ldloc.0
0x410eef  stsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, valuetype ExclusionAttributes> Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::s_excludedFileList
0x410ef4  newobj   instance void Microsoft.SharePoint.ApplicationRuntime.SPVirtualPathProvider::.ctor()
0x410ef9  stloc.s  7
0x410efb  ldloc.s  7
0x410efd  call     void [System.Web]System.Web.Hosting.HostingEnvironment::RegisterVirtualPathProvider(class [System.Web]System.Web.Hosting.VirtualPathProvider)
0x410f02  ldc.i4.1
0x410f03  stsfld   bool Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::s_virtualPathProviderInitialized
0x410f08  call     class Microsoft.SharePoint.Administration.SPTemplateFileSystemWatcher Microsoft.SharePoint.Administration.SPTemplateFileSystemWatcher::get_Local()
0x410f0d  callvirt instance void Microsoft.SharePoint.Administration.SPTemplateFileSystemWatcher::Initialize()
0x410f12  call     class Microsoft.SharePoint.Utilities.SPPerformanceCounterAgent Microsoft.SharePoint.Utilities.SPPerformanceCounterAgent::get_Current()
0x410f17  pop
0x410f18  call     void Microsoft.SharePoint.SPAudit::Initialize()
0x410f1d  leave.s  loc_410F2B
0x410f1f  ldloc.s  8
0x410f21  brfalse.s loc_410F2A
0x410f23  ldloc.s  9
0x410f25  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x410f2a  endfinally
0x410f2b  call     bool Microsoft.SharePoint.SPGlobal::get_IsSPO()
0x410f30  brtrue   loc_411020
0x410f35  ldc.i4   0x709021
0x410f3a  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Health()
0x410f3f  ldc.i4.s 0x64
0x410f41  ldstr    aAzureTelemetry// "[Azure Telemetry] On-prem - NOT enabled"...
0x410f46  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x410f4b  ldarg.1
0x410f4c  ldarg.0
0x410f4d  ldftn    instance void Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::BeginRequestHandler(object oSender, class [mscorlib]System.EventArgs ea)
0x410f53  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x410f58  call     class [mscorlib]System.EventHandler Microsoft.SharePoint.ApplicationRuntime.RequestInstrumentationScopeManager::WrapBeginRequestEventHandler(class [mscorlib]System.EventHandler originalBeginRequestHandler)
0x410f5d  callvirt instance void [System.Web]System.Web.HttpApplication::add_BeginRequest(class [mscorlib]System.EventHandler)
0x410f62  ldarg.1
0x410f63  ldarg.0
0x410f64  ldftn    instance void Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::PostAuthenticateRequestHandler(object oSender, class [mscorlib]System.EventArgs ea)
0x410f6a  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x410f6f  callvirt instance void [System.Web]System.Web.HttpApplication::add_PostAuthenticateRequest(class [mscorlib]System.EventHandler)
0x410f74  ldarg.1
0x410f75  ldarg.0
0x410f76  ldftn    instance void Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::PostAuthorizeRequestHandler(object oSender, class [mscorlib]System.EventArgs ea)
0x410f7c  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x410f81  callvirt instance void [System.Web]System.Web.HttpApplication::add_PostAuthorizeRequest(class [mscorlib]System.EventHandler)
0x410f86  ldarg.1
0x410f87  ldarg.0
0x410f88  ldftn    instance void Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::PostResolveRequestCacheHandler(object oSender, class [mscorlib]System.EventArgs ea)
0x410f8e  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x410f93  callvirt instance void [System.Web]System.Web.HttpApplication::add_PostResolveRequestCache(class [mscorlib]System.EventHandler)
0x410f98  ldarg.1
0x410f99  ldarg.0
0x410f9a  ldftn    instance void Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::AcquireRequestStateHandler(object oSender, class [mscorlib]System.EventArgs ea)
0x410fa0  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x410fa5  callvirt instance void [System.Web]System.Web.HttpApplication::add_AcquireRequestState(class [mscorlib]System.EventHandler)
0x410faa  ldarg.1
0x410fab  ldarg.0
0x410fac  ldftn    instance void Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::PostAcquireRequestStateHandler(object oSender, class [mscorlib]System.EventArgs ea)
0x410fb2  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x410fb7  callvirt instance void [System.Web]System.Web.HttpApplication::add_PostAcquireRequestState(class [mscorlib]System.EventHandler)
0x410fbc  ldarg.1
0x410fbd  ldarg.0
0x410fbe  ldftn    instance void Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::PreRequestExecuteAppHandler(object oSender, class [mscorlib]System.EventArgs ea)
0x410fc4  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x410fc9  callvirt instance void [System.Web]System.Web.HttpApplication::add_PreRequestHandlerExecute(class [mscorlib]System.EventHandler)
0x410fce  ldarg.1
0x410fcf  ldarg.0
0x410fd0  ldftn    instance void Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::PreSendRequestHeaders(object oSender, class [mscorlib]System.EventArgs ea)
0x410fd6  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x410fdb  callvirt instance void [System.Web]System.Web.HttpApplication::add_PreSendRequestHeaders(class [mscorlib]System.EventHandler)
0x410fe0  ldarg.1
0x410fe1  ldarg.0
0x410fe2  ldftn    instance void Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::ErrorAppHandler(object oSender, class [mscorlib]System.EventArgs ea)
0x410fe8  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x410fed  callvirt instance void [System.Web]System.Web.HttpApplication::add_Error(class [mscorlib]System.EventHandler)
0x410ff2  ldarg.1
0x410ff3  ldarg.0
0x410ff4  ldftn    instance void Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::PostLogRequestHandler(object oSender, class [mscorlib]System.EventArgs ea)
0x410ffa  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x410fff  callvirt instance void [System.Web]System.Web.HttpApplication::add_PostLogRequest(class [mscorlib]System.EventHandler)
0x411004  ldarg.1
0x411005  ldarg.0
0x411006  ldftn    instance void Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::EndRequestHandler(object oSender, class [mscorlib]System.EventArgs ea)
0x41100c  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x411011  call     class [mscorlib]System.EventHandler Microsoft.SharePoint.ApplicationRuntime.RequestInstrumentationScopeManager::WrapEndRequestEventHandler(class [mscorlib]System.EventHandler originalEndRequestHandler)
0x411016  callvirt instance void [System.Web]System.Web.HttpApplication::add_EndRequest(class [mscorlib]System.EventHandler)
0x41101b  br       loc_4111E2
0x411020  ldc.i4   0x709022
0x411025  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Health()
0x41102a  ldc.i4.s 0x64
0x41102c  ldstr    aAzureTelemetry_0// "[Azure Telemetry] SPO - enabled."
0x411031  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x411036  ldarg.1
0x411037  ldstr    aMicrosoftFiles// "Microsoft_FileServices"
0x41103c  ldstr    aSpoSprequestmo// "SPO-SPRequestModule"
0x411041  ldstr    aHttpBeginreque// "Http.BeginRequestHandler"
0x411046  ldarg.0
0x411047  ldftn    instance void Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::BeginRequestHandler(object oSender, class [mscorlib]System.EventArgs ea)
0x41104d  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x411052  call     class [mscorlib]System.EventHandler Microsoft.SharePoint.ApplicationRuntime.RequestInstrumentationScopeManager::WrapBeginRequestEventHandler(class [mscorlib]System.EventHandler originalBeginRequestHandler)
0x411057  call     class [mscorlib]System.EventHandler Microsoft.SharePoint.AzureTelemetry.SPAzureTelemetryMonitoredScope::WrapEventHandler(string tenant, string workload, string stage, class [mscorlib]System.EventHandler eventHandler)
0x41105c  callvirt instance void [System.Web]System.Web.HttpApplication::add_BeginRequest(class [mscorlib]System.EventHandler)
0x411061  ldarg.1
0x411062  ldstr    aMicrosoftFiles// "Microsoft_FileServices"
0x411067  ldstr    aSpoSprequestmo// "SPO-SPRequestModule"
0x41106c  ldstr    aHttpPostauthen// "Http.PostAuthenticateRequestHandler"
0x411071  ldarg.0
0x411072  ldftn    instance void Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::PostAuthenticateRequestHandler(object oSender, class [mscorlib]System.EventArgs ea)
0x411078  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x41107d  call     class [mscorlib]System.EventHandler Microsoft.SharePoint.AzureTelemetry.SPAzureTelemetryMonitoredScope::WrapEventHandler(string tenant, string workload, string stage, class [mscorlib]System.EventHandler eventHandler)
0x411082  callvirt instance void [System.Web]System.Web.HttpApplication::add_PostAuthenticateRequest(class [mscorlib]System.EventHandler)
0x411087  ldarg.1
0x411088  ldstr    aMicrosoftFiles// "Microsoft_FileServices"
0x41108d  ldstr    aSpoSprequestmo// "SPO-SPRequestModule"
0x411092  ldstr    aHttpPostauthor// "Http.PostAuthorizeRequestHandler"
0x411097  ldarg.0
0x411098  ldftn    instance void Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::PostAuthorizeRequestHandler(object oSender, class [mscorlib]System.EventArgs ea)
0x41109e  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x4110a3  call     class [mscorlib]System.EventHandler Microsoft.SharePoint.AzureTelemetry.SPAzureTelemetryMonitoredScope::WrapEventHandler(string tenant, string workload, string stage, class [mscorlib]System.EventHandler eventHandler)
0x4110a8  callvirt instance void [System.Web]System.Web.HttpApplication::add_PostAuthorizeRequest(class [mscorlib]System.EventHandler)
0x4110ad  ldarg.1
0x4110ae  ldstr    aMicrosoftFiles// "Microsoft_FileServices"
0x4110b3  ldstr    aSpoSprequestmo// "SPO-SPRequestModule"
0x4110b8  ldstr    aHttpPostresolv// "Http.PostResolveRequestCacheHandler"
0x4110bd  ldarg.0
0x4110be  ldftn    instance void Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::PostResolveRequestCacheHandler(object oSender, class [mscorlib]System.EventArgs ea)
0x4110c4  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x4110c9  call     class [mscorlib]System.EventHandler Microsoft.SharePoint.AzureTelemetry.SPAzureTelemetryMonitoredScope::WrapEventHandler(string tenant, string workload, string stage, class [mscorlib]System.EventHandler eventHandler)
0x4110ce  callvirt instance void [System.Web]System.Web.HttpApplication::add_PostResolveRequestCache(class [mscorlib]System.EventHandler)
0x4110d3  ldarg.1
0x4110d4  ldstr    aMicrosoftFiles// "Microsoft_FileServices"
0x4110d9  ldstr    aSpoSprequestmo// "SPO-SPRequestModule"
0x4110de  ldstr    aHttpAcquirereq// "Http.AcquireRequestStateHandler"
0x4110e3  ldarg.0
0x4110e4  ldftn    instance void Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::AcquireRequestStateHandler(object oSender, class [mscorlib]System.EventArgs ea)
0x4110ea  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x4110ef  call     class [mscorlib]System.EventHandler Microsoft.SharePoint.AzureTelemetry.SPAzureTelemetryMonitoredScope::WrapEventHandler(string tenant, string workload, string stage, class [mscorlib]System.EventHandler eventHandler)
0x4110f4  callvirt instance void [System.Web]System.Web.HttpApplication::add_AcquireRequestState(class [mscorlib]System.EventHandler)
0x4110f9  ldarg.1
0x4110fa  ldstr    aMicrosoftFiles// "Microsoft_FileServices"
0x4110ff  ldstr    aSpoSprequestmo// "SPO-SPRequestModule"
0x411104  ldstr    aHttpPostacquir// "Http.PostAcquireRequestStateHandler"
0x411109  ldarg.0
0x41110a  ldftn    instance void Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::PostAcquireRequestStateHandler(object oSender, class [mscorlib]System.EventArgs ea)
0x411110  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x411115  call     class [mscorlib]System.EventHandler Microsoft.SharePoint.AzureTelemetry.SPAzureTelemetryMonitoredScope::WrapEventHandler(string tenant, string workload, string stage, class [mscorlib]System.EventHandler eventHandler)
0x41111a  callvirt instance void [System.Web]System.Web.HttpApplication::add_PostAcquireRequestState(class [mscorlib]System.EventHandler)
0x41111f  ldarg.1
0x411120  ldstr    aMicrosoftFiles// "Microsoft_FileServices"
0x411125  ldstr    aSpoSprequestmo// "SPO-SPRequestModule"
0x41112a  ldstr    aHttpPrerequest// "Http.PreRequestExecuteAppHandler"
0x41112f  ldarg.0
0x411130  ldftn    instance void Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::PreRequestExecuteAppHandler(object oSender, class [mscorlib]System.EventArgs ea)
0x411136  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x41113b  call     class [mscorlib]System.EventHandler Microsoft.SharePoint.AzureTelemetry.SPAzureTelemetryMonitoredScope::WrapEventHandler(string tenant, string workload, string stage, class [mscorlib]System.EventHandler eventHandler)
0x411140  callvirt instance void [System.Web]System.Web.HttpApplication::add_PreRequestHandlerExecute(class [mscorlib]System.EventHandler)
0x411145  ldarg.1
0x411146  ldstr    aMicrosoftFiles// "Microsoft_FileServices"
0x41114b  ldstr    aSpoSprequestmo// "SPO-SPRequestModule"
0x411150  ldstr    aHttpPresendreq// "Http.PreSendRequestHeaders"
0x411155  ldarg.0
0x411156  ldftn    instance void Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::PreSendRequestHeaders(object oSender, class [mscorlib]System.EventArgs ea)
0x41115c  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x411161  call     class [mscorlib]System.EventHandler Microsoft.SharePoint.AzureTelemetry.SPAzureTelemetryMonitoredScope::WrapEventHandler(string tenant, string workload, string stage, class [mscorlib]System.EventHandler eventHandler)
0x411166  callvirt instance void [System.Web]System.Web.HttpApplication::add_PreSendRequestHeaders(class [mscorlib]System.EventHandler)
0x41116b  ldarg.1
0x41116c  ldstr    aMicrosoftFiles// "Microsoft_FileServices"
0x411171  ldstr    aSpoSprequestmo// "SPO-SPRequestModule"
0x411176  ldstr    aHttpErrorappha// "Http.ErrorAppHandler"
0x41117b  ldarg.0
0x41117c  ldftn    instance void Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::ErrorAppHandler(object oSender, class [mscorlib]System.EventArgs ea)
0x411182  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x411187  call     class [mscorlib]System.EventHandler Microsoft.SharePoint.AzureTelemetry.SPAzureTelemetryMonitoredScope::WrapEventHandler(string tenant, string workload, string stage, class [mscorlib]System.EventHandler eventHandler)
0x41118c  callvirt instance void [System.Web]System.Web.HttpApplication::add_Error(class [mscorlib]System.EventHandler)
0x411191  ldarg.1
0x411192  ldstr    aMicrosoftFiles// "Microsoft_FileServices"
0x411197  ldstr    aSpoSprequestmo// "SPO-SPRequestModule"
0x41119c  ldstr    aHttpPostlogreq// "Http.PostLogRequestHandler"
0x4111a1  ldarg.0
0x4111a2  ldftn    instance void Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::PostLogRequestHandler(object oSender, class [mscorlib]System.EventArgs ea)
0x4111a8  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x4111ad  call     class [mscorlib]System.EventHandler Microsoft.SharePoint.AzureTelemetry.SPAzureTelemetryMonitoredScope::WrapEventHandler(string tenant, string workload, string stage, class [mscorlib]System.EventHandler eventHandler)
0x4111b2  callvirt instance void [System.Web]System.Web.HttpApplication::add_PostLogRequest(class [mscorlib]System.EventHandler)
0x4111b7  ldarg.1
0x4111b8  ldstr    aMicrosoftFiles// "Microsoft_FileServices"
0x4111bd  ldstr    aSpoSprequestmo// "SPO-SPRequestModule"
0x4111c2  ldstr    aHttpEndrequest// "Http.EndRequestHandler"
0x4111c7  ldarg.0
0x4111c8  ldftn    instance void Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::EndRequestHandler(object oSender, class [mscorlib]System.EventArgs ea)
0x4111ce  newobj   instance void [mscorlib]System.EventHandler::.ctor(object, native int)
0x4111d3  call     class [mscorlib]System.EventHandler Microsoft.SharePoint.ApplicationRuntime.RequestInstrumentationScopeManager::WrapEndRequestEventHandler(class [mscorlib]System.EventHandler originalEndRequestHandler)
0x4111d8  call     class [mscorlib]System.EventHandler Microsoft.SharePoint.AzureTelemetry.SPAzureTelemetryMonitoredScope::WrapEventHandler(string tenant, string workload, string stage, class [mscorlib]System.EventHandler eventHandler)
0x4111dd  callvirt instance void [System.Web]System.Web.HttpApplication::add_EndRequest(class [mscorlib]System.EventHandler)
0x4111e2  ldc.i4   0x50F6C0
0x4111e7  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AspRuntime()
  ... truncated ...
```
