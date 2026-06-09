# Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::PostResolveRequestCacheHandler

- ea: `0x414060`
- end: `0x414822`
- name: `Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::PostResolveRequestCacheHandler`
- size: `1986`
- prototype: ``
- caller_count: `0`
- callee_count: `67`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x195760`
- `0x1a1ea0`
- `0x1c89e0`
- `0x1fa2e0`
- `0x1fa460`
- `0x1fa530`
- `0x231e20`
- `0x231ec0`
- `0x232000`
- `0x232550`
- `0x26f650`
- `0x29d110`
- `0x29ffd0`
- `0x2eb6c0`
- `0x2eb9d0`
- `0x319a60`
- `0x321300`
- `0x360ef0`
- `0x361ad0`
- `0x363870`
- `0x372430`
- `0x372830`
- `0x372840`
- `0x372940`
- `0x388200`
- `0x388b90`
- `0x410db0`
- `0x4116a0`
- `0x413800`
- `0x413940`
- `0x413ad0`
- `0x414060`
- `0x414830`
- `0x419010`
- `0x419060`
- `0x419540`
- `0x419560`
- `0x4196e0`
- `0x419b20`
- `0x41a640`
- `0x41aac0`
- `0x41b9f0`
- `0x41bb50`
- `0x5966c0`
- `0x5967a0`
- `0x5b38e0`
- `0x5b3ce0`
- `0x5c10e0`
- `0x5c24f0`
- `0x6785e0`

## string_xrefs

- `0x41446f`: `CompleteRequestWasCalled`
- `0x4147ef`: `CompleteRequestWasCalled`
- `0x41406c`: `SPRequestModule.PostResolveRequestCacheHandler Begin`
- `0x4140ae`: `PostResolveRequestCacheHandler`
- `0x41420a`: `SPRequestModule.PostResolveRequestCacheHandler: Request being throttled. Sending 503.`
- `0x414369`: `SPRequestModule.PostResolveRequestCacheHandler: Cached context exists: '{0}'. Cached site subscription id: '{1}'. Correlation Id: '{2}'.`
- `0x414407`: `SPRequestModule.PostResolveRequestCacheHandler: before GetContextWeb`
- `0x41441b`: `Stop excessive thread aborts`
- `0x414441`: `SPRequestModule.PostResolveRequestCacheHandler: after GetContextWeb, content is {0} null`
- `0x4144a9`: `Server side redirection for request with filepath {0} should fallback because CompleteRequest was called`
- `0x4144db`: `SPRequestModule.PostResolveRequestCacheHandler: GetContextWeb throws: {0}`
- `0x414528`: `Server side redirection for request with filepath {0} should fallback because of error: {1}`
- `0x414662`: `SPRequestModule.PostResolveRequestCacheHandler: Could not get SPRequestModuleData. Sending 404.`
- `0x414684`: `SPRequestModule.PostResolveRequestCacheHandler: Could not get SPRequestModuleData. Sending 404.`
- `0x4146b9`: `Server side redirection for folder request {0} has unsuccessful mondo call, should fallback to native owssvr.dll`
- `0x414723`: `VTI_IS_INCLUDED_PATH`
- `0x414817`: `SPRequestModule.PostResolveRequestCacheHandler End`

## pseudocode

```c

```

## disassembly

```asm
0x414060  ldc.i4   0x5561DA
0x414065  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AspRuntime()
0x41406a  ldc.i4.s 0x32
0x41406c  ldstr    aSprequestmodul_12// "SPRequestModule.PostResolveRequestCache"...
0x414071  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x414076  ldarg.0
0x414077  ldfld    bool Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::_isAnonymousStaticRequest
0x41407c  brfalse.s loc_41407F
0x41407e  ret
0x41407f  ldarg.1
0x414080  isinst   [System.Web]System.Web.HttpApplication
0x414085  stloc.0
0x414086  ldloc.0
0x414087  brfalse.s loc_414091
0x414089  ldloc.0
0x41408a  callvirt instance class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpApplication::get_Context()
0x41408f  br.s     loc_414092
0x414091  ldnull
0x414092  stloc.1
0x414093  ldloc.1
0x414094  brfalse.s loc_41409D
0x414096  ldloc.1
0x414097  callvirt instance class [System.Web]System.Web.IHttpHandler [System.Web]System.Web.HttpContext::get_Handler()
0x41409c  pop
0x41409d  ldloc.1
0x41409e  brfalse  loc_41480B
0x4140a3  ldloc.1
0x4140a4  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x4140a9  brfalse  loc_41480B
0x4140ae  ldstr    aPostresolvereq// "PostResolveRequestCacheHandler"
0x4140b3  ldc.i4.s 0x64
0x4140b5  ldc.i4.1
0x4140b6  newarr   Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x4140bb  stloc.s  0x10
0x4140bd  ldloc.s  0x10
0x4140bf  ldc.i4.0
0x4140c0  newobj   instance void Microsoft.SharePoint.Utilities.SPSqlQueryCounter::.ctor()
0x4140c5  stelem.ref
0x4140c6  ldloc.s  0x10
0x4140c8  newobj   instance void Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string name, unsigned int32 maximumExecutionTime, class Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[] monitors)
0x4140cd  stloc.s  0x11
0x4140cf  ldloc.1
0x4140d0  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x4140d5  stloc.2
0x4140d6  ldsfld   class Microsoft.SharePoint.Utilities.SPPerformanceInspector Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::_PerformanceInspector
0x4140db  brfalse.s loc_414152
0x4140dd  ldloc.2
0x4140de  ldstr    aXSharepointhea// "X-SharePointHealthScore"
0x4140e3  ldsfld   class Microsoft.SharePoint.Utilities.SPPerformanceInspector Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::_PerformanceInspector
0x4140e8  callvirt instance int32 Microsoft.SharePoint.Utilities.SPPerformanceInspector::get_HealthScore()
0x4140ed  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x4140f2  call     string [mscorlib]System.Convert::ToString(int32, class [mscorlib]System.IFormatProvider)
0x4140f7  callvirt instance void [System.Web]System.Web.HttpResponse::AddHeader(string, string)
0x4140fc  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::_RequestManagementSettingsId
0x414101  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x414106  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x41410b  brfalse.s loc_414152
0x41410d  call     class Microsoft.SharePoint.Administration.SPFarm Microsoft.SharePoint.Administration.SPFarm::get_LocalOrThrow()
0x414112  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::_RequestManagementSettingsId
0x414117  callvirt instance class Microsoft.SharePoint.Administration.SPPersistedObject Microsoft.SharePoint.Administration.SPFarm::GetObject(valuetype [mscorlib]System.Guid id)
0x41411c  castclass Microsoft.SharePoint.Administration.SPRequestManagementSettings
0x414121  stloc.3
0x414122  ldloc.3
0x414123  ldnull
0x414124  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x414129  brfalse.s loc_414152
0x41412b  ldloc.3
0x41412c  callvirt instance bool Microsoft.SharePoint.Administration.SPRequestManagementSettings::IsRequestManagementServiceOnline()
0x414131  brfalse.s loc_414152
0x414133  ldloc.3
0x414134  callvirt instance class Microsoft.SharePoint.Administration.SPRoutingMachineHealth Microsoft.SharePoint.Administration.SPRequestManagementSettings::get_RoutingMachineHealth()
0x414139  call     class Microsoft.SharePoint.Administration.SPServer Microsoft.SharePoint.Administration.SPServer::get_LocalOrThrow()
0x41413e  callvirt instance string Microsoft.SharePoint.Administration.SPServer::get_Address()
0x414143  ldsfld   class Microsoft.SharePoint.Utilities.SPPerformanceInspector Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::_PerformanceInspector
0x414148  callvirt instance int32 Microsoft.SharePoint.Utilities.SPPerformanceInspector::get_HealthScore()
0x41414d  callvirt instance void Microsoft.SharePoint.Administration.SPRoutingMachineHealth::SetHealthForMachine(string machineAddress, int32 healthScore)
0x414152  ldsfld   class Microsoft.SharePoint.Utilities.SPPerformanceInspector Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::_PerformanceInspector
0x414157  brfalse  loc_414232
0x41415c  ldsfld   class Microsoft.SharePoint.Utilities.SPPerformanceInspector Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::_PerformanceInspector
0x414161  callvirt instance bool Microsoft.SharePoint.Utilities.SPPerformanceInspector::IsInThrottling()
0x414166  brfalse  loc_414232
0x41416b  ldsfld   class Microsoft.SharePoint.Utilities.SPPerformanceInspector Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::_PerformanceInspector
0x414170  ldloc.1
0x414171  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x414176  callvirt instance bool Microsoft.SharePoint.Utilities.SPPerformanceInspector::ShouldThrottleRequest(class [System.Web]System.Web.HttpRequest request)
0x41417b  brfalse  loc_414232
0x414180  ldloc.1
0x414181  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x414186  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x41418b  callvirt instance string [System]System.Uri::get_LocalPath()
0x414190  call     bool Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::IsIgnoreThrottling(string uri)
0x414195  brtrue   loc_414232
0x41419a  call     class Microsoft.SharePoint.Administration.SPRequestUsageMonitoredScope Microsoft.SharePoint.Administration.SPRequestUsageMonitoredScope::get_Local()
0x41419f  brfalse.s loc_4141C4
0x4141a1  call     class Microsoft.SharePoint.Administration.SPRequestUsageMonitoredScope Microsoft.SharePoint.Administration.SPRequestUsageMonitoredScope::get_Local()
0x4141a6  ldstr    aTypeHealthscor_0// "Type=\"HealthScoreTenThrottling\", Thro"...
0x4141ab  call     class Microsoft.SharePoint.Utilities.SPPerformanceInspector Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::get_PerformanceInspector()
0x4141b0  callvirt instance valuetype Microsoft.SharePoint.Utilities.SPRequestThrottleLevel Microsoft.SharePoint.Utilities.SPPerformanceInspector::get_CurrentServerThrottleLevel()
0x4141b5  box      Microsoft.SharePoint.Utilities.SPRequestThrottleLevel
0x4141ba  call     string [mscorlib]System.String::Format(string, object)
0x4141bf  callvirt instance void Microsoft.SharePoint.Administration.SPRequestUsageMonitoredScope::set_UsageLimitData(string value)
0x4141c4  ldloc.1
0x4141c5  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x4141ca  ldsfld   string Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::RequestIsThrottledFlag
0x4141cf  ldc.i4.1
0x4141d0  box      [mscorlib]System.Int32
0x4141d5  callvirt instance void [mscorlib]System.Collections.IDictionary::set_Item(object, object)
0x4141da  call     class Microsoft.SharePoint.ApplicationRuntime.SPRequestsProfiler Microsoft.SharePoint.ApplicationRuntime.SPRequestsProfiler::get_Local()
0x4141df  callvirt instance void Microsoft.SharePoint.ApplicationRuntime.SPRequestsProfiler::RequestReject()
0x4141e4  call     class Microsoft.SharePoint.Utilities.SPMonitoredScope Microsoft.SharePoint.Utilities.SPMonitoredScope::get_Current()
0x4141e9  callvirt instance class Microsoft.SharePoint.Utilities.SPMonitoredScope Microsoft.SharePoint.Utilities.SPMonitoredScope::get_Parent()
0x4141ee  stloc.s  4
0x4141f0  ldloc.s  4
0x4141f2  brfalse.s loc_414232
0x4141f4  ldloc.1
0x4141f5  ldc.i4.0
0x4141f6  ldc.i4.0
0x4141f7  call     bool Microsoft.SharePoint.Utilities.SPUtilityInternal::TrySendVroom429IfVroomRequest(class [System.Web]System.Web.HttpContext context, [opt] bool allowCompleteRequest, [opt] int32 retryAfterInterval)
0x4141fc  brtrue.s loc_414232
0x4141fe  ldc.i4   0x7E1751
0x414203  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AspRuntime()
0x414208  ldc.i4.s 0x32
0x41420a  ldstr    aSprequestmodul_13// "SPRequestModule.PostResolveRequestCache"...
0x41420f  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x414214  ldloc.1
0x414215  ldc.i4   0x1F7
0x41421a  ldloc.s  4
0x41421c  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.Utilities.SPMonitoredScope::get_Id()
0x414221  call     string Microsoft.SharePoint.Utilities.SPPerformanceInspector::CreateServerBusyPage(valuetype [mscorlib]System.Guid guid)
0x414226  ldstr    aTextHtml// "text/html"
0x41422b  ldnull
0x41422c  ldc.i4.0
0x41422d  call     void Microsoft.SharePoint.Utilities.SPUtilityInternal::SendResponse(class [System.Web]System.Web.HttpContext context, int32 code, string strBody, string strContentType, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> headers, [opt] bool allowCompleteRequest)
0x414232  ldloc.1
0x414233  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x414238  callvirt instance string [System.Web]System.Web.HttpRequest::get_FilePath()
0x41423d  stloc.s  5
0x41423f  ldloc.1
0x414240  call     void Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::HandleRedirectToIsolatedDomainForAppWebIfNeeded(class [System.Web]System.Web.HttpContext context)
0x414245  ldarg.0
0x414246  ldfld    bool Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::_isMobileRequest
0x41424b  brfalse.s loc_414253
0x41424d  ldloc.1
0x41424e  call     void Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::HandleMobilePageRequest(class [System.Web]System.Web.HttpContext context)
0x414253  ldarg.0
0x414254  ldfld    bool Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::_isMobileRequest
0x414259  brtrue.s loc_41426B
0x41425b  ldloc.1
0x41425c  ldloc.s  5
0x41425e  call     bool Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::IsMobileAspxPageRequest(class [System.Web]System.Web.HttpContext context, string filePath)
0x414263  brfalse.s loc_41426B
0x414265  ldloc.1
0x414266  call     void Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::HandleMobileRedirect(class [System.Web]System.Web.HttpContext context)
0x41426b  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::RedirectUnsuccessFallBackKillSwitchId
0x414270  ldstr    a1192017// "1/19/2017"
0x414275  ldstr    aOcwSharepointP_0// "OCW - sharepoint page server redirect f"...
0x41427a  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x41427f  brtrue.s loc_4142CC
0x414281  ldloc.1
0x414282  ldarg.0
0x414283  ldfld    bool Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::_exclusion
0x414288  ldloc.s  5
0x41428a  ldc.i4.1
0x41428b  call     bool Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::IsDatabaseAspxOrFolderPageRequest(class [System.Web]System.Web.HttpContext context, bool exclusion, string filePath, valuetype DatabaseASPX requestType)
0x414290  stloc.s  6
0x414292  ldloc.1
0x414293  ldarg.0
0x414294  ldfld    bool Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::_exclusion
0x414299  ldloc.s  5
0x41429b  ldc.i4.0
0x41429c  call     bool Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::IsDatabaseAspxOrFolderPageRequest(class [System.Web]System.Web.HttpContext context, bool exclusion, string filePath, valuetype DatabaseASPX requestType)
0x4142a1  stloc.s  7
0x4142a3  ldloc.s  6
0x4142a5  brtrue.s loc_4142AB
0x4142a7  ldloc.s  7
0x4142a9  br.s     loc_4142AC
0x4142ab  ldc.i4.1
0x4142ac  stloc.s  8
0x4142ae  call     bool Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::get_PageServerRedirectFeatureEnabled()
0x4142b3  brfalse.s loc_4142B9
0x4142b5  ldloc.s  8
0x4142b7  brtrue.s loc_4142C7
0x4142b9  call     bool Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::get_PageServerRedirectFeatureEnabled()
0x4142be  brtrue.s loc_4142C4
0x4142c0  ldloc.s  7
0x4142c2  br.s     loc_4142C8
0x4142c4  ldc.i4.0
0x4142c5  br.s     loc_4142C8
0x4142c7  ldc.i4.1
0x4142c8  stloc.s  9
0x4142ca  br.s     loc_41433B
0x4142cc  ldloc.1
0x4142cd  ldarg.0
0x4142ce  ldfld    bool Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::_exclusion
0x4142d3  ldloc.s  5
0x4142d5  ldc.i4.2
0x4142d6  call     bool Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::IsDatabaseAspxOrFolderPageRequest(class [System.Web]System.Web.HttpContext context, bool exclusion, string filePath, valuetype DatabaseASPX requestType)
0x4142db  brfalse.s loc_4142F1
0x4142dd  ldloc.1
0x4142de  ldarg.0
0x4142df  ldfld    bool Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::_exclusion
0x4142e4  ldloc.s  5
0x4142e6  ldc.i4.0
0x4142e7  call     bool Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::IsDatabaseAspxOrFolderPageRequest(class [System.Web]System.Web.HttpContext context, bool exclusion, string filePath, valuetype DatabaseASPX requestType)
0x4142ec  ldc.i4.0
0x4142ed  ceq
0x4142ef  br.s     loc_4142F2
0x4142f1  ldc.i4.0
0x4142f2  stloc.s  6
0x4142f4  ldloc.1
0x4142f5  ldarg.0
0x4142f6  ldfld    bool Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::_exclusion
0x4142fb  ldloc.s  5
0x4142fd  ldc.i4.0
0x4142fe  call     bool Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::IsDatabaseAspxOrFolderPageRequest(class [System.Web]System.Web.HttpContext context, bool exclusion, string filePath, valuetype DatabaseASPX requestType)
0x414303  stloc.s  7
0x414305  call     bool Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::get_PageServerRedirectFeatureEnabled()
0x41430a  brfalse.s loc_41431D
0x41430c  ldloc.1
0x41430d  ldarg.0
0x41430e  ldfld    bool Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::_exclusion
0x414313  ldloc.s  5
0x414315  ldc.i4.2
0x414316  call     bool Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::IsDatabaseAspxOrFolderPageRequest(class [System.Web]System.Web.HttpContext context, bool exclusion, string filePath, valuetype DatabaseASPX requestType)
0x41431b  brtrue.s loc_414338
0x41431d  call     bool Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::get_PageServerRedirectFeatureEnabled()
0x414322  brtrue.s loc_414335
0x414324  ldloc.1
0x414325  ldarg.0
0x414326  ldfld    bool Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::_exclusion
0x41432b  ldloc.s  5
0x41432d  ldc.i4.0
0x41432e  call     bool Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::IsDatabaseAspxOrFolderPageRequest(class [System.Web]System.Web.HttpContext context, bool exclusion, string filePath, valuetype DatabaseASPX requestType)
0x414333  br.s     loc_414339
0x414335  ldc.i4.0
0x414336  br.s     loc_414339
0x414338  ldc.i4.1
0x414339  stloc.s  9
0x41433b  ldloc.s  9
0x41433d  brfalse  loc_4146D3
0x414342  ldc.i4   0x2BA7
0x414347  call     bool Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId featureId)
0x41434c  brtrue.s loc_414352
0x41434e  ldc.i4.s 0x64
0x414350  br.s     loc_414354
0x414352  ldc.i4.s 0x32
0x414354  stloc.s  0xA
0x414356  call     class Microsoft.SharePoint.SPServiceContext Microsoft.SharePoint.SPServiceContext::get_CachedContext()
0x41435b  stloc.s  0xB
0x41435d  ldc.i4   0x118F104
0x414362  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x414367  ldloc.s  0xA
0x414369  ldstr    aSprequestmodul_14// "SPRequestModule.PostResolveRequestCache"...
0x41436e  ldc.i4.3
0x41436f  newarr   [mscorlib]System.Object
0x414374  stloc.s  0x12
0x414376  ldloc.s  0x12
0x414378  ldc.i4.0
0x414379  ldloc.s  0xB
0x41437b  ldnull
0x41437c  call     bool Microsoft.SharePoint.SPServiceContext::op_Inequality(class Microsoft.SharePoint.SPServiceContext serviceContextA, class Microsoft.SharePoint.SPServiceContext serviceContextB)
0x414381  box      [mscorlib]System.Boolean
0x414386  stelem.ref
0x414387  ldloc.s  0x12
0x414389  ldc.i4.1
0x41438a  ldloc.s  0xB
0x41438c  ldnull
0x41438d  call     bool Microsoft.SharePoint.SPServiceContext::op_Inequality(class Microsoft.SharePoint.SPServiceContext serviceContextA, class Microsoft.SharePoint.SPServiceContext serviceContextB)
0x414392  brfalse.s loc_4143A3
0x414394  ldloc.s  0xB
0x414396  callvirt instance class Microsoft.SharePoint.SPSiteSubscriptionIdentifier Microsoft.SharePoint.SPServiceContext::get_SiteSubscriptionId()
0x41439b  ldnull
0x41439c  call     bool Microsoft.SharePoint.SPSiteSubscriptionIdentifier::op_Inequality(class Microsoft.SharePoint.SPSiteSubscriptionIdentifier siteSubscriptionIdentifierA, class Microsoft.SharePoint.SPSiteSubscriptionIdentifier siteSubscriptionIdentifierB)
0x4143a1  brtrue.s loc_4143AA
0x4143a3  ldstr    aNA// "N/A"
0x4143a8  br.s     loc_4143C5
0x4143aa  ldloc.s  0xB
0x4143ac  callvirt instance class Microsoft.SharePoint.SPSiteSubscriptionIdentifier Microsoft.SharePoint.SPServiceContext::get_SiteSubscriptionId()
0x4143b1  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPSiteSubscriptionIdentifier::get_Id()
0x4143b6  stloc.s  0x13
0x4143b8  ldloca.s 0x13
0x4143ba  constrained. [mscorlib]System.Guid
0x4143c0  callvirt instance string [mscorlib]System.Object::ToString()
0x4143c5  stelem.ref
0x4143c6  ldloc.s  0x12
0x4143c8  ldc.i4.2
0x4143c9  ldloc.s  0xB
0x4143cb  ldnull
0x4143cc  call     bool Microsoft.SharePoint.SPServiceContext::op_Inequality(class Microsoft.SharePoint.SPServiceContext serviceContextA, class Microsoft.SharePoint.SPServiceContext serviceContextB)
0x4143d1  brtrue.s loc_4143DA
0x4143d3  ldstr    aNA// "N/A"
0x4143d8  br.s     loc_4143F0
0x4143da  ldloc.s  0xB
0x4143dc  callvirt instance valuetype [mscorlib]System.Guid Microsoft.SharePoint.SPServiceContext::get_CorrelationId()
0x4143e1  stloc.s  0x14
0x4143e3  ldloca.s 0x14
0x4143e5  constrained. [mscorlib]System.Guid
0x4143eb  callvirt instance string [mscorlib]System.Object::ToString()
0x4143f0  stelem.ref
0x4143f1  ldloc.s  0x12
  ... truncated ...
```
