# Microsoft.SharePoint.IdentityModel.SPTokenCache::AddCachedTokenV2

- ea: `0x25bc0`
- end: `0x25d39`
- name: `Microsoft.SharePoint.IdentityModel.SPTokenCache::AddCachedTokenV2`
- size: `377`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x25a90`

## callees

- `0x25bc0`
- `0x26030`
- `0x26040`
- `0x26050`
- `0x26130`
- `0x264f0`
- `0x26700`

## string_xrefs

- `0x25c48`: `Token Cache: Added token to distributed cache.`
- `0x25c5f`: `Token Cache: Failed to add token from distributed cache. Key: '{0}'.(This is expected during the process warm up or if data cache Initialization is getting done by some other thread).`
- `0x25c81`: `Token Cache: Reverting to local cache to Add the token. Key: '{0}'.`
- `0x25ce8`: `Token Cache: Reverting to local cache to Add the token. Key: '{0}'.`
- `0x25cb9`: `Token Cache: Failed to add token from distributed cache. Key: '{0}', Exception: '{1}'.`
- `0x25d20`: `Token Cache: Added token to local cache.`

## pseudocode

```c

```

## disassembly

```asm
0x25bc0  ldc.i4.1
0x25bc1  stloc.0
0x25bc2  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm::get_Local()
0x25bc7  callvirt instance class [System]System.Collections.Generic.ISet`1<int32> [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm::get_ServerDebugFlags()
0x25bcc  ldc.i4   0xCB31
0x25bd1  callvirt instance bool class [mscorlib]System.Collections.Generic.ICollection`1<int32>::Contains(var<u1>)
0x25bd6  brtrue.s loc_25C22
0x25bd8  ldarg.2
0x25bd9  brfalse.s loc_25C22
0x25bdb  ldarg.2
0x25bdc  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry::get_SessionToken()
0x25be1  brfalse.s loc_25C22
0x25be3  ldarg.2
0x25be4  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry::get_SessionToken()
0x25be9  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken::get_ClaimsPrincipal()
0x25bee  brfalse.s loc_25C22
0x25bf0  ldarg.2
0x25bf1  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry::get_SessionToken()
0x25bf6  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken::get_ClaimsPrincipal()
0x25bfb  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0x25c00  brfalse.s loc_25C22
0x25c02  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x25c07  ldarg.2
0x25c08  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry::get_SessionToken()
0x25c0d  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken::get_ClaimsPrincipal()
0x25c12  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0x25c17  callvirt instance string [mscorlib]System.Security.Principal.IIdentity::get_Name()
0x25c1c  call     bool Microsoft.SharePoint.IdentityModel.SPTokenCache::IsRealUser(class [System.Web]System.Web.HttpContext context, string userLogin)
0x25c21  stloc.0
0x25c22  ldsfld   string [mscorlib]System.String::Empty
0x25c27  stloc.1
0x25c28  call     bool Microsoft.SharePoint.IdentityModel.SPTokenCache::get_UseDistributedCache()
0x25c2d  brfalse  loc_25D10
0x25c32  ldsfld   bool Microsoft.SharePoint.IdentityModel.SPDistributedSecurityTokenCacheInitializer::IsInitialized
0x25c37  brfalse.s loc_25C50
0x25c39  ldarg.0
0x25c3a  call     instance class Microsoft.SharePoint.IdentityModel.SPDistributedSecurityTokenCache Microsoft.SharePoint.IdentityModel.SPTokenCache::get_DistributedTokenCache()
0x25c3f  ldarg.1
0x25c40  ldarg.2
0x25c41  ldloc.0
0x25c42  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.DistributedCaching.SPDataCacheItemVersion Microsoft.SharePoint.IdentityModel.SPDistributedSecurityTokenCache::PutV2(string key, object value, bool isRealUser)
0x25c47  pop
0x25c48  ldstr    aTokenCacheAdde// "Token Cache: Added token to distributed"...
0x25c4d  stloc.1
0x25c4e  br.s     loc_25CA7
0x25c50  ldloc.0
0x25c51  brfalse.s loc_25CA7
0x25c53  ldc.i4   0x1017856
0x25c58  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DistributedCache()
0x25c5d  ldc.i4.s 0xF
0x25c5f  ldstr    aTokenCacheFail_9// "Token Cache: Failed to add token from d"...
0x25c64  ldc.i4.1
0x25c65  newarr   [mscorlib]System.Object
0x25c6a  stloc.3
0x25c6b  ldloc.3
0x25c6c  ldc.i4.0
0x25c6d  ldarg.1
0x25c6e  stelem.ref
0x25c6f  ldloc.3
0x25c70  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x25c75  ldc.i4   0x1017857
0x25c7a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DistributedCache()
0x25c7f  ldc.i4.s 0xF
0x25c81  ldstr    aTokenCacheReve// "Token Cache: Reverting to local cache t"...
0x25c86  ldc.i4.1
0x25c87  newarr   [mscorlib]System.Object
0x25c8c  stloc.s  4
0x25c8e  ldloc.s  4
0x25c90  ldc.i4.0
0x25c91  ldarg.1
0x25c92  stelem.ref
0x25c93  ldloc.s  4
0x25c95  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x25c9a  ldarg.0
0x25c9b  call     instance class Microsoft.SharePoint.IdentityModel.SPWfeSecurityTokenCache Microsoft.SharePoint.IdentityModel.SPTokenCache::get_WFETokenCache()
0x25ca0  ldarg.1
0x25ca1  ldarg.2
0x25ca2  callvirt instance void Microsoft.SharePoint.IdentityModel.SPWfeSecurityTokenCache::Add(string key, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry token)
0x25ca7  leave.s  loc_25D26
0x25ca9  stloc.2
0x25caa  ldloc.0
0x25cab  brfalse.s loc_25D0E
0x25cad  ldc.i4   0x1017858
0x25cb2  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DistributedCache()
0x25cb7  ldc.i4.s 0x32
0x25cb9  ldstr    aTokenCacheFail_10// "Token Cache: Failed to add token from d"...
0x25cbe  ldc.i4.2
0x25cbf  newarr   [mscorlib]System.Object
0x25cc4  stloc.s  5
0x25cc6  ldloc.s  5
0x25cc8  ldc.i4.0
0x25cc9  ldarg.1
0x25cca  stelem.ref
0x25ccb  ldloc.s  5
0x25ccd  ldc.i4.1
0x25cce  ldloc.2
0x25ccf  callvirt instance string [mscorlib]System.Object::ToString()
0x25cd4  stelem.ref
0x25cd5  ldloc.s  5
0x25cd7  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x25cdc  ldc.i4   0x1017859
0x25ce1  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DistributedCache()
0x25ce6  ldc.i4.s 0x32
0x25ce8  ldstr    aTokenCacheReve// "Token Cache: Reverting to local cache t"...
0x25ced  ldc.i4.1
0x25cee  newarr   [mscorlib]System.Object
0x25cf3  stloc.s  6
0x25cf5  ldloc.s  6
0x25cf7  ldc.i4.0
0x25cf8  ldarg.1
0x25cf9  stelem.ref
0x25cfa  ldloc.s  6
0x25cfc  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x25d01  ldarg.0
0x25d02  call     instance class Microsoft.SharePoint.IdentityModel.SPWfeSecurityTokenCache Microsoft.SharePoint.IdentityModel.SPTokenCache::get_WFETokenCache()
0x25d07  ldarg.1
0x25d08  ldarg.2
0x25d09  callvirt instance void Microsoft.SharePoint.IdentityModel.SPWfeSecurityTokenCache::Add(string key, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry token)
0x25d0e  leave.s  loc_25D26
0x25d10  ldloc.0
0x25d11  brfalse.s loc_25D26
0x25d13  ldarg.0
0x25d14  call     instance class Microsoft.SharePoint.IdentityModel.SPWfeSecurityTokenCache Microsoft.SharePoint.IdentityModel.SPTokenCache::get_WFETokenCache()
0x25d19  ldarg.1
0x25d1a  ldarg.2
0x25d1b  callvirt instance void Microsoft.SharePoint.IdentityModel.SPWfeSecurityTokenCache::Add(string key, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry token)
0x25d20  ldstr    aTokenCacheAdde_0// "Token Cache: Added token to local cache"...
0x25d25  stloc.1
0x25d26  ldc.i4   0x101785A
0x25d2b  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x25d30  ldc.i4.s 0x64
0x25d32  ldloc.1
0x25d33  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x25d38  ret
```
