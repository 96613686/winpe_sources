# Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::TrySignInUserFromCache

- ea: `0x4500`
- end: `0x4669`
- name: `Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::TrySignInUserFromCache`
- size: `361`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x4270`

## callees

- `0x4500`
- `0x4670`
- `0x4900`
- `0x13570`
- `0x22ae0`
- `0x22b00`
- `0x22c40`
- `0x258a0`

## string_xrefs

- `0x4503`: `tokenContext`
- `0x4536`: `SPApplicationAuthenticationModule: Failed to build cache key for user {0}`
- `0x456b`: `SPApplicationAuthenticationModule: No token cache available`
- `0x459b`: `Use the SPUtility to load the site subscription from URI.`
- `0x45df`: `SPApplicationAuthenticationModule: Looking up token cache. [SiteSubscriptionId: {0}], [CacheKey: {1}]`
- `0x461c`: `SPApplicationAuthenticationModule: User token does not exist in token cache.`
- `0x4634`: `SPApplicationAuthenticationModule: Found user token in token cache.`
- `0x463e`: `Setting thread identity using token from Cache using User Login Token`

## pseudocode

```c

```

## disassembly

```asm
0x4500  ldarg.0
0x4501  brtrue.s loc_450E
0x4503  ldstr    aTokencontext// "tokenContext"
0x4508  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x450d  throw
0x450e  ldarg.0
0x450f  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::get_Identity()
0x4514  ldc.i4.0
0x4515  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Item(int32)
0x451a  stloc.0
0x451b  ldloc.0
0x451c  brtrue.s loc_4520
0x451e  ldc.i4.0
0x451f  ret
0x4520  ldloc.0
0x4521  ldloca.s 1
0x4523  call     bool Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::TryBuildCacheKey(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity userIdentity, [out] string& cacheKey)
0x4528  brtrue.s loc_4556
0x452a  ldc.i4   0x2563D7
0x452f  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x4534  ldc.i4.s 0x32
0x4536  ldstr    aSpapplicationa_41// "SPApplicationAuthenticationModule: Fail"...
0x453b  ldc.i4.1
0x453c  newarr   [mscorlib]System.Object
0x4541  stloc.s  5
0x4543  ldloc.s  5
0x4545  ldc.i4.0
0x4546  ldloc.0
0x4547  callvirt instance string [mscorlib]System.Security.Principal.IIdentity::get_Name()
0x454c  stelem.ref
0x454d  ldloc.s  5
0x454f  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x4554  ldc.i4.0
0x4555  ret
0x4556  call     class Microsoft.SharePoint.IdentityModel.SPTokenCache Microsoft.SharePoint.IdentityModel.SPTokenCache::get_Current()
0x455b  stloc.2
0x455c  ldloc.2
0x455d  brtrue.s loc_4577
0x455f  ldc.i4   0x2563D8
0x4564  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x4569  ldc.i4.s 0xF
0x456b  ldstr    aSpapplicationa_42// "SPApplicationAuthenticationModule: No t"...
0x4570  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x4575  ldc.i4.0
0x4576  ret
0x4577  ldsfld   string [mscorlib]System.String::Empty
0x457c  stloc.3
0x457d  ldstr    aGettingSiteSub// "Getting Site Subscription Id"
0x4582  ldc.i4.s 0x32
0x4584  ldc.i4.0
0x4585  newarr   [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x458a  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.TraceSeverity, class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[])
0x458f  stloc.s  6
0x4591  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::UseUtilityLoadForSiteSubscription
0x4596  ldstr    a7242017// "7/24/2017"
0x459b  ldstr    aUseTheSputilit// "Use the SPUtility to load the site subs"...
0x45a0  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid, string, string)
0x45a5  brfalse.s loc_45B9
0x45a7  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAlternateUrl::get_ContextUri()
0x45ac  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x45b1  call     string Microsoft.SharePoint.IdentityModel.SPTokenCache::GetSubscriptionIdFromContext(string context)
0x45b6  stloc.3
0x45b7  br.s     loc_45C5
0x45b9  ldloc.2
0x45ba  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAlternateUrl::get_ContextUri()
0x45bf  callvirt instance string Microsoft.SharePoint.IdentityModel.SPTokenCache::GetSiteSubscriptionIdFromUri(class [System]System.Uri context)
0x45c4  stloc.3
0x45c5  leave.s  loc_45D3
0x45c7  ldloc.s  6
0x45c9  brfalse.s loc_45D2
0x45cb  ldloc.s  6
0x45cd  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x45d2  endfinally
0x45d3  ldc.i4   0x2563D9
0x45d8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x45dd  ldc.i4.s 0x32
0x45df  ldstr    aSpapplicationa_43// "SPApplicationAuthenticationModule: Look"...
0x45e4  ldc.i4.2
0x45e5  newarr   [mscorlib]System.Object
0x45ea  stloc.s  7
0x45ec  ldloc.s  7
0x45ee  ldc.i4.0
0x45ef  ldloc.3
0x45f0  stelem.ref
0x45f1  ldloc.s  7
0x45f3  ldc.i4.1
0x45f4  ldloc.1
0x45f5  stelem.ref
0x45f6  ldloc.s  7
0x45f8  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x45fd  ldloc.2
0x45fe  ldloc.3
0x45ff  ldloc.1
0x4600  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken Microsoft.SharePoint.IdentityModel.SPTokenCache::TryGetCachedToken(string subscriptionId, string identity)
0x4605  isinst   [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken
0x460a  stloc.s  4
0x460c  ldloc.s  4
0x460e  brtrue.s loc_4628
0x4610  ldc.i4   0x2563DA
0x4615  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x461a  ldc.i4.s 0x32
0x461c  ldstr    aSpapplicationa_44// "SPApplicationAuthenticationModule: User"...
0x4621  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x4626  ldc.i4.0
0x4627  ret
0x4628  ldc.i4   0x2563DB
0x462d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x4632  ldc.i4.s 0x32
0x4634  ldstr    aSpapplicationa_45// "SPApplicationAuthenticationModule: Foun"...
0x4639  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x463e  ldstr    aSettingThreadI_0// "Setting thread identity using token fro"...
0x4643  ldc.i4.s 0x64
0x4645  ldc.i4.0
0x4646  newarr   [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x464b  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.TraceSeverity, class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[])
0x4650  stloc.s  8
0x4652  ldloc.s  4
0x4654  call     void Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::SignInFromCache(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken sessionSecurityToken)
0x4659  leave.s  loc_4667
0x465b  ldloc.s  8
0x465d  brfalse.s loc_4666
0x465f  ldloc.s  8
0x4661  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4666  endfinally
0x4667  ldc.i4.1
0x4668  ret
```
