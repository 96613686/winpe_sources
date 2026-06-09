# Microsoft.SharePoint.IdentityModel.SPTokenCache::AreCookiesConsistentForWrite

- ea: `0x23b50`
- end: `0x23bce`
- name: `Microsoft.SharePoint.IdentityModel.SPTokenCache::AreCookiesConsistentForWrite`
- size: `126`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x23bd0`
- `0x23ca0`

## callees

- `0x20800`
- `0x23b50`

## string_xrefs

- `0x23b61`: `Token Cache: CookieValueOne is null.`
- `0x23b7e`: `Token Cache: CookieValueTwo is null.`
- `0x23ba6`: `Token Cache: Cookies are NOT consistent on IsPersistent.`
- `0x23bc0`: `Token Cache: Cookies are consistent on IsPersistent.`

## pseudocode

```c

```

## disassembly

```asm
0x23b50  ldc.i4.0
0x23b51  stloc.0
0x23b52  ldarg.1
0x23b53  brtrue.s loc_23B6F
0x23b55  ldc.i4   0x5E3447
0x23b5a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x23b5f  ldc.i4.s 0xA
0x23b61  ldstr    aTokenCacheCook// "Token Cache: CookieValueOne is null."
0x23b66  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x23b6b  ldc.i4.0
0x23b6c  stloc.0
0x23b6d  br.s     loc_23BCC
0x23b6f  ldarg.2
0x23b70  brtrue.s loc_23B8C
0x23b72  ldc.i4   0x5E3448
0x23b77  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x23b7c  ldc.i4.s 0xA
0x23b7e  ldstr    aTokenCacheCook_0// "Token Cache: CookieValueTwo is null."
0x23b83  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x23b88  ldc.i4.0
0x23b89  stloc.0
0x23b8a  br.s     loc_23BCC
0x23b8c  ldarg.1
0x23b8d  callvirt instance bool Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_IsPersistent()
0x23b92  ldarg.2
0x23b93  callvirt instance bool Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_IsPersistent()
0x23b98  beq.s    loc_23BB4
0x23b9a  ldc.i4   0x5E3449
0x23b9f  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x23ba4  ldc.i4.s 0xA
0x23ba6  ldstr    aTokenCacheCook_1// "Token Cache: Cookies are NOT consistent"...
0x23bab  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x23bb0  ldc.i4.0
0x23bb1  stloc.0
0x23bb2  br.s     loc_23BCC
0x23bb4  ldc.i4   0x5E344A
0x23bb9  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x23bbe  ldc.i4.s 0x32
0x23bc0  ldstr    aTokenCacheCook_2// "Token Cache: Cookies are consistent on "...
0x23bc5  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x23bca  ldc.i4.1
0x23bcb  stloc.0
0x23bcc  ldloc.0
0x23bcd  ret
```
