# Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::TryReadSessionTokenFromCache

- ea: `0x59f0`
- end: `0x5b0e`
- name: `Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::TryReadSessionTokenFromCache`
- size: `286`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x3bb0`

## callees

- `0x59f0`
- `0x5b10`
- `0x5b40`
- `0x14f10`
- `0x22ae0`
- `0x22b00`
- `0x258a0`

## string_xrefs

- `0x59f3`: `token`
- `0x5a2f`: `Use the SPUtility to load the site subscription from URI.`
- `0x5a80`: `Reading token from Cache using cacheKey claim value`
- `0x5abd`: `SPApplicationAuthenticationModule.TryReadSessionTokenFromCache() couldn't find cacheKey claim. This is normal if this is a guest user.`
- `0x5ad4`: `Reading token from Cache using token signature`

## pseudocode

```c

```

## disassembly

```asm
0x59f0  ldarg.1
0x59f1  brtrue.s loc_59FE
0x59f3  ldstr    aToken// "token"
0x59f8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x59fd  throw
0x59fe  ldarg.2
0x59ff  ldnull
0x5a00  stind.ref
0x5a01  call     class Microsoft.SharePoint.IdentityModel.SPTokenCache Microsoft.SharePoint.IdentityModel.SPTokenCache::get_Current()
0x5a06  stloc.0
0x5a07  ldloc.0
0x5a08  brtrue.s loc_5A0C
0x5a0a  ldc.i4.0
0x5a0b  ret
0x5a0c  ldsfld   string [mscorlib]System.String::Empty
0x5a11  stloc.1
0x5a12  ldstr    aGettingSiteSub// "Getting Site Subscription Id"
0x5a17  ldc.i4.s 0x32
0x5a19  ldc.i4.0
0x5a1a  newarr   [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x5a1f  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.TraceSeverity, class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[])
0x5a24  stloc.3
0x5a25  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::UseUtilityLoadForSiteSubscription
0x5a2a  ldstr    a7242017// "7/24/2017"
0x5a2f  ldstr    aUseTheSputilit// "Use the SPUtility to load the site subs"...
0x5a34  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid, string, string)
0x5a39  brfalse.s loc_5A4D
0x5a3b  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAlternateUrl::get_ContextUri()
0x5a40  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x5a45  call     string Microsoft.SharePoint.IdentityModel.SPTokenCache::GetSubscriptionIdFromContext(string context)
0x5a4a  stloc.1
0x5a4b  br.s     loc_5A5D
0x5a4d  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAlternateUrl::get_ContextUri()
0x5a52  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x5a57  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::GetSubscriptionIdFromContext(string)
0x5a5c  stloc.1
0x5a5d  leave.s  loc_5A69
0x5a5f  ldloc.3
0x5a60  brfalse.s loc_5A68
0x5a62  ldloc.3
0x5a63  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5a68  endfinally
0x5a69  ldarg.1
0x5a6a  call     bool Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::IsLoopbackToken(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken token)
0x5a6f  brfalse.s loc_5ACD
0x5a71  ldarg.1
0x5a72  call     string Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::GetCacheKeyFromClaim(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken token)
0x5a77  stloc.2
0x5a78  ldloc.2
0x5a79  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5a7e  brtrue.s loc_5AB1
0x5a80  ldstr    aReadingTokenFr// "Reading token from Cache using cacheKey"...
0x5a85  ldc.i4.s 0x32
0x5a87  ldc.i4.0
0x5a88  newarr   [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x5a8d  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.TraceSeverity, class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[])
0x5a92  stloc.s  4
0x5a94  ldarg.2
0x5a95  ldloc.0
0x5a96  ldloc.1
0x5a97  ldloc.2
0x5a98  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken Microsoft.SharePoint.IdentityModel.SPTokenCache::TryGetCachedToken(string subscriptionId, string identity)
0x5a9d  isinst   [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken
0x5aa2  stind.ref
0x5aa3  leave.s  loc_5AC7
0x5aa5  ldloc.s  4
0x5aa7  brfalse.s loc_5AB0
0x5aa9  ldloc.s  4
0x5aab  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5ab0  endfinally
0x5ab1  ldc.i4   0x2563E1
0x5ab6  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x5abb  ldc.i4.s 0x32
0x5abd  ldstr    aSpapplicationa_82// "SPApplicationAuthenticationModule.TryRe"...
0x5ac2  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x5ac7  ldarg.2
0x5ac8  ldind.ref
0x5ac9  brfalse.s loc_5ACD
0x5acb  ldc.i4.1
0x5acc  ret
0x5acd  ldarg.1
0x5ace  call     string Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::GetCacheKeyFromTokenSignature(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken token)
0x5ad3  stloc.2
0x5ad4  ldstr    aReadingTokenFr_0// "Reading token from Cache using token si"...
0x5ad9  ldc.i4.s 0x32
0x5adb  ldc.i4.0
0x5adc  newarr   [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x5ae1  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.TraceSeverity, class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[])
0x5ae6  stloc.s  5
0x5ae8  ldarg.2
0x5ae9  ldloc.0
0x5aea  ldloc.1
0x5aeb  ldloc.2
0x5aec  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken Microsoft.SharePoint.IdentityModel.SPTokenCache::TryGetCachedToken(string subscriptionId, string identity)
0x5af1  isinst   [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken
0x5af6  stind.ref
0x5af7  leave.s  loc_5B05
0x5af9  ldloc.s  5
0x5afb  brfalse.s loc_5B04
0x5afd  ldloc.s  5
0x5aff  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5b04  endfinally
0x5b05  ldnull
0x5b06  ldarg.2
0x5b07  ldind.ref
0x5b08  ceq
0x5b0a  ldc.i4.0
0x5b0b  ceq
0x5b0d  ret
```
