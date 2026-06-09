# Microsoft.SharePoint.IdentityModel.SPTokenCache::InitializeAndValidateRequest

- ea: `0x24b00`
- end: `0x24b85`
- name: `Microsoft.SharePoint.IdentityModel.SPTokenCache::InitializeAndValidateRequest`
- size: `133`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x24c50`

## callees

- `0x20660`
- `0x208b0`
- `0x21b70`
- `0x21d60`
- `0x24b00`

## string_xrefs

- `0x24b11`: `Token Cache: RequestData is null.`
- `0x24b34`: `Token Cache: Couldn't initialize data for request.`
- `0x24b4e`: `Token Cache: Initialized and validated request data. Username: <name>'{0}'</name>, IssuerType: '{1}'.`

## pseudocode

```c

```

## disassembly

```asm
0x24b00  ldc.i4.0
0x24b01  stloc.0
0x24b02  ldarg.1
0x24b03  brtrue.s loc_24B1F
0x24b05  ldc.i4   0x5E34A3
0x24b0a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x24b0f  ldc.i4.s 0xA
0x24b11  ldstr    aTokenCacheRequ_2// "Token Cache: RequestData is null."
0x24b16  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x24b1b  ldc.i4.0
0x24b1c  stloc.0
0x24b1d  br.s     loc_24B83
0x24b1f  ldarg.1
0x24b20  ldarg.2
0x24b21  callvirt instance bool Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::InitializeAndValidate(unsigned int8[] cookieBinaryData)
0x24b26  brtrue.s loc_24B42
0x24b28  ldc.i4   0x5E34C0
0x24b2d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x24b32  ldc.i4.s 0xA
0x24b34  ldstr    aTokenCacheCoul_7// "Token Cache: Couldn't initialize data f"...
0x24b39  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x24b3e  ldc.i4.0
0x24b3f  stloc.0
0x24b40  br.s     loc_24B83
0x24b42  ldc.i4   0x5E34C1
0x24b47  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x24b4c  ldc.i4.s 0x32
0x24b4e  ldstr    aTokenCacheInit// "Token Cache: Initialized and validated "...
0x24b53  ldc.i4.2
0x24b54  newarr   [mscorlib]System.Object
0x24b59  stloc.1
0x24b5a  ldloc.1
0x24b5b  ldc.i4.0
0x24b5c  ldarg.1
0x24b5d  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x24b62  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_UserName()
0x24b67  stelem.ref
0x24b68  ldloc.1
0x24b69  ldc.i4.1
0x24b6a  ldarg.1
0x24b6b  callvirt instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x24b70  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPOriginalIssuerType Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_IssuerType()
0x24b75  box      [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPOriginalIssuerType
0x24b7a  stelem.ref
0x24b7b  ldloc.1
0x24b7c  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x24b81  ldc.i4.1
0x24b82  stloc.0
0x24b83  ldloc.0
0x24b84  ret
```
