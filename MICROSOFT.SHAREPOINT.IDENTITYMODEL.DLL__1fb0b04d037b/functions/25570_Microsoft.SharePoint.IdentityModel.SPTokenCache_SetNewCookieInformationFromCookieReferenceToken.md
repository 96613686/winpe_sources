# Microsoft.SharePoint.IdentityModel.SPTokenCache::SetNewCookieInformationFromCookieReferenceToken

- ea: `0x25570`
- end: `0x25672`
- name: `Microsoft.SharePoint.IdentityModel.SPTokenCache::SetNewCookieInformationFromCookieReferenceToken`
- size: `258`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x21b70`
- `0x21ca0`
- `0x21cc0`
- `0x21ce0`
- `0x22da0`
- `0x22f40`
- `0x253c0`
- `0x25570`

## string_xrefs

- `0x2559a`: `Token Cache: RequestData is null`
- `0x255bf`: `Token Cache: Current cookie value is null`
- `0x255df`: `Token Cache: The cookie token is null`
- `0x25605`: `Token Cache: The cookie token is not a cookie token`
- `0x2562d`: `Token Cache: New cookie string couldn't be obtained from the cookie token request`
- `0x25664`: `Token Cache: New cookie value obtained.`

## pseudocode

```c

```

## disassembly

```asm
0x25570  ldc.i4.0
0x25571  stloc.0
0x25572  ldnull
0x25573  stloc.1
0x25574  ldnull
0x25575  stloc.2
0x25576  ldarg.1
0x25577  ldnull
0x25578  callvirt instance void Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::set_NewCookieString(string value)
0x2557d  ldarg.1
0x2557e  ldnull
0x2557f  callvirt instance void Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::set_NewCookieBinaryData(unsigned int8[] value)
0x25584  ldarg.1
0x25585  ldnull
0x25586  callvirt instance void Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::set_NewCookieValue(class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue value)
0x2558b  ldarg.1
0x2558c  brtrue.s loc_255AB
0x2558e  ldc.i4   0x1192360
0x25593  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x25598  ldc.i4.s 0xA
0x2559a  ldstr    aTokenCacheRequ_6// "Token Cache: RequestData is null"
0x2559f  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x255a4  ldc.i4.0
0x255a5  stloc.0
0x255a6  br       loc_25670
0x255ab  ldarg.1
0x255ac  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x255b1  brtrue.s loc_255D0
0x255b3  ldc.i4   0x1192361
0x255b8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x255bd  ldc.i4.s 0xA
0x255bf  ldstr    aTokenCacheCurr_0// "Token Cache: Current cookie value is nu"...
0x255c4  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x255c9  ldc.i4.0
0x255ca  stloc.0
0x255cb  br       loc_25670
0x255d0  ldarg.2
0x255d1  brtrue.s loc_255F0
0x255d3  ldc.i4   0x1192362
0x255d8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x255dd  ldc.i4.s 0xA
0x255df  ldstr    aTokenCacheTheC_15// "Token Cache: The cookie token is null"
0x255e4  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x255e9  ldc.i4.0
0x255ea  stloc.0
0x255eb  br       loc_25670
0x255f0  ldarg.0
0x255f1  ldarg.2
0x255f2  call     instance bool Microsoft.SharePoint.IdentityModel.SPTokenCache::ValidateCookieReferenceToken(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken cookieReferenceToken)
0x255f7  brtrue.s loc_25613
0x255f9  ldc.i4   0x1192363
0x255fe  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x25603  ldc.i4.s 0xA
0x25605  ldstr    aTokenCacheTheC_16// "Token Cache: The cookie token is not a "...
0x2560a  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x2560f  ldc.i4.0
0x25610  stloc.0
0x25611  br.s     loc_25670
0x25613  ldarg.0
0x25614  ldarg.2
0x25615  ldc.i4.1
0x25616  ldloca.s 1
0x25618  ldloca.s 2
0x2561a  callvirt instance bool Microsoft.SharePoint.IdentityModel.SPTokenCache::GetCookieInformationFromToken(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken sessionToken, valuetype Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValueOption cookieOption, [out] class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue& cookieObject, [out] string& cookieString)
0x2561f  brtrue.s loc_2563B
0x25621  ldc.i4   0x1192380
0x25626  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x2562b  ldc.i4.s 0xA
0x2562d  ldstr    aTokenCacheNewC_1// "Token Cache: New cookie string couldn't"...
0x25632  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x25637  ldc.i4.0
0x25638  stloc.0
0x25639  br.s     loc_25670
0x2563b  ldarg.0
0x2563c  ldloc.2
0x2563d  call     instance unsigned int8[] Microsoft.SharePoint.IdentityModel.SPTokenCache::WriteTokenToBytes(string tokenValue)
0x25642  stloc.3
0x25643  ldarg.1
0x25644  ldloc.2
0x25645  callvirt instance void Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::set_NewCookieString(string value)
0x2564a  ldarg.1
0x2564b  ldloc.3
0x2564c  callvirt instance void Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::set_NewCookieBinaryData(unsigned int8[] value)
0x25651  ldarg.1
0x25652  ldloc.1
0x25653  callvirt instance void Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::set_NewCookieValue(class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue value)
0x25658  ldc.i4   0x1192381
0x2565d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x25662  ldc.i4.s 0x32
0x25664  ldstr    aTokenCacheNewC_2// "Token Cache: New cookie value obtained."
0x25669  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x2566e  ldc.i4.1
0x2566f  stloc.0
0x25670  ldloc.0
0x25671  ret
```
