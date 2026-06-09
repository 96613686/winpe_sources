# Microsoft.SharePoint.IdentityModel.SPTokenCache::AreTokenAndCookieConsistentForWrite

- ea: `0x23ca0`
- end: `0x23d42`
- name: `Microsoft.SharePoint.IdentityModel.SPTokenCache::AreTokenAndCookieConsistentForWrite`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x24080`

## callees

- `0x22ed0`
- `0x23b50`
- `0x23ca0`

## string_xrefs

- `0x23cb3`: `Token Cache: CookieValue is null.`
- `0x23cd0`: `Token Cache: SessionToken is null.`
- `0x23cf6`: `Token Cache: Cookie value couldn't be obtained from token so declining to refresh token.`
- `0x23d1a`: `Token Cache: Token and cookie are NOT consistent.`
- `0x23d34`: `Token Cache: Token and cookie are consistent.`

## pseudocode

```c

```

## disassembly

```asm
0x23ca0  ldc.i4.0
0x23ca1  stloc.0
0x23ca2  ldnull
0x23ca3  stloc.1
0x23ca4  ldarg.1
0x23ca5  brtrue.s loc_23CC1
0x23ca7  ldc.i4   0x5E344B
0x23cac  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x23cb1  ldc.i4.s 0xA
0x23cb3  ldstr    aTokenCacheCook_5// "Token Cache: CookieValue is null."
0x23cb8  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x23cbd  ldc.i4.0
0x23cbe  stloc.0
0x23cbf  br.s     loc_23D40
0x23cc1  ldarg.2
0x23cc2  brtrue.s loc_23CDE
0x23cc4  ldc.i4   0x5E344C
0x23cc9  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x23cce  ldc.i4.s 0xA
0x23cd0  ldstr    aTokenCacheSess// "Token Cache: SessionToken is null."
0x23cd5  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x23cda  ldc.i4.0
0x23cdb  stloc.0
0x23cdc  br.s     loc_23D40
0x23cde  ldarg.0
0x23cdf  ldarg.2
0x23ce0  ldc.i4.1
0x23ce1  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPTokenCache::GetCookieObjectFromToken(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken sessionToken, valuetype Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValueOption cookieOption)
0x23ce6  dup
0x23ce7  stloc.1
0x23ce8  brtrue.s loc_23D04
0x23cea  ldc.i4   0x5E344D
0x23cef  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x23cf4  ldc.i4.s 0xA
0x23cf6  ldstr    aTokenCacheCook_6// "Token Cache: Cookie value couldn't be o"...
0x23cfb  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x23d00  ldc.i4.0
0x23d01  stloc.0
0x23d02  br.s     loc_23D40
0x23d04  ldarg.0
0x23d05  ldarg.1
0x23d06  ldloc.1
0x23d07  callvirt instance bool Microsoft.SharePoint.IdentityModel.SPTokenCache::AreCookiesConsistentForWrite(class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue cookieValueOne, class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue cookieValueTwo)
0x23d0c  brtrue.s loc_23D28
0x23d0e  ldc.i4   0x5E344E
0x23d13  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x23d18  ldc.i4.s 0xA
0x23d1a  ldstr    aTokenCacheToke// "Token Cache: Token and cookie are NOT c"...
0x23d1f  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x23d24  ldc.i4.0
0x23d25  stloc.0
0x23d26  br.s     loc_23D40
0x23d28  ldc.i4   0x5E344F
0x23d2d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x23d32  ldc.i4.s 0x32
0x23d34  ldstr    aTokenCacheToke_0// "Token Cache: Token and cookie are consi"...
0x23d39  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x23d3e  ldc.i4.1
0x23d3f  stloc.0
0x23d40  ldloc.0
0x23d41  ret
```
