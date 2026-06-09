# Microsoft.SharePoint.IdentityModel.SPTokenCache::IsCookieDataValidForWrite

- ea: `0x23bd0`
- end: `0x23c9f`
- name: `Microsoft.SharePoint.IdentityModel.SPTokenCache::IsCookieDataValidForWrite`
- size: `207`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callers

- `0x24740`

## callees

- `0x22570`
- `0x226f0`
- `0x23b50`
- `0x23bd0`

## string_xrefs

- `0x23be6`: `Token Cache: The requestData is null.`
- `0x23c04`: `Token Cache: The cookieKind is None.`
- `0x23c2b`: `Token Cache: This is marked as an update but there is no original cookie data.`
- `0x23c5c`: `Token Cache: The cookie value to write isn't consistent with the current cookie value.`
- `0x23c77`: `Token Cache: Cookies are consistent for write update.`
- `0x23c91`: `Token Cache: Cookie is valid for rewrite.`

## pseudocode

```c

```

## disassembly

```asm
0x23bd0  ldc.i4.0
0x23bd1  stloc.0
0x23bd2  ldc.i4.2
0x23bd3  ldarg.2
0x23bd4  ceq
0x23bd6  stloc.1
0x23bd7  ldarg.1
0x23bd8  brtrue.s loc_23BF5
0x23bda  ldc.i4   0x6D31C9
0x23bdf  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x23be4  ldc.i4.s 0xA
0x23be6  ldstr    aTokenCacheTheR// "Token Cache: The requestData is null."
0x23beb  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x23bf0  br       loc_23C9D
0x23bf5  ldarg.2
0x23bf6  brtrue.s loc_23C13
0x23bf8  ldc.i4   0x6D31CA
0x23bfd  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x23c02  ldc.i4.s 0xA
0x23c04  ldstr    aTokenCacheTheC_0// "Token Cache: The cookieKind is None."
0x23c09  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x23c0e  br       loc_23C9D
0x23c13  ldloc.1
0x23c14  brfalse.s loc_23C37
0x23c16  ldarg.1
0x23c17  ldc.i4.1
0x23c18  callvirt instance bool Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::CheckCookieData(valuetype Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestDataKind kind)
0x23c1d  brtrue.s loc_23C37
0x23c1f  ldc.i4   0x6D31CB
0x23c24  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x23c29  ldc.i4.s 0xA
0x23c2b  ldstr    aTokenCacheThis// "Token Cache: This is marked as an updat"...
0x23c30  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x23c35  br.s     loc_23C9D
0x23c37  ldloc.1
0x23c38  brfalse.s loc_23C68
0x23c3a  ldarg.0
0x23c3b  ldarg.1
0x23c3c  ldc.i4.1
0x23c3d  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::GetCookieValue(valuetype Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestDataKind kind)
0x23c42  ldarg.1
0x23c43  ldarg.2
0x23c44  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::GetCookieValue(valuetype Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestDataKind kind)
0x23c49  callvirt instance bool Microsoft.SharePoint.IdentityModel.SPTokenCache::AreCookiesConsistentForWrite(class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue cookieValueOne, class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue cookieValueTwo)
0x23c4e  brtrue.s loc_23C68
0x23c50  ldc.i4   0x6D31CC
0x23c55  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x23c5a  ldc.i4.s 0xA
0x23c5c  ldstr    aTokenCacheTheC_1// "Token Cache: The cookie value to write "...
0x23c61  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x23c66  br.s     loc_23C9D
0x23c68  ldloc.1
0x23c69  brfalse.s loc_23C85
0x23c6b  ldc.i4   0x6D31CD
0x23c70  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x23c75  ldc.i4.s 0x32
0x23c77  ldstr    aTokenCacheCook_3// "Token Cache: Cookies are consistent for"...
0x23c7c  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x23c81  ldc.i4.1
0x23c82  stloc.0
0x23c83  br.s     loc_23C9D
0x23c85  ldc.i4   0x6D31CE
0x23c8a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x23c8f  ldc.i4.s 0x32
0x23c91  ldstr    aTokenCacheCook_4// "Token Cache: Cookie is valid for rewrit"...
0x23c96  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x23c9b  ldc.i4.1
0x23c9c  stloc.0
0x23c9d  ldloc.0
0x23c9e  ret
```
