# Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::InitializeCookieDataForRequest

- ea: `0x21ed0`
- end: `0x21fcd`
- name: `Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::InitializeCookieDataForRequest`
- size: `253`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x21d60`

## callees

- `0x20660`
- `0x20b00`
- `0x21b30`
- `0x21b60`
- `0x21b80`
- `0x21ed0`
- `0x22ae0`
- `0x23040`
- `0x28160`

## string_xrefs

- `0x21eec`: `Token Request Data: No cookie bytes.`
- `0x21f12`: `Token Request Data: Could not get cookie value handler.`
- `0x21f43`: `Token Request Data: Null decoded cookie value in the request.`
- `0x21f65`: `Token Request Data: Empty decoded cookie value in the request.`
- `0x21f88`: `Token Request Data: Cookie didn't initialize properly.`
- `0x21fb0`: `Token Request Data: Cookie value is intialized. UserName: '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0x21ed0  ldc.i4.0
0x21ed1  stloc.0
0x21ed2  ldnull
0x21ed3  stloc.1
0x21ed4  ldnull
0x21ed5  stloc.2
0x21ed6  ldarg.0
0x21ed7  call     instance unsigned int8[] Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieBinaryData()
0x21edc  brtrue.s loc_21EFB
0x21ede  ldc.i4.0
0x21edf  stloc.0
0x21ee0  ldc.i4   0x5E3414
0x21ee5  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x21eea  ldc.i4.s 0xA
0x21eec  ldstr    aTokenRequestDa_10// "Token Request Data: No cookie bytes."
0x21ef1  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x21ef6  br       loc_21FCB
0x21efb  call     class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue Microsoft.SharePoint.IdentityModel.SPClaimsUtility::GetCookieValueHandler()
0x21f00  dup
0x21f01  stloc.2
0x21f02  brtrue.s loc_21F21
0x21f04  ldc.i4.0
0x21f05  stloc.0
0x21f06  ldc.i4   0x5E3415
0x21f0b  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x21f10  ldc.i4.s 0xA
0x21f12  ldstr    aTokenRequestDa_11// "Token Request Data: Could not get cooki"...
0x21f17  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x21f1c  br       loc_21FCB
0x21f21  call     class Microsoft.SharePoint.IdentityModel.SPTokenCache Microsoft.SharePoint.IdentityModel.SPTokenCache::get_Current()
0x21f26  ldarg.0
0x21f27  call     instance unsigned int8[] Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::get_CookieBinaryData()
0x21f2c  callvirt instance string Microsoft.SharePoint.IdentityModel.SPTokenCache::ReadTokenFromBytes(unsigned int8[] tokenValue)
0x21f31  dup
0x21f32  stloc.1
0x21f33  brtrue.s loc_21F4F
0x21f35  ldc.i4.0
0x21f36  stloc.0
0x21f37  ldc.i4   0x5E3416
0x21f3c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x21f41  ldc.i4.s 0xA
0x21f43  ldstr    aTokenRequestDa_12// "Token Request Data: Null decoded cookie"...
0x21f48  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x21f4d  br.s     loc_21FCB
0x21f4f  ldloc.1
0x21f50  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x21f55  brfalse.s loc_21F71
0x21f57  ldc.i4.0
0x21f58  stloc.0
0x21f59  ldc.i4   0x5E3417
0x21f5e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x21f63  ldc.i4.s 0xA
0x21f65  ldstr    aTokenRequestDa_13// "Token Request Data: Empty decoded cooki"...
0x21f6a  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x21f6f  br.s     loc_21FCB
0x21f71  ldloc.2
0x21f72  ldloc.1
0x21f73  callvirt instance bool Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::Initialize(string cookieValue)
0x21f78  brtrue.s loc_21F94
0x21f7a  ldc.i4.0
0x21f7b  stloc.0
0x21f7c  ldc.i4   0x5E3418
0x21f81  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x21f86  ldc.i4.s 0xA
0x21f88  ldstr    aTokenRequestDa_14// "Token Request Data: Cookie didn't initi"...
0x21f8d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x21f92  br.s     loc_21FCB
0x21f94  ldc.i4.1
0x21f95  stloc.0
0x21f96  ldarg.0
0x21f97  ldloc.1
0x21f98  call     instance void Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::set_CookieString(string value)
0x21f9d  ldarg.0
0x21f9e  ldloc.2
0x21f9f  call     instance void Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenRequestData::set_CookieValue(class Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue value)
0x21fa4  ldc.i4   0x5E3419
0x21fa9  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x21fae  ldc.i4.s 0x32
0x21fb0  ldstr    aTokenRequestDa_15// "Token Request Data: Cookie value is int"...
0x21fb5  ldc.i4.1
0x21fb6  newarr   [mscorlib]System.Object
0x21fbb  stloc.3
0x21fbc  ldloc.3
0x21fbd  ldc.i4.0
0x21fbe  ldloc.2
0x21fbf  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::get_UserName()
0x21fc4  stelem.ref
0x21fc5  ldloc.3
0x21fc6  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x21fcb  ldloc.0
0x21fcc  ret
```
