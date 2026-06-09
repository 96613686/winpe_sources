# Microsoft.SharePoint.IdentityModel.SPTokenCache::DoesCookieNeedToBeRewritten

- ea: `0x23d50`
- end: `0x23dda`
- name: `Microsoft.SharePoint.IdentityModel.SPTokenCache::DoesCookieNeedToBeRewritten`
- size: `138`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x24a40`

## callees

- `0x21b70`
- `0x21bd0`
- `0x238c0`
- `0x23d50`

## string_xrefs

- `0x23d83`: `Token Cache: CookieValue is null.`
- `0x23d61`: `Token Cache: RequestData is null.`
- `0x23da5`: `Token Cache: CachedSessionToken is null.`
- `0x23dc8`: `Token Cache: Request is excluded from cookie rewrite.`

## pseudocode

```c

```

## disassembly

```asm
0x23d50  ldc.i4.0
0x23d51  stloc.0
0x23d52  ldarg.1
0x23d53  brtrue.s loc_23D6F
0x23d55  ldc.i4   0x5E3450
0x23d5a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x23d5f  ldc.i4.s 0xA
0x23d61  ldstr    aTokenCacheRequ_2// "Token Cache: RequestData is null."
0x23d66  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x23d6b  ldc.i4.0
0x23d6c  stloc.0
0x23d6d  br.s     loc_23DD8
0x23d6f  ldarg.1
0x23d70  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x23d75  brtrue.s loc_23D91
0x23d77  ldc.i4   0x5E3451
0x23d7c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x23d81  ldc.i4.s 0xA
0x23d83  ldstr    aTokenCacheCook_5// "Token Cache: CookieValue is null."
0x23d88  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x23d8d  ldc.i4.0
0x23d8e  stloc.0
0x23d8f  br.s     loc_23DD8
0x23d91  ldarg.1
0x23d92  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CachedSessionToken()
0x23d97  brtrue.s loc_23DB3
0x23d99  ldc.i4   0x5E3452
0x23d9e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x23da3  ldc.i4.s 0xA
0x23da5  ldstr    aTokenCacheCach// "Token Cache: CachedSessionToken is null"...
0x23daa  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x23daf  ldc.i4.0
0x23db0  stloc.0
0x23db1  br.s     loc_23DD8
0x23db3  ldarg.0
0x23db4  ldarg.1
0x23db5  callvirt instance bool Microsoft.SharePoint.IdentityModel.SPTokenCache::IsRequestExcludedFromCookieRewrite(class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData requestData)
0x23dba  brfalse.s loc_23DD6
0x23dbc  ldc.i4   0x5E3453
0x23dc1  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x23dc6  ldc.i4.s 0x32
0x23dc8  ldstr    aTokenCacheRequ_3// "Token Cache: Request is excluded from c"...
0x23dcd  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x23dd2  ldc.i4.0
0x23dd3  stloc.0
0x23dd4  br.s     loc_23DD8
0x23dd6  ldc.i4.1
0x23dd7  stloc.0
0x23dd8  ldloc.0
0x23dd9  ret
```
