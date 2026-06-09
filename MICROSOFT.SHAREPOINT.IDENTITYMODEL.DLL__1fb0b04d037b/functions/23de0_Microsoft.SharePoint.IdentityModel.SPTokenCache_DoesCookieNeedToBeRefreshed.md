# Microsoft.SharePoint.IdentityModel.SPTokenCache::DoesCookieNeedToBeRefreshed

- ea: `0x23de0`
- end: `0x23f0e`
- name: `Microsoft.SharePoint.IdentityModel.SPTokenCache::DoesCookieNeedToBeRefreshed`
- size: `302`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x24080`
- `0x24a40`

## callees

- `0x20720`
- `0x21b70`
- `0x21bd0`
- `0x23950`
- `0x23de0`
- `0x23f10`

## string_xrefs

- `0x23e16`: `Token Cache: CookieValue is null.`
- `0x23df1`: `Token Cache: RequestData is null.`
- `0x23e3b`: `Token Cache: CachedSessionToken is null.`
- `0x23e61`: `Token Cache: Request is excluded from cookie refresh.`
- `0x23eaa`: `Token Cache: Cookie does not need to be refreshed. CookieExpires: '{0}'.`
- `0x23ee2`: `Token Cache: Cookie needs to be refreshed. CookieExpires: '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0x23de0  ldc.i4.0
0x23de1  stloc.0
0x23de2  ldarg.1
0x23de3  brtrue.s loc_23E02
0x23de5  ldc.i4   0x5E3454
0x23dea  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x23def  ldc.i4.s 0xA
0x23df1  ldstr    aTokenCacheRequ_2// "Token Cache: RequestData is null."
0x23df6  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x23dfb  ldc.i4.0
0x23dfc  stloc.0
0x23dfd  br       loc_23F0C
0x23e02  ldarg.1
0x23e03  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x23e08  brtrue.s loc_23E27
0x23e0a  ldc.i4   0x5E3455
0x23e0f  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x23e14  ldc.i4.s 0xA
0x23e16  ldstr    aTokenCacheCook_5// "Token Cache: CookieValue is null."
0x23e1b  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x23e20  ldc.i4.0
0x23e21  stloc.0
0x23e22  br       loc_23F0C
0x23e27  ldarg.1
0x23e28  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CachedSessionToken()
0x23e2d  brtrue.s loc_23E4C
0x23e2f  ldc.i4   0x5E3456
0x23e34  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x23e39  ldc.i4.s 0xA
0x23e3b  ldstr    aTokenCacheCach// "Token Cache: CachedSessionToken is null"...
0x23e40  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x23e45  ldc.i4.0
0x23e46  stloc.0
0x23e47  br       loc_23F0C
0x23e4c  ldarg.0
0x23e4d  ldarg.1
0x23e4e  callvirt instance bool Microsoft.SharePoint.IdentityModel.SPTokenCache::IsRequestExcludedFromCookieRefresh(class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData requestData)
0x23e53  brfalse.s loc_23E72
0x23e55  ldc.i4   0x5E3457
0x23e5a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x23e5f  ldc.i4.s 0x32
0x23e61  ldstr    aTokenCacheRequ_4// "Token Cache: Request is excluded from c"...
0x23e66  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x23e6b  ldc.i4.0
0x23e6c  stloc.0
0x23e6d  br       loc_23F0C
0x23e72  ldarg.0
0x23e73  ldarg.1
0x23e74  callvirt instance int64 Microsoft.SharePoint.IdentityModel.SPTokenCache::GetCookieRefreshWindow(class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData requestData)
0x23e79  stloc.1
0x23e7a  ldarg.1
0x23e7b  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x23e80  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_Expires()
0x23e85  stloc.2
0x23e86  ldloca.s 2
0x23e88  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x23e8d  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x23e92  stloc.3
0x23e93  ldloca.s 3
0x23e95  call     instance int64 [mscorlib]System.DateTime::get_Ticks()
0x23e9a  sub
0x23e9b  ldloc.1
0x23e9c  blt.s    loc_23ED6
0x23e9e  ldc.i4   0x5E3458
0x23ea3  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x23ea8  ldc.i4.s 0x32
0x23eaa  ldstr    aTokenCacheCook_7// "Token Cache: Cookie does not need to be"...
0x23eaf  ldc.i4.1
0x23eb0  newarr   [mscorlib]System.Object
0x23eb5  stloc.s  4
0x23eb7  ldloc.s  4
0x23eb9  ldc.i4.0
0x23eba  ldarg.1
0x23ebb  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x23ec0  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_Expires()
0x23ec5  box      [mscorlib]System.DateTime
0x23eca  stelem.ref
0x23ecb  ldloc.s  4
0x23ecd  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x23ed2  ldc.i4.0
0x23ed3  stloc.0
0x23ed4  br.s     loc_23F0C
0x23ed6  ldc.i4   0x5E3459
0x23edb  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x23ee0  ldc.i4.s 0x32
0x23ee2  ldstr    aTokenCacheCook_8// "Token Cache: Cookie needs to be refresh"...
0x23ee7  ldc.i4.1
0x23ee8  newarr   [mscorlib]System.Object
0x23eed  stloc.s  5
0x23eef  ldloc.s  5
0x23ef1  ldc.i4.0
0x23ef2  ldarg.1
0x23ef3  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x23ef8  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_Expires()
0x23efd  box      [mscorlib]System.DateTime
0x23f02  stelem.ref
0x23f03  ldloc.s  5
0x23f05  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x23f0a  ldc.i4.1
0x23f0b  stloc.0
0x23f0c  ldloc.0
0x23f0d  ret
```
