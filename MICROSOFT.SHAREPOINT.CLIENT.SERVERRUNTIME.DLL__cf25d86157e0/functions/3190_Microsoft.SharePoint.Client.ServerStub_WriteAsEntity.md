# Microsoft.SharePoint.Client.ServerStub::WriteAsEntity

- ea: `0x3190`
- end: `0x3381`
- name: `Microsoft.SharePoint.Client.ServerStub::WriteAsEntity`
- size: `497`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x3130`

## callees

- `0xa30`
- `0xa50`
- `0xba0`
- `0x2930`
- `0x2c20`
- `0x3190`
- `0x3390`
- `0x3660`
- `0x3a40`
- `0xe080`
- `0xe120`
- `0xe6c0`
- `0x15030`
- `0x15200`
- `0x152f0`
- `0x18670`
- `0x1d4a0`
- `0x1d670`
- `0x1d680`

## string_xrefs

- `0x3309`: `_WriteAsEntity`
- `0x31d4`: `_GetObjectUrlPath`

## pseudocode

```c

```

## disassembly

```asm
0x3190  ldarg.0
0x3191  ldarg.1
0x3192  ldarg.s  4
0x3194  callvirt instance void Microsoft.SharePoint.Client.ServerStub::OnRESTfulQuerying(object obj, class Microsoft.SharePoint.Client.RESTfulQuery query)
0x3199  newobj   instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataEntry::.ctor()
0x319e  stloc.0
0x319f  ldarg.s  5
0x31a1  callvirt instance valuetype Microsoft.SharePoint.Client.ODataMetadataLevel Microsoft.SharePoint.Client.ProxyContext::get_MetadataLevel()
0x31a6  call     bool Microsoft.SharePoint.Client.ODataMetadataHelper::IsJsonLight(valuetype Microsoft.SharePoint.Client.ODataMetadataLevel metadataLevel)
0x31ab  brfalse.s loc_31B7
0x31ad  ldloc.0
0x31ae  ldarg.1
0x31af  ldarg.s  5
0x31b1  ldnull
0x31b2  call     void Microsoft.SharePoint.Client.Rest.JsonLightUtility::LightupJsonLightWriter(class [Microsoft.Data.OData]Microsoft.Data.OData.ODataItem item, object entity, class Microsoft.SharePoint.Client.ProxyContext proxyContext, string expectedTypeName)
0x31b7  ldarg.2
0x31b8  ldnull
0x31b9  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x31be  brfalse.s loc_320A
0x31c0  call     bool Microsoft.SharePoint.Client.ServerStub::get_IsMonitoredScopeRemovalKillSwitchActive()
0x31c5  brfalse.s loc_3201
0x31c7  ldarg.s  5
0x31c9  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0x31ce  ldarg.0
0x31cf  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.Client.ServerStub::get_TargetType()
0x31d4  ldstr    aGetobjecturlpa// "_GetObjectUrlPath"
0x31d9  ldc.i4.0
0x31da  callvirt instance class Microsoft.SharePoint.Client.IClientServiceMonitoredScope Microsoft.SharePoint.Client.ClientServiceHost::CreateMonitoredScope(class [mscorlib]System.Type type, string memberName, valuetype Microsoft.SharePoint.Client.MonitoredScopeType scopeType)
0x31df  stloc.1
0x31e0  ldarg.0
0x31e1  ldarg.1
0x31e2  callvirt instance class [System]System.Uri Microsoft.SharePoint.Client.ServerStub::GetObjectUrlPath(object target)
0x31e7  starg.s  2
0x31e9  leave.s  loc_31F5
0x31eb  stloc.2
0x31ec  ldloc.1
0x31ed  ldloc.2
0x31ee  callvirt instance void Microsoft.SharePoint.Client.IClientServiceMonitoredScope::LogException(class [mscorlib]System.Exception exception)
0x31f3  rethrow
0x31f5  leave.s  loc_320A
0x31f7  ldloc.1
0x31f8  brfalse.s loc_3200
0x31fa  ldloc.1
0x31fb  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3200  endfinally
0x3201  ldarg.0
0x3202  ldarg.1
0x3203  callvirt instance class [System]System.Uri Microsoft.SharePoint.Client.ServerStub::GetObjectUrlPath(object target)
0x3208  starg.s  2
0x320a  ldarg.2
0x320b  ldnull
0x320c  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x3211  brfalse.s loc_323A
0x3213  ldarg.0
0x3214  callvirt instance string Microsoft.SharePoint.Client.ServerStub::get_TargetTypeScriptClientFullName()
0x3219  call     valuetype [mscorlib]System.Guid [mscorlib]System.Guid::NewGuid()
0x321e  stloc.s  7
0x3220  ldloca.s 7
0x3222  constrained. [mscorlib]System.Guid
0x3228  callvirt instance string [mscorlib]System.Object::ToString()
0x322d  call     string [mscorlib]System.String::Concat(string, string)
0x3232  ldc.i4.2
0x3233  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0x3238  starg.s  2
0x323a  ldloc.0
0x323b  ldarg.s  5
0x323d  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0x3242  callvirt instance class [System]System.Uri Microsoft.SharePoint.Client.ClientServiceHost::get_ServiceBaseUriWithPathPartition()
0x3247  ldarg.2
0x3248  callvirt instance string [mscorlib]System.Object::ToString()
0x324d  newobj   instance void [System]System.Uri::.ctor(class [System]System.Uri, string)
0x3252  callvirt instance string [mscorlib]System.Object::ToString()
0x3257  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataEntry::set_Id(string)
0x325c  ldloc.0
0x325d  ldarg.2
0x325e  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataEntry::set_EditLink(class [System]System.Uri)
0x3263  ldloc.0
0x3264  ldarg.0
0x3265  callvirt instance string Microsoft.SharePoint.Client.ServerStub::get_TargetTypeScriptClientFullName()
0x326a  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataEntry::set_TypeName(string)
0x326f  ldarg.s  5
0x3271  callvirt instance valuetype Microsoft.SharePoint.Client.ODataMetadataLevel Microsoft.SharePoint.Client.ProxyContext::get_MetadataLevel()
0x3276  call     bool Microsoft.SharePoint.Client.ODataMetadataHelper::ShouldAddTypeNameAnnotation(valuetype Microsoft.SharePoint.Client.ODataMetadataLevel metadataLevel)
0x327b  brfalse.s loc_3296
0x327d  ldloc.0
0x327e  newobj   instance void [Microsoft.Data.OData]Microsoft.Data.OData.SerializationTypeNameAnnotation::.ctor()
0x3283  stloc.3
0x3284  ldloc.3
0x3285  ldarg.0
0x3286  callvirt instance string Microsoft.SharePoint.Client.ServerStub::get_TargetTypeScriptClientFullName()
0x328b  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.SerializationTypeNameAnnotation::set_TypeName(string)
0x3290  ldloc.3
0x3291  callvirt T0x2B000008
0x3296  ldnull
0x3297  stloc.s  4
0x3299  call     bool Microsoft.SharePoint.Client.ServerStub::get_IsMonitoredScopeRemovalKillSwitchActive()
0x329e  brfalse.s loc_32E0
0x32a0  ldarg.s  5
0x32a2  callvirt instance class Microsoft.SharePoint.Client.ClientServiceHost Microsoft.SharePoint.Client.ProxyContext::get_ServiceHost()
0x32a7  ldarg.0
0x32a8  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.Client.ServerStub::get_TargetType()
0x32ad  ldstr    aGetetag// "_GetETag"
0x32b2  ldc.i4.0
0x32b3  callvirt instance class Microsoft.SharePoint.Client.IClientServiceMonitoredScope Microsoft.SharePoint.Client.ClientServiceHost::CreateMonitoredScope(class [mscorlib]System.Type type, string memberName, valuetype Microsoft.SharePoint.Client.MonitoredScopeType scopeType)
0x32b8  stloc.s  5
0x32ba  ldarg.0
0x32bb  ldarg.1
0x32bc  call     instance string Microsoft.SharePoint.Client.ServerStub::GetObjectETagHttpHeaderValue(object value)
0x32c1  stloc.s  4
0x32c3  leave.s  loc_32D2
0x32c5  stloc.s  6
0x32c7  ldloc.s  5
0x32c9  ldloc.s  6
0x32cb  callvirt instance void Microsoft.SharePoint.Client.IClientServiceMonitoredScope::LogException(class [mscorlib]System.Exception exception)
0x32d0  rethrow
0x32d2  leave.s  loc_32E9
0x32d4  ldloc.s  5
0x32d6  brfalse.s loc_32DF
0x32d8  ldloc.s  5
0x32da  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x32df  endfinally
0x32e0  ldarg.0
0x32e1  ldarg.1
0x32e2  call     instance string Microsoft.SharePoint.Client.ServerStub::GetObjectETagHttpHeaderValue(object value)
0x32e7  stloc.s  4
0x32e9  ldloc.s  4
0x32eb  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x32f0  brtrue.s loc_32FA
0x32f2  ldloc.0
0x32f3  ldloc.s  4
0x32f5  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataEntry::set_ETag(string)
0x32fa  call     bool Microsoft.SharePoint.Client.ServerStub::get_IsMonitoredScopeRemovalKillSwitchActive()
0x32ff  brfalse.s loc_3354
0x3301  ldarg.s  5
0x3303  ldarg.0
0x3304  callvirt instance class [mscorlib]System.Type Microsoft.SharePoint.Client.ServerStub::get_TargetType()
0x3309  ldstr    aWriteasentity// "_WriteAsEntity"
0x330e  call     string Microsoft.SharePoint.Client.Utility::GetMonitoredScopeName(class [mscorlib]System.Type type, string memberName)
0x3313  callvirt instance class [mscorlib]System.IDisposable Microsoft.SharePoint.Client.ProxyContext::CreatePerformanceMarkerScope(string scopeName)
0x3318  stloc.s  8
0x331a  ldloc.0
0x331b  ldarg.0
0x331c  ldarg.1
0x331d  ldarg.s  4
0x331f  ldarg.s  5
0x3321  ldc.i4.1
0x3322  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Data.OData]Microsoft.Data.OData.ODataProperty> Microsoft.SharePoint.Client.ServerStub::GetODataScalarProperties(object value, class Microsoft.SharePoint.Client.RESTfulQuery query, class Microsoft.SharePoint.Client.ProxyContext proxyContext, bool includeExpandoField)
0x3327  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataEntry::set_Properties(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Data.OData]Microsoft.Data.OData.ODataProperty>)
0x332c  ldarg.3
0x332d  ldloc.0
0x332e  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataWriter::WriteStart(class [Microsoft.Data.OData]Microsoft.Data.OData.ODataEntry)
0x3333  ldarg.0
0x3334  ldarg.1
0x3335  ldarg.2
0x3336  ldarg.3
0x3337  ldarg.s  4
0x3339  ldarg.s  5
0x333b  call     instance void Microsoft.SharePoint.Client.ServerStub::WriteNavigationProperties(object value, class [System]System.Uri path, class [Microsoft.Data.OData]Microsoft.Data.OData.ODataWriter writer, class Microsoft.SharePoint.Client.RESTfulQuery query, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x3340  ldarg.3
0x3341  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataWriter::WriteEnd()
0x3346  leave.s  loc_3380
0x3348  ldloc.s  8
0x334a  brfalse.s loc_3353
0x334c  ldloc.s  8
0x334e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3353  endfinally
0x3354  ldloc.0
0x3355  ldarg.0
0x3356  ldarg.1
0x3357  ldarg.s  4
0x3359  ldarg.s  5
0x335b  ldc.i4.1
0x335c  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Data.OData]Microsoft.Data.OData.ODataProperty> Microsoft.SharePoint.Client.ServerStub::GetODataScalarProperties(object value, class Microsoft.SharePoint.Client.RESTfulQuery query, class Microsoft.SharePoint.Client.ProxyContext proxyContext, bool includeExpandoField)
0x3361  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataEntry::set_Properties(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.Data.OData]Microsoft.Data.OData.ODataProperty>)
0x3366  ldarg.3
0x3367  ldloc.0
0x3368  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataWriter::WriteStart(class [Microsoft.Data.OData]Microsoft.Data.OData.ODataEntry)
0x336d  ldarg.0
0x336e  ldarg.1
0x336f  ldarg.2
0x3370  ldarg.3
0x3371  ldarg.s  4
0x3373  ldarg.s  5
0x3375  call     instance void Microsoft.SharePoint.Client.ServerStub::WriteNavigationProperties(object value, class [System]System.Uri path, class [Microsoft.Data.OData]Microsoft.Data.OData.ODataWriter writer, class Microsoft.SharePoint.Client.RESTfulQuery query, class Microsoft.SharePoint.Client.ProxyContext proxyContext)
0x337a  ldarg.3
0x337b  callvirt instance void [Microsoft.Data.OData]Microsoft.Data.OData.ODataWriter::WriteEnd()
0x3380  ret
```
