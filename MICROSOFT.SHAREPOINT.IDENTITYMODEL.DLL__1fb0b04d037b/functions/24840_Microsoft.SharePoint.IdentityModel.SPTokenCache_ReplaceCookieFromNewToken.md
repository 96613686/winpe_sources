# Microsoft.SharePoint.IdentityModel.SPTokenCache::ReplaceCookieFromNewToken

- ea: `0x24840`
- end: `0x248ec`
- name: `Microsoft.SharePoint.IdentityModel.SPTokenCache::ReplaceCookieFromNewToken`
- size: `172`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x244f0`
- `0x24930`

## callees

- `0x21b70`
- `0x21ca0`
- `0x21cc0`
- `0x21ce0`
- `0x21d00`
- `0x22da0`
- `0x22f40`
- `0x24740`
- `0x24840`

## string_xrefs

- `0x24853`: `Token Cache: RequestData is null.`
- `0x24872`: `Token Cache: CurrentCookieValue is null.`
- `0x24891`: `Token Cache: NewSessionToken is null.`
- `0x248bb`: `Token Cache: New Cookie string couldn't be obtained from token.`

## pseudocode

```c

```

## disassembly

```asm
0x24840  ldnull
0x24841  stloc.0
0x24842  ldnull
0x24843  stloc.1
0x24844  ldarg.1
0x24845  brtrue.s loc_2485E
0x24847  ldc.i4   0x6D31D4
0x2484c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x24851  ldc.i4.s 0xA
0x24853  ldstr    aTokenCacheRequ_2// "Token Cache: RequestData is null."
0x24858  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x2485d  ret
0x2485e  ldarg.1
0x2485f  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x24864  brtrue.s loc_2487D
0x24866  ldc.i4   0x6D31D5
0x2486b  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x24870  ldc.i4.s 0xA
0x24872  ldstr    aTokenCacheCurr// "Token Cache: CurrentCookieValue is null"...
0x24877  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x2487c  ret
0x2487d  ldarg.1
0x2487e  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_NewSessionToken()
0x24883  brtrue.s loc_2489C
0x24885  ldc.i4   0x6D31D6
0x2488a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x2488f  ldc.i4.s 0xA
0x24891  ldstr    aTokenCacheNews// "Token Cache: NewSessionToken is null."
0x24896  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x2489b  ret
0x2489c  ldarg.0
0x2489d  ldarg.1
0x2489e  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_NewSessionToken()
0x248a3  ldc.i4.1
0x248a4  ldloca.s 0
0x248a6  ldloca.s 1
0x248a8  callvirt instance bool Microsoft.SharePoint.IdentityModel.SPTokenCache::GetCookieInformationFromToken(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken sessionToken, valuetype Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValueOption cookieOption, [out] class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue& cookieObject, [out] string& cookieString)
0x248ad  brtrue.s loc_248C6
0x248af  ldc.i4   0x6D31D7
0x248b4  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x248b9  ldc.i4.s 0xA
0x248bb  ldstr    aTokenCacheNewC_0// "Token Cache: New Cookie string couldn't"...
0x248c0  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x248c5  ret
0x248c6  ldarg.0
0x248c7  ldloc.1
0x248c8  call     instance unsigned int8[] Microsoft.SharePoint.IdentityModel.SPTokenCache::WriteTokenToBytes(string tokenValue)
0x248cd  stloc.2
0x248ce  ldarg.1
0x248cf  ldloc.1
0x248d0  callvirt instance void Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::set_NewCookieString(string value)
0x248d5  ldarg.1
0x248d6  ldloc.2
0x248d7  callvirt instance void Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::set_NewCookieBinaryData(unsigned int8[] value)
0x248dc  ldarg.1
0x248dd  ldloc.0
0x248de  callvirt instance void Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::set_NewCookieValue(class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue value)
0x248e3  ldarg.0
0x248e4  ldarg.1
0x248e5  ldc.i4.2
0x248e6  callvirt instance void Microsoft.SharePoint.IdentityModel.SPTokenCache::WriteCookie(class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData requestData, valuetype Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestDataKind cookieKind)
0x248eb  ret
```
