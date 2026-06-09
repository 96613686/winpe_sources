# Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::BeginRequestHandler

- ea: `0x4127a0`
- end: `0x41374b`
- name: `Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::BeginRequestHandler`
- size: `4011`
- prototype: ``
- caller_count: `0`
- callee_count: `88`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callees

- `0x17f7d0`
- `0x188770`
- `0x189150`
- `0x191d30`
- `0x19bae0`
- `0x19e7a0`
- `0x19f730`
- `0x1a1770`
- `0x1a1e90`
- `0x1c1b60`
- `0x1c8480`
- `0x1c89e0`
- `0x1fa290`
- `0x1fa2e0`
- `0x1fa790`
- `0x1faa00`
- `0x223ba0`
- `0x22b4f0`
- `0x22b510`
- `0x232000`
- `0x2697b0`
- `0x26b410`
- `0x29d0f0`
- `0x29d110`
- `0x29ffd0`
- `0x2e6c80`
- `0x2e6ca0`
- `0x2e6d80`
- `0x32cb80`
- `0x32cc50`
- `0x35f3a0`
- `0x35f3c0`
- `0x35f3e0`
- `0x35f400`
- `0x35f420`
- `0x360aa0`
- `0x360ac0`
- `0x360ae0`
- `0x360b00`
- `0x360b20`
- `0x360b40`
- `0x361810`
- `0x361aa0`
- `0x388200`
- `0x388390`
- `0x388b90`
- `0x407800`
- `0x410db0`
- `0x411230`
- `0x4116a0`

## string_xrefs

- `0x4131da`: `access_token`
- `0x412ae8`: `CompleteRequestWasCalled`
- `0x412fe5`: `.json`
- `0x413002`: `.json`
- `0x4135c9`: `DELETE`
- `0x4130fb`: `/_layouts/15/metadata/json/1/rootcertificate`
- `0x4130a7`: `/_layouts/15/metadata/json/1`
- `0x4130d0`: `/_layouts/15/metadata/json/1`
- `0x413122`: `/_layouts/15/metadata/json/1`
- `0x4130b9`: `jsonmetadata.ashx`
- `0x41310d`: `jsonmetadata.ashx`
- `0x4129b4`: `Finished sending response, start to complete the request.`
- `0x412b14`: `BeginRequestHandler Completing request early due to RouteTarget!=null`
- `0x412bdc`: `BeginRequestHandler Completing request prematurely due to potential spoof .css issue`
- `0x412bf9`: `BeginRequestHandler Completing request prematurely due to potential spoof .css issue`
- `0x412d66`: `VTI_IS_ACCESSIBILITY_MODE`
- `0x41301e`: `BeginRequestHandler Returning early with 403 Forbidden due to SOAP method sent to a json endpoint`
- `0x4131f2`: `tempauth`
- `0x413286`: `Fast Shared Access flight disabled, we will server.TransferRequest if necessary.`
- `0x4132e7`: `VTI_ANONSVC_PATH`
- `0x4133f6`: `Endpoint {0}, is not accessible in the scope of an app. Returning a 403.`
- `0x413436`: `FileNotAccessibleInApps`

## pseudocode

```c

```

## disassembly

```asm
0x4127a0  ldnull
0x4127a1  stloc.s  0x29
0x4127a3  newobj   instance void <>c__DisplayClass1c::.ctor()
0x4127a8  stloc.s  0x2A
0x4127aa  ldarg.1
0x4127ab  isinst   [System.Web]System.Web.HttpApplication
0x4127b0  stloc.0
0x4127b1  ldloc.0
0x4127b2  brfalse.s loc_4127BC
0x4127b4  ldloc.0
0x4127b5  callvirt instance class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpApplication::get_Context()
0x4127ba  br.s     loc_4127BD
0x4127bc  ldnull
0x4127bd  stloc.1
0x4127be  ldloc.s  0x2A
0x4127c0  ldloc.1
0x4127c1  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x4127c6  stfld    class [System.Web]System.Web.HttpRequest <>c__DisplayClass1c::req
0x4127cb  ldloc.s  0x2A
0x4127cd  ldfld    class [System.Web]System.Web.HttpRequest <>c__DisplayClass1c::req
0x4127d2  call     void Microsoft.SharePoint.ApplicationRuntime.SPHeaderManager::SetNativeRequestModuleServerVariables(class [System.Web]System.Web.HttpRequest req)
0x4127d7  call     class Microsoft.SharePoint.Administration.SPAppRequestDiagnosticSettings Microsoft.SharePoint.Administration.SPAppRequestDiagnosticSettings::get_Local()
0x4127dc  callvirt instance int32 Microsoft.SharePoint.Administration.SPAppRequestDiagnosticSettings::get_TraceCacheSampleNumber()
0x4127e1  ldc.i4.0
0x4127e2  ble.s    loc_41281E
0x4127e4  call     class [mscorlib]System.Random Microsoft.SharePoint.Utilities.SPUtility::get_RandomGenerator()
0x4127e9  call     class Microsoft.SharePoint.Administration.SPAppRequestDiagnosticSettings Microsoft.SharePoint.Administration.SPAppRequestDiagnosticSettings::get_Local()
0x4127ee  callvirt instance int32 Microsoft.SharePoint.Administration.SPAppRequestDiagnosticSettings::get_TraceCacheSampleNumber()
0x4127f3  callvirt instance int32 [mscorlib]System.Random::Next(int32)
0x4127f8  brtrue.s loc_41281E
0x4127fa  ldloc.1
0x4127fb  call     bool Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::IsCsomRestRequest(class [System.Web]System.Web.HttpContext context)
0x412800  brfalse.s loc_41281E
0x412802  ldc.i4   0x27BE
0x412807  ldnull
0x412808  ldnull
0x412809  call     bool Microsoft.SharePoint.DarkDeploymentUtility::IsFeatureEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId featureId, class Microsoft.SharePoint.SPContext context, [opt] class Microsoft.SharePoint.SPWeb web)
0x41280e  brfalse.s loc_41281E
0x412810  call     bool Microsoft.SharePoint.Utilities.SPUtility::CheckTraceCacheFilter()
0x412815  brfalse.s loc_41281E
0x412817  call     void Microsoft.SharePoint.Diagnostics.ULS::TurnOnThreadCache()
0x41281c  br.s     loc_412823
0x41281e  call     void Microsoft.SharePoint.Diagnostics.ULS::TurnOffThreadCache()
0x412823  ldc.i4   0x5561D8
0x412828  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AspRuntime()
0x41282d  ldc.i4.s 0x32
0x41282f  ldstr    aSprequestmodul_4// "SPRequestModule.BeginRequestHandler Beg"...
0x412834  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x412839  ldarg.0
0x41283a  call     instance void Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::EnsureInitialize()
0x41283f  ldnull
0x412840  stloc.2
0x412841  ldarg.0
0x412842  ldc.i4.0
0x412843  stfld    bool Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::_isAnonymousStaticRequest
0x412848  ldloc.1
0x412849  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x41284e  ldstr    aMicrosoftShare_79// "Microsoft.SharePoint.Client.RequestId"
0x412853  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x412858  brtrue.s loc_412874
0x41285a  ldloc.1
0x41285b  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x412860  ldstr    aMicrosoftShare_79// "Microsoft.SharePoint.Client.RequestId"
0x412865  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x41286a  box      [mscorlib]System.Guid
0x41286f  callvirt instance void [mscorlib]System.Collections.IDictionary::Add(object, object)
0x412874  ldarg.0
0x412875  ldloc.s  0x2A
0x412877  ldfld    class [System.Web]System.Web.HttpRequest <>c__DisplayClass1c::req
0x41287c  call     bool Microsoft.SharePoint.Administration.SPRequestPing::IsPingRequest(class [System.Web]System.Web.HttpRequest request)
0x412881  stfld    bool Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::_isPingRequest
0x412886  ldarg.0
0x412887  ldfld    bool Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::_isPingRequest
0x41288c  brfalse  loc_4129C5
0x412891  ldc.i4   0x64E64B
0x412896  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Runtime()
0x41289b  ldc.i4.s 0x64
0x41289d  ldstr    aStartToProcess// "Start to processing SPPING request."
0x4128a2  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x4128a7  ldsfld   class Microsoft.SharePoint.Utilities.SPPerformanceInspector Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::_PerformanceInspector
0x4128ac  brfalse.s loc_41290D
0x4128ae  ldsfld   class Microsoft.SharePoint.Utilities.SPPerformanceInspector Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::_PerformanceInspector
0x4128b3  callvirt instance bool Microsoft.SharePoint.Utilities.SPPerformanceInspector::IsInThrottling()
0x4128b8  brfalse.s loc_41290D
0x4128ba  ldc.i4   0x7E174F
0x4128bf  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AspRuntime()
0x4128c4  ldc.i4.s 0x32
0x4128c6  ldstr    aSprequestmodul_5// "SPRequestModule.BeginRequestHandler: SP"...
0x4128cb  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x4128d0  call     class Microsoft.SharePoint.Administration.SPRequestUsageMonitoredScope Microsoft.SharePoint.Administration.SPRequestUsageMonitoredScope::get_Local()
0x4128d5  brfalse.s loc_4128FA
0x4128d7  call     class Microsoft.SharePoint.Administration.SPRequestUsageMonitoredScope Microsoft.SharePoint.Administration.SPRequestUsageMonitoredScope::get_Local()
0x4128dc  ldstr    aTypeHealthscor// "Type=\"HealthScorePingThrottling\", Thr"...
0x4128e1  call     class Microsoft.SharePoint.Utilities.SPPerformanceInspector Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::get_PerformanceInspector()
0x4128e6  callvirt instance valuetype Microsoft.SharePoint.Utilities.SPRequestThrottleLevel Microsoft.SharePoint.Utilities.SPPerformanceInspector::get_CurrentServerThrottleLevel()
0x4128eb  box      Microsoft.SharePoint.Utilities.SPRequestThrottleLevel
0x4128f0  call     string [mscorlib]System.String::Format(string, object)
0x4128f5  callvirt instance void Microsoft.SharePoint.Administration.SPRequestUsageMonitoredScope::set_UsageLimitData(string value)
0x4128fa  ldloc.1
0x4128fb  ldc.i4   0x1F7
0x412900  ldsfld   string [mscorlib]System.String::Empty
0x412905  ldnull
0x412906  ldnull
0x412907  ldc.i4.0
0x412908  call     void Microsoft.SharePoint.Utilities.SPUtilityInternal::SendResponse(class [System.Web]System.Web.HttpContext context, int32 code, string strBody, string strContentType, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> headers, [opt] bool allowCompleteRequest)
0x41290d  ldc.i4   0x64E64C
0x412912  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Runtime()
0x412917  ldc.i4.s 0x64
0x412919  ldstr    aStartToDoSppin// "Start to do SPPING works."
0x41291e  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x412923  ldloc.1
0x412924  call     void Microsoft.SharePoint.Administration.SPRequestPing::DoPingWork(class [System.Web]System.Web.HttpContext context)
0x412929  ldc.i4   0x64E64D
0x41292e  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Runtime()
0x412933  ldc.i4.s 0x64
0x412935  ldstr    aFinishedSpping// "Finished SPPING works."
0x41293a  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x41293f  call     class Microsoft.SharePoint.Administration.SPFarm Microsoft.SharePoint.Administration.SPFarm::get_LocalOrThrow()
0x412944  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::_WebApplicationId
0x412949  callvirt instance class Microsoft.SharePoint.Administration.SPPersistedObject Microsoft.SharePoint.Administration.SPFarm::GetObject(valuetype [mscorlib]System.Guid id)
0x41294e  isinst   Microsoft.SharePoint.Administration.SPWebApplication
0x412953  call     int32 Microsoft.SharePoint.Administration.SPRequestPing::GetPingReturnCode(class Microsoft.SharePoint.Administration.SPWebApplication webApp)
0x412958  stloc.3
0x412959  ldc.i4   0x64E64E
0x41295e  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Runtime()
0x412963  ldc.i4.s 0x64
0x412965  ldstr    aStartToSendRes// "Start to send response."
0x41296a  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x41296f  ldc.i4   0x7E1750
0x412974  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AspRuntime()
0x412979  ldc.i4.s 0x32
0x41297b  ldstr    aSprequestmodul_6// "SPRequestModule.BeginRequestHandler: SP"...
0x412980  ldc.i4.1
0x412981  newarr   [mscorlib]System.Object
0x412986  stloc.s  0x2B
0x412988  ldloc.s  0x2B
0x41298a  ldc.i4.0
0x41298b  ldloc.3
0x41298c  box      [mscorlib]System.Int32
0x412991  stelem.ref
0x412992  ldloc.s  0x2B
0x412994  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x412999  ldloc.1
0x41299a  ldloc.3
0x41299b  ldsfld   string [mscorlib]System.String::Empty
0x4129a0  ldnull
0x4129a1  ldnull
0x4129a2  ldc.i4.0
0x4129a3  call     void Microsoft.SharePoint.Utilities.SPUtilityInternal::SendResponse(class [System.Web]System.Web.HttpContext context, int32 code, string strBody, string strContentType, [opt] class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> headers, [opt] bool allowCompleteRequest)
0x4129a8  ldc.i4   0x64E64F
0x4129ad  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Runtime()
0x4129b2  ldc.i4.s 0x64
0x4129b4  ldstr    aFinishedSendin// "Finished sending response, start to com"...
0x4129b9  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x4129be  ldloc.0
0x4129bf  callvirt instance void [System.Web]System.Web.HttpApplication::CompleteRequest()
0x4129c4  ret
0x4129c5  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::_RequestManagementSettingsId
0x4129ca  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x4129cf  call     bool [mscorlib]System.Guid::op_Inequality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x4129d4  brfalse  loc_412B61
0x4129d9  call     class Microsoft.SharePoint.Administration.SPFarm Microsoft.SharePoint.Administration.SPFarm::get_LocalOrThrow()
0x4129de  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::_RequestManagementSettingsId
0x4129e3  callvirt instance class Microsoft.SharePoint.Administration.SPPersistedObject Microsoft.SharePoint.Administration.SPFarm::GetObject(valuetype [mscorlib]System.Guid id)
0x4129e8  castclass Microsoft.SharePoint.Administration.SPRequestManagementSettings
0x4129ed  stloc.s  4
0x4129ef  ldloc.s  4
0x4129f1  ldnull
0x4129f2  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x4129f7  brfalse  loc_412B30
0x4129fc  ldloc.s  4
0x4129fe  ldloc.s  0x2A
0x412a00  ldfld    class [System.Web]System.Web.HttpRequest <>c__DisplayClass1c::req
0x412a05  callvirt instance bool Microsoft.SharePoint.Administration.SPRequestManagementSettings::IsRequestManagementEnabledForRequest(class [System.Web]System.Web.HttpRequest request)
0x412a0a  brfalse  loc_412B30
0x412a0f  ldarg.0
0x412a10  ldc.i4.1
0x412a11  stfld    bool Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::_isRequestManagementRequest
0x412a16  ldloc.s  0x2A
0x412a18  ldfld    class [System.Web]System.Web.HttpRequest <>c__DisplayClass1c::req
0x412a1d  ldloc.s  0x2A
0x412a1f  ldfld    class [System.Web]System.Web.HttpRequest <>c__DisplayClass1c::req
0x412a24  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x412a29  callvirt instance string [mscorlib]System.Object::ToString()
0x412a2e  call     string Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::BuildRequestUsageScopeName(class [System.Web]System.Web.HttpRequest req, string uri)
0x412a33  newobj   instance void Microsoft.SharePoint.Administration.SPRequestUsageMonitoredScope::.ctor(string name)
0x412a38  stloc.2
0x412a39  ldloc.s  4
0x412a3b  ldloc.1
0x412a3c  callvirt instance class Microsoft.SharePoint.Administration.SPRequestManagementProcessResult Microsoft.SharePoint.Administration.SPRequestManagementSettings::ProcessRequest(class [System.Web]System.Web.HttpContext context)
0x412a41  stloc.s  5
0x412a43  ldloc.2
0x412a44  callvirt T0x2B00029D
0x412a49  stloc.s  6
0x412a4b  ldloc.s  6
0x412a4d  brfalse.s loc_412AA9
0x412a4f  ldloc.s  5
0x412a51  callvirt instance class Microsoft.SharePoint.Administration.SPRoutingMachineInfo Microsoft.SharePoint.Administration.SPRequestManagementProcessResult::get_RouteTarget()
0x412a56  ldnull
0x412a57  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x412a5c  brfalse.s loc_412A71
0x412a5e  ldloc.s  6
0x412a60  ldloc.s  5
0x412a62  callvirt instance class Microsoft.SharePoint.Administration.SPRoutingMachineInfo Microsoft.SharePoint.Administration.SPRequestManagementProcessResult::get_RouteTarget()
0x412a67  callvirt instance string Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x412a6c  callvirt instance void Microsoft.SharePoint.Administration.SPRequestManagementCounter::set_RequestManagementRoutedServerUrl(string value)
0x412a71  ldloc.s  6
0x412a73  ldloc.s  5
0x412a75  callvirt instance bool Microsoft.SharePoint.Administration.SPRequestManagementProcessResult::get_IsThrottled()
0x412a7a  callvirt instance void Microsoft.SharePoint.Administration.SPRequestManagementCounter::set_RequestManagementThrottled(bool value)
0x412a7f  ldloc.s  6
0x412a81  ldloc.s  5
0x412a83  callvirt instance valuetype [mscorlib]System.Nullable`1<int64> Microsoft.SharePoint.Administration.SPRequestManagementProcessResult::get_UploadDuration()
0x412a88  callvirt instance void Microsoft.SharePoint.Administration.SPRequestManagementCounter::set_RequestManagementUploadDuration(valuetype [mscorlib]System.Nullable`1<int64> value)
0x412a8d  ldloc.s  6
0x412a8f  ldloc.s  5
0x412a91  callvirt instance valuetype [mscorlib]System.Nullable`1<int64> Microsoft.SharePoint.Administration.SPRequestManagementProcessResult::get_ResponseDuration()
0x412a96  callvirt instance void Microsoft.SharePoint.Administration.SPRequestManagementCounter::set_RequestManagementResponseDuration(valuetype [mscorlib]System.Nullable`1<int64> value)
0x412a9b  ldloc.s  6
0x412a9d  ldloc.s  5
0x412a9f  callvirt instance valuetype [mscorlib]System.Nullable`1<int64> Microsoft.SharePoint.Administration.SPRequestManagementProcessResult::get_DownloadDuration()
0x412aa4  callvirt instance void Microsoft.SharePoint.Administration.SPRequestManagementCounter::set_RequestManagementDownloadDuration(valuetype [mscorlib]System.Nullable`1<int64> value)
0x412aa9  ldloc.s  5
0x412aab  callvirt instance bool Microsoft.SharePoint.Administration.SPRequestManagementProcessResult::get_IsThrottled()
0x412ab0  brtrue.s loc_412ABB
0x412ab2  ldloc.s  5
0x412ab4  callvirt instance bool Microsoft.SharePoint.Administration.SPRequestManagementProcessResult::get_IsFailedRequest()
0x412ab9  brfalse.s loc_412AF9
0x412abb  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::EfficientThrottlingKillSwitchId2
0x412ac0  ldstr    a552018// "5/5/2018"
0x412ac5  ldstr    aMoreEfficientT_0// "More efficient throttling part 2"
0x412aca  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x412acf  ldc.i4.0
0x412ad0  ceq
0x412ad2  stloc.s  7
0x412ad4  ldloc.1
0x412ad5  ldc.i4.s 0x78
0x412ad7  ldloc.s  7
0x412ad9  call     void Microsoft.SharePoint.Utilities.SPUtilityInternal::SendResourceThrottledResponse(class [System.Web]System.Web.HttpContext context, [opt] int32 retryAfterInterval, [opt] bool allowCompleteRequest)
0x412ade  ldloc.s  7
0x412ae0  brfalse.s loc_412B30
0x412ae2  ldloc.1
0x412ae3  callvirt instance class [mscorlib]System.Collections.IDictionary [System.Web]System.Web.HttpContext::get_Items()
0x412ae8  ldstr    aCompletereques// "CompleteRequestWasCalled"
0x412aed  callvirt instance bool [mscorlib]System.Collections.IDictionary::Contains(object)
0x412af2  brfalse.s loc_412B30
0x412af4  leave    loc_412BEC
0x412af9  ldloc.s  5
0x412afb  callvirt instance class Microsoft.SharePoint.Administration.SPRoutingMachineInfo Microsoft.SharePoint.Administration.SPRequestManagementProcessResult::get_RouteTarget()
0x412b00  ldnull
0x412b01  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x412b06  brfalse.s loc_412B29
0x412b08  ldc.i4   0x58F88A
0x412b0d  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Runtime()
0x412b12  ldc.i4.s 0x32
0x412b14  ldstr    aBeginrequestha// "BeginRequestHandler Completing request "...
0x412b19  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x412b1e  ldloc.0
0x412b1f  callvirt instance void [System.Web]System.Web.HttpApplication::CompleteRequest()
0x412b24  leave    loc_412BEC
0x412b29  ldarg.0
0x412b2a  ldc.i4.0
0x412b2b  stfld    bool Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::_isRequestManagementRequest
0x412b30  leave.s  loc_412B61
0x412b32  stloc.s  8
0x412b34  ldc.i4   0x17DB088
0x412b39  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_RequestManagement()
0x412b3e  ldc.i4.s 0x14
0x412b40  ldstr    aRequestManagem_5// "Request management failed. {0}"
0x412b45  ldc.i4.1
0x412b46  newarr   [mscorlib]System.Object
0x412b4b  stloc.s  0x2C
0x412b4d  ldloc.s  0x2C
0x412b4f  ldc.i4.0
0x412b50  ldloc.s  8
0x412b52  callvirt instance string [mscorlib]System.Exception::get_Message()
0x412b57  stelem.ref
0x412b58  ldloc.s  0x2C
0x412b5a  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x412b5f  leave.s  loc_412B61
0x412b61  ldloc.s  0x2A
0x412b63  ldfld    class [System.Web]System.Web.HttpRequest <>c__DisplayClass1c::req
0x412b68  callvirt instance string [System.Web]System.Web.HttpRequest::get_PathInfo()
0x412b6d  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x412b72  brtrue   loc_412C0A
0x412b77  ldloc.s  0x2A
0x412b79  ldfld    class [System.Web]System.Web.HttpRequest <>c__DisplayClass1c::req
0x412b7e  callvirt instance string [System.Web]System.Web.HttpRequest::get_PathInfo()
0x412b83  ldstr    aCss// ".css"
0x412b88  ldc.i4.5
0x412b89  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x412b8e  brfalse.s loc_412C0A
0x412b90  ldstr    a8f87bed38a6c4a// "{8F87BED3-8A6C-4A6F-84AA-BFDA40B858F5}"
0x412b95  newobj   instance void [mscorlib]System.Guid::.ctor(string)
0x412b9a  ldstr    a07182016// "07/18/2016"
0x412b9f  ldstr    aAllowCssDownlo// "Allow CSS download in publiccdn.ashx"
0x412ba4  call     bool Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid id, string lastModifiedDate, string label)
0x412ba9  brtrue.s loc_412BED
0x412bab  ldsfld   string[] Microsoft.SharePoint.ApplicationRuntime.SPRequestModule::s_AllowCssDownloadWithNonEmptyPathInfo
0x412bb0  ldloc.s  0x29
  ... truncated ...
```
