# Microsoft.SharePoint.IdentityModel.SPTokenCache::UpdateCookieIfNecessary

- ea: `0x24a40`
- end: `0x24af9`
- name: `Microsoft.SharePoint.IdentityModel.SPTokenCache::UpdateCookieIfNecessary`
- size: `185`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x24c50`

## callees

- `0x21b30`
- `0x21b70`
- `0x21bd0`
- `0x23d50`
- `0x23de0`
- `0x248f0`
- `0x24930`
- `0x24a40`

## string_xrefs

- `0x24a6e`: `Token Cache: CookieValue is null.`
- `0x24a4f`: `Token Cache: RequestData is null.`
- `0x24a8d`: `Token Cache: CachedToken is null.`
- `0x24aac`: `Token Cache: CookieBinaryData is null.`

## pseudocode

```c

```

## disassembly

```asm
0x24a40  ldarg.1
0x24a41  brtrue.s loc_24A5A
0x24a43  ldc.i4   0x5E349F
0x24a48  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x24a4d  ldc.i4.s 0xA
0x24a4f  ldstr    aTokenCacheRequ_2// "Token Cache: RequestData is null."
0x24a54  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x24a59  ret
0x24a5a  ldarg.1
0x24a5b  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x24a60  brtrue.s loc_24A79
0x24a62  ldc.i4   0x5E34A0
0x24a67  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x24a6c  ldc.i4.s 0xA
0x24a6e  ldstr    aTokenCacheCook_5// "Token Cache: CookieValue is null."
0x24a73  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x24a78  ret
0x24a79  ldarg.1
0x24a7a  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CachedSessionToken()
0x24a7f  brtrue.s loc_24A98
0x24a81  ldc.i4   0x5E34A1
0x24a86  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x24a8b  ldc.i4.s 0xA
0x24a8d  ldstr    aTokenCacheCach_0// "Token Cache: CachedToken is null."
0x24a92  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x24a97  ret
0x24a98  ldarg.1
0x24a99  callvirt instance unsigned int8[] Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieBinaryData()
0x24a9e  brtrue.s loc_24AB7
0x24aa0  ldc.i4   0x5E34A2
0x24aa5  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x24aaa  ldc.i4.s 0xA
0x24aac  ldstr    aTokenCacheCook_11// "Token Cache: CookieBinaryData is null."
0x24ab1  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x24ab6  ret
0x24ab7  ldarg.1
0x24ab8  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CachedSessionToken()
0x24abd  brfalse.s loc_24AD8
0x24abf  ldarg.1
0x24ac0  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x24ac5  brfalse.s loc_24AD8
0x24ac7  ldarg.0
0x24ac8  ldarg.1
0x24ac9  callvirt instance bool Microsoft.SharePoint.IdentityModel.SPTokenCache::DoesCookieNeedToBeRefreshed(class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData requestData)
0x24ace  brfalse.s loc_24AD8
0x24ad0  ldarg.0
0x24ad1  ldarg.1
0x24ad2  callvirt instance void Microsoft.SharePoint.IdentityModel.SPTokenCache::RefreshCookie(class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData requestData)
0x24ad7  ret
0x24ad8  ldarg.1
0x24ad9  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CachedSessionToken()
0x24ade  brfalse.s loc_24AF8
0x24ae0  ldarg.1
0x24ae1  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x24ae6  brfalse.s loc_24AF8
0x24ae8  ldarg.0
0x24ae9  ldarg.1
0x24aea  callvirt instance bool Microsoft.SharePoint.IdentityModel.SPTokenCache::DoesCookieNeedToBeRewritten(class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData requestData)
0x24aef  brfalse.s loc_24AF8
0x24af1  ldarg.0
0x24af2  ldarg.1
0x24af3  callvirt instance void Microsoft.SharePoint.IdentityModel.SPTokenCache::RewriteCookie(class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData requestData)
0x24af8  ret
```
