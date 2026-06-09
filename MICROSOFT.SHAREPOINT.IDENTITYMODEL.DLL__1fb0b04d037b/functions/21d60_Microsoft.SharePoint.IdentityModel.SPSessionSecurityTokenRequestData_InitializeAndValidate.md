# Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::InitializeAndValidate

- ea: `0x21d60`
- end: `0x21ec2`
- name: `Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::InitializeAndValidate`
- size: `354`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x24b00`

## callees

- `0x20660`
- `0x208b0`
- `0x21b40`
- `0x21b70`
- `0x21d60`
- `0x21ed0`
- `0x22040`
- `0x22230`
- `0x22280`

## string_xrefs

- `0x21d78`: `Token Request Data: The CookieBinaryData is null.`
- `0x21d9b`: `Token Request Data: Couldn't initialize cook data for request.`
- `0x21dc0`: `Token Request Data: Failure initializing site subscription for request. Uri: '{0}'.`
- `0x21df5`: `Token Request Data: Couldn't validate request cookie.`
- `0x21e1f`: `Token Request Data: Unknown issuer type for cookie's identity. UserName: '{0}'.`
- `0x21e57`: `Token Request Data: Failure intializing token for request. UserName: '{0}'.`
- `0x21e87`: `Token Request Data: Initialized and validated request data. UserName: '{0}', IssuerType: '{1}'.`

## pseudocode

```c

```

## disassembly

```asm
0x21d60  ldc.i4.0
0x21d61  stloc.0
0x21d62  ldarg.0
0x21d63  ldarg.1
0x21d64  call     instance void Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::set_CookieBinaryData(unsigned int8[] value)
0x21d69  ldarg.1
0x21d6a  brtrue.s loc_21D87
0x21d6c  ldc.i4   0x5E340D
0x21d71  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x21d76  ldc.i4.s 0xA
0x21d78  ldstr    aTokenRequestDa_3// "Token Request Data: The CookieBinaryDat"...
0x21d7d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x21d82  br       loc_21EC0
0x21d87  ldarg.0
0x21d88  callvirt instance bool Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::InitializeCookieDataForRequest()
0x21d8d  brtrue.s loc_21DAC
0x21d8f  ldc.i4   0x5E340E
0x21d94  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x21d99  ldc.i4.s 0xA
0x21d9b  ldstr    aTokenRequestDa_4// "Token Request Data: Couldn't initialize"...
0x21da0  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x21da5  ldc.i4.0
0x21da6  stloc.0
0x21da7  br       loc_21EC0
0x21dac  ldarg.0
0x21dad  call     instance bool Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::InitializeSiteSubscription()
0x21db2  brtrue.s loc_21DE1
0x21db4  ldc.i4   0x11D881A
0x21db9  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x21dbe  ldc.i4.s 0xA
0x21dc0  ldstr    aTokenRequestDa_5// "Token Request Data: Failure initializin"...
0x21dc5  ldc.i4.1
0x21dc6  newarr   [mscorlib]System.Object
0x21dcb  stloc.1
0x21dcc  ldloc.1
0x21dcd  ldc.i4.0
0x21dce  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAlternateUrl::get_ContextUri()
0x21dd3  stelem.ref
0x21dd4  ldloc.1
0x21dd5  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x21dda  ldc.i4.0
0x21ddb  stloc.0
0x21ddc  br       loc_21EC0
0x21de1  ldarg.0
0x21de2  callvirt instance bool Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::ValidateCookieValue()
0x21de7  brtrue.s loc_21E06
0x21de9  ldc.i4   0x5E340F
0x21dee  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x21df3  ldc.i4.s 0x14
0x21df5  ldstr    aTokenRequestDa_6// "Token Request Data: Couldn't validate r"...
0x21dfa  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x21dff  ldc.i4.0
0x21e00  stloc.0
0x21e01  br       loc_21EC0
0x21e06  ldarg.0
0x21e07  call     instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x21e0c  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPOriginalIssuerType Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_IssuerType()
0x21e11  brtrue.s loc_21E43
0x21e13  ldc.i4   0x5E3410
0x21e18  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x21e1d  ldc.i4.s 0xA
0x21e1f  ldstr    aTokenRequestDa_7// "Token Request Data: Unknown issuer type"...
0x21e24  ldc.i4.1
0x21e25  newarr   [mscorlib]System.Object
0x21e2a  stloc.2
0x21e2b  ldloc.2
0x21e2c  ldc.i4.0
0x21e2d  ldarg.0
0x21e2e  call     instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x21e33  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_UserName()
0x21e38  stelem.ref
0x21e39  ldloc.2
0x21e3a  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x21e3f  ldc.i4.0
0x21e40  stloc.0
0x21e41  br.s     loc_21EC0
0x21e43  ldarg.0
0x21e44  callvirt instance bool Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::InitializeTokenDataForRequest()
0x21e49  brtrue.s loc_21E7B
0x21e4b  ldc.i4   0x5E3412
0x21e50  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x21e55  ldc.i4.s 0xA
0x21e57  ldstr    aTokenRequestDa_8// "Token Request Data: Failure intializing"...
0x21e5c  ldc.i4.1
0x21e5d  newarr   [mscorlib]System.Object
0x21e62  stloc.3
0x21e63  ldloc.3
0x21e64  ldc.i4.0
0x21e65  ldarg.0
0x21e66  call     instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x21e6b  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_UserName()
0x21e70  stelem.ref
0x21e71  ldloc.3
0x21e72  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x21e77  ldc.i4.0
0x21e78  stloc.0
0x21e79  br.s     loc_21EC0
0x21e7b  ldc.i4   0x5E3413
0x21e80  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x21e85  ldc.i4.s 0x32
0x21e87  ldstr    aTokenRequestDa_9// "Token Request Data: Initialized and val"...
0x21e8c  ldc.i4.2
0x21e8d  newarr   [mscorlib]System.Object
0x21e92  stloc.s  4
0x21e94  ldloc.s  4
0x21e96  ldc.i4.0
0x21e97  ldarg.0
0x21e98  call     instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x21e9d  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_UserName()
0x21ea2  stelem.ref
0x21ea3  ldloc.s  4
0x21ea5  ldc.i4.1
0x21ea6  ldarg.0
0x21ea7  call     instance class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieValue()
0x21eac  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPOriginalIssuerType Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_IssuerType()
0x21eb1  box      [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPOriginalIssuerType
0x21eb6  stelem.ref
0x21eb7  ldloc.s  4
0x21eb9  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x21ebe  ldc.i4.1
0x21ebf  stloc.0
0x21ec0  ldloc.0
0x21ec1  ret
```
