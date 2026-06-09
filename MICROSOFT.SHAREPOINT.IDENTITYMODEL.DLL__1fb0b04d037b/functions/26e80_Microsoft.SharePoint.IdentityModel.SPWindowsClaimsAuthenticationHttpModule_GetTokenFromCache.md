# Microsoft.SharePoint.IdentityModel.SPWindowsClaimsAuthenticationHttpModule::GetTokenFromCache

- ea: `0x26e80`
- end: `0x26fc5`
- name: `Microsoft.SharePoint.IdentityModel.SPWindowsClaimsAuthenticationHttpModule::GetTokenFromCache`
- size: `325`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x26910`

## callees

- `0x22ae0`
- `0x22b00`
- `0x22c40`
- `0x258a0`
- `0x26e80`

## string_xrefs

- `0x26f11`: `Use the SPUtility to load the site subscription from URI.`
- `0x26e91`: `windowsIdentity`
- `0x26eb3`: `SessionSecurityTokenHandler is missing for request url '{0}'.`
- `0x26f64`: `Claims Windows Sign-In: User '{0}' for request url '{1}' does not have a cached SessionSecurityToken.`
- `0x26f9c`: `Claims Windows Sign-In: User '{0}' for request url '{1}' has cached SessionSecurityToken for request url '{1}'.`

## pseudocode

```c

```

## disassembly

```asm
0x26e80  ldarg.1
0x26e81  brtrue.s loc_26E8E
0x26e83  ldstr    aContext_0// "context"
0x26e88  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x26e8d  throw
0x26e8e  ldarg.2
0x26e8f  brtrue.s loc_26E9C
0x26e91  ldstr    aWindowsidentit// "windowsIdentity"
0x26e96  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x26e9b  throw
0x26e9c  ldnull
0x26e9d  stloc.0
0x26e9e  call     class Microsoft.SharePoint.IdentityModel.SPTokenCache Microsoft.SharePoint.IdentityModel.SPTokenCache::get_Current()
0x26ea3  stloc.1
0x26ea4  ldloc.1
0x26ea5  brtrue.s loc_26ED5
0x26ea7  ldc.i4   0x15D693
0x26eac  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x26eb1  ldc.i4.s 0xA
0x26eb3  ldstr    aSessionsecurit_0// "SessionSecurityTokenHandler is missing "...
0x26eb8  ldc.i4.1
0x26eb9  newarr   [mscorlib]System.Object
0x26ebe  stloc.s  5
0x26ec0  ldloc.s  5
0x26ec2  ldc.i4.0
0x26ec3  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAlternateUrl::get_ContextUri()
0x26ec8  stelem.ref
0x26ec9  ldloc.s  5
0x26ecb  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x26ed0  br       loc_26FC3
0x26ed5  ldarg.2
0x26ed6  callvirt instance class [mscorlib]System.Security.Principal.SecurityIdentifier [mscorlib]System.Security.Principal.WindowsIdentity::get_User()
0x26edb  callvirt instance string [mscorlib]System.Security.Principal.IdentityReference::get_Value()
0x26ee0  stloc.2
0x26ee1  ldloc.2
0x26ee2  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPActiveDirectoryClaimProvider::CreateUserKeyClaim(string)
0x26ee7  stloc.3
0x26ee8  ldloc.3
0x26ee9  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaim::get_ClaimType()
0x26eee  ldloc.3
0x26eef  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaim::get_Value()
0x26ef4  ldloc.3
0x26ef5  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaim::get_ValueType()
0x26efa  ldloc.3
0x26efb  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaim::get_OriginalIssuer()
0x26f00  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimEncodingManager::EncodeClaimIntoFormsSuffix(string, string, string, string)
0x26f05  stloc.s  4
0x26f07  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.IdentityModel.SPWindowsClaimsAuthenticationHttpModule::UseUtilityLoadForSiteSubscription
0x26f0c  ldstr    a7242017// "7/24/2017"
0x26f11  ldstr    aUseTheSputilit// "Use the SPUtility to load the site subs"...
0x26f16  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid, string, string)
0x26f1b  brfalse.s loc_26F3C
0x26f1d  ldloc.1
0x26f1e  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAlternateUrl::get_ContextUri()
0x26f23  callvirt instance string [System]System.Uri::get_AbsoluteUri()
0x26f28  call     string Microsoft.SharePoint.IdentityModel.SPTokenCache::GetSubscriptionIdFromContext(string context)
0x26f2d  ldloc.s  4
0x26f2f  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken Microsoft.SharePoint.IdentityModel.SPTokenCache::TryGetCachedToken(string subscriptionId, string identity)
0x26f34  isinst   [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken
0x26f39  stloc.0
0x26f3a  br.s     loc_26F55
0x26f3c  ldloc.1
0x26f3d  ldloc.1
0x26f3e  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAlternateUrl::get_ContextUri()
0x26f43  callvirt instance string Microsoft.SharePoint.IdentityModel.SPTokenCache::GetSiteSubscriptionIdFromUri(class [System]System.Uri context)
0x26f48  ldloc.s  4
0x26f4a  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken Microsoft.SharePoint.IdentityModel.SPTokenCache::TryGetCachedToken(string subscriptionId, string identity)
0x26f4f  isinst   [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken
0x26f54  stloc.0
0x26f55  ldloc.0
0x26f56  brtrue.s loc_26F8D
0x26f58  ldc.i4   0x15D694
0x26f5d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x26f62  ldc.i4.s 0x64
0x26f64  ldstr    aClaimsWindowsS_1// "Claims Windows Sign-In: User '{0}' for "...
0x26f69  ldc.i4.2
0x26f6a  newarr   [mscorlib]System.Object
0x26f6f  stloc.s  6
0x26f71  ldloc.s  6
0x26f73  ldc.i4.0
0x26f74  ldarg.2
0x26f75  callvirt instance string [mscorlib]System.Security.Claims.ClaimsIdentity::get_Name()
0x26f7a  stelem.ref
0x26f7b  ldloc.s  6
0x26f7d  ldc.i4.1
0x26f7e  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAlternateUrl::get_ContextUri()
0x26f83  stelem.ref
0x26f84  ldloc.s  6
0x26f86  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x26f8b  br.s     loc_26FC3
0x26f8d  ldc.i4   0x15D695
0x26f92  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x26f97  ldc.i4   0xC8
0x26f9c  ldstr    aClaimsWindowsS_2// "Claims Windows Sign-In: User '{0}' for "...
0x26fa1  ldc.i4.2
0x26fa2  newarr   [mscorlib]System.Object
0x26fa7  stloc.s  7
0x26fa9  ldloc.s  7
0x26fab  ldc.i4.0
0x26fac  ldarg.2
0x26fad  callvirt instance string [mscorlib]System.Security.Claims.ClaimsIdentity::get_Name()
0x26fb2  stelem.ref
0x26fb3  ldloc.s  7
0x26fb5  ldc.i4.1
0x26fb6  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAlternateUrl::get_ContextUri()
0x26fbb  stelem.ref
0x26fbc  ldloc.s  7
0x26fbe  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x26fc3  ldloc.0
0x26fc4  ret
```
