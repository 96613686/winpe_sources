# Microsoft.SharePoint.IdentityModel.SPTokenCache::DoesTokenNeedToBeRefreshed

- ea: `0x24080`
- end: `0x241ab`
- name: `Microsoft.SharePoint.IdentityModel.SPTokenCache::DoesTokenNeedToBeRefreshed`
- size: `299`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x24c50`

## callees

- `0x21b70`
- `0x21bd0`
- `0x239e0`
- `0x23ca0`
- `0x23de0`
- `0x24080`

## string_xrefs

- `0x240b6`: `Token Cache: CookieValue is null.`
- `0x24091`: `Token Cache: RequestData is null.`
- `0x240db`: `Token Cache: CachedSessionToken is null.`
- `0x24101`: `Token Cache: Request is excluded from token refresh.`
- `0x24124`: `Token Cache: Token will not be refreshed because cookie does not needs to be refreshed.`
- `0x24152`: `Token Cache: Token and cookie are consistent so declining to refresh token.`
- `0x2416c`: `Token Cache: Token and cookie are NOT consitent so forcing token refresh.`
- `0x24187`: `Token Cache: Token needs a refresh.`
- `0x2419f`: `Token Cache: Token does NOT need a refresh.`

## pseudocode

```c

```

## disassembly

```asm
0x24080  ldc.i4.0
0x24081  stloc.0
0x24082  ldarg.1
0x24083  brtrue.s loc_240A2
0x24085  ldc.i4   0x5E345A
0x2408a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x2408f  ldc.i4.s 0xA
0x24091  ldstr    aTokenCacheRequ_2// "Token Cache: RequestData is null."
0x24096  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x2409b  ldc.i4.0
0x2409c  stloc.0
0x2409d  br       loc_24178
0x240a2  ldarg.1
0x240a3  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x240a8  brtrue.s loc_240C7
0x240aa  ldc.i4   0x5E345B
0x240af  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x240b4  ldc.i4.s 0xA
0x240b6  ldstr    aTokenCacheCook_5// "Token Cache: CookieValue is null."
0x240bb  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x240c0  ldc.i4.0
0x240c1  stloc.0
0x240c2  br       loc_24178
0x240c7  ldarg.1
0x240c8  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CachedSessionToken()
0x240cd  brtrue.s loc_240EC
0x240cf  ldc.i4   0x5E345C
0x240d4  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x240d9  ldc.i4.s 0xA
0x240db  ldstr    aTokenCacheCach// "Token Cache: CachedSessionToken is null"...
0x240e0  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x240e5  ldc.i4.0
0x240e6  stloc.0
0x240e7  br       loc_24178
0x240ec  ldarg.0
0x240ed  ldarg.1
0x240ee  callvirt instance bool Microsoft.SharePoint.IdentityModel.SPTokenCache::IsRequestExcludedFromTokenRefresh(class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData requestData)
0x240f3  brfalse.s loc_2410F
0x240f5  ldc.i4   0x5E345D
0x240fa  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x240ff  ldc.i4.s 0x32
0x24101  ldstr    aTokenCacheRequ_5// "Token Cache: Request is excluded from t"...
0x24106  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x2410b  ldc.i4.0
0x2410c  stloc.0
0x2410d  br.s     loc_24178
0x2410f  ldarg.0
0x24110  ldarg.1
0x24111  callvirt instance bool Microsoft.SharePoint.IdentityModel.SPTokenCache::DoesCookieNeedToBeRefreshed(class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData requestData)
0x24116  brtrue.s loc_24132
0x24118  ldc.i4   0x5E345E
0x2411d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x24122  ldc.i4.s 0x32
0x24124  ldstr    aTokenCacheToke_1// "Token Cache: Token will not be refreshe"...
0x24129  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x2412e  ldc.i4.0
0x2412f  stloc.0
0x24130  br.s     loc_24178
0x24132  ldarg.0
0x24133  ldarg.1
0x24134  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x24139  ldarg.1
0x2413a  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CachedSessionToken()
0x2413f  callvirt instance bool Microsoft.SharePoint.IdentityModel.SPTokenCache::AreTokenAndCookieConsistentForWrite(class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue cookieValue, class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken sessionToken)
0x24144  brfalse.s loc_24160
0x24146  ldc.i4   0x5E345F
0x2414b  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x24150  ldc.i4.s 0x32
0x24152  ldstr    aTokenCacheToke_2// "Token Cache: Token and cookie are consi"...
0x24157  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x2415c  ldc.i4.0
0x2415d  stloc.0
0x2415e  br.s     loc_24178
0x24160  ldc.i4   0x5E3460
0x24165  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x2416a  ldc.i4.s 0x32
0x2416c  ldstr    aTokenCacheToke_3// "Token Cache: Token and cookie are NOT c"...
0x24171  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x24176  ldc.i4.1
0x24177  stloc.0
0x24178  ldloc.0
0x24179  brfalse.s loc_24193
0x2417b  ldc.i4   0x5E3461
0x24180  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x24185  ldc.i4.s 0x32
0x24187  ldstr    aTokenCacheToke_4// "Token Cache: Token needs a refresh."
0x2418c  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x24191  br.s     loc_241A9
0x24193  ldc.i4   0x5E3462
0x24198  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x2419d  ldc.i4.s 0x32
0x2419f  ldstr    aTokenCacheToke_5// "Token Cache: Token does NOT need a refr"...
0x241a4  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x241a9  ldloc.0
0x241aa  ret
```
