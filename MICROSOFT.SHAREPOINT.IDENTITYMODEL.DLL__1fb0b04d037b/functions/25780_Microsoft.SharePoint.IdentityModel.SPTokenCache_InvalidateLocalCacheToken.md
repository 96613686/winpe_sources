# Microsoft.SharePoint.IdentityModel.SPTokenCache::InvalidateLocalCacheToken

- ea: `0x25780`
- end: `0x2581a`
- name: `Microsoft.SharePoint.IdentityModel.SPTokenCache::InvalidateLocalCacheToken`
- size: `154`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x25690`

## callees

- `0x22ad0`
- `0x25780`
- `0x26040`
- `0x26690`
- `0x26700`

## string_xrefs

- `0x2579e`: `cacheKey`
- `0x25794`: `InvalidateLocalCacheToken: Invalid cacheKey.`
- `0x257c7`: `Did not find an entry in local cache with key. Key: '{0}'.`
- `0x257ea`: `Invalidating local cache for entry. Key: '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0x25780  ldarg.1
0x25781  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x25786  brfalse.s loc_257A9
0x25788  ldc.i4   0x894710
0x2578d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x25792  ldc.i4.s 0xA
0x25794  ldstr    aInvalidateloca// "InvalidateLocalCacheToken: Invalid cach"...
0x25799  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x2579e  ldstr    aCachekey_0// "cacheKey"
0x257a3  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x257a8  throw
0x257a9  ldarg.0
0x257aa  call     instance class Microsoft.SharePoint.IdentityModel.SPWfeSecurityTokenCache Microsoft.SharePoint.IdentityModel.SPTokenCache::get_WFETokenCache()
0x257af  ldarg.1
0x257b0  ldloca.s 0
0x257b2  callvirt instance object Microsoft.SharePoint.IdentityModel.SPWfeSecurityTokenCache::TryGetValue(string key, [out] class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry& result)
0x257b7  pop
0x257b8  ldloc.0
0x257b9  brtrue.s loc_257DE
0x257bb  ldc.i4   0x894711
0x257c0  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x257c5  ldc.i4.s 0x32
0x257c7  ldstr    aDidNotFindAnEn_0// "Did not find an entry in local cache wi"...
0x257cc  ldc.i4.1
0x257cd  newarr   [mscorlib]System.Object
0x257d2  stloc.2
0x257d3  ldloc.2
0x257d4  ldc.i4.0
0x257d5  ldarg.1
0x257d6  stelem.ref
0x257d7  ldloc.2
0x257d8  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x257dd  ret
0x257de  ldc.i4   0x894712
0x257e3  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x257e8  ldc.i4.s 0x14
0x257ea  ldstr    aInvalidatingLo// "Invalidating local cache for entry. Key"...
0x257ef  ldc.i4.1
0x257f0  newarr   [mscorlib]System.Object
0x257f5  stloc.3
0x257f6  ldloc.3
0x257f7  ldc.i4.0
0x257f8  ldarg.1
0x257f9  stelem.ref
0x257fa  ldloc.3
0x257fb  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x25800  ldarg.0
0x25801  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken Microsoft.SharePoint.IdentityModel.SPTokenCache::get_AnonymousSessionSecurityToken()
0x25806  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry::.ctor(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken)
0x2580b  stloc.1
0x2580c  ldarg.0
0x2580d  call     instance class Microsoft.SharePoint.IdentityModel.SPWfeSecurityTokenCache Microsoft.SharePoint.IdentityModel.SPTokenCache::get_WFETokenCache()
0x25812  ldarg.1
0x25813  ldloc.1
0x25814  callvirt instance void Microsoft.SharePoint.IdentityModel.SPWfeSecurityTokenCache::Add(string key, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTokenCacheEntry token)
0x25819  ret
```
