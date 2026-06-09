# Microsoft.SharePoint.IdentityModel.SPWindowsClaimsAuthenticationHttpModule::ShouldWriteCookie

- ea: `0x26b60`
- end: `0x26c09`
- name: `Microsoft.SharePoint.IdentityModel.SPWindowsClaimsAuthenticationHttpModule::ShouldWriteCookie`
- size: `169`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x26910`

## callees

- `0x26b60`

## string_xrefs

- `0x26b71`: `ShouldWriteCookie: 'false'. WindowsOnly: 'true'.`
- `0x26b91`: `ShouldWriteCookie: 'false'. SessionSecurityToken: 'null'.`
- `0x26bba`: `ShouldWriteCookie: 'false'. TokenReference: 'null'.`
- `0x26be1`: `ShouldWriteCookie: 'false'. TokenReferenceValue: 'null'.`
- `0x26bfb`: `ShouldWriteCookie: 'true'.`

## pseudocode

```c

```

## disassembly

```asm
0x26b60  ldc.i4.0
0x26b61  stloc.0
0x26b62  ldarg.1
0x26b63  brfalse.s loc_26B82
0x26b65  ldc.i4   0x1280594
0x26b6a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x26b6f  ldc.i4.s 0x64
0x26b71  ldstr    aShouldwritecoo// "ShouldWriteCookie: 'false'. WindowsOnly"...
0x26b76  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x26b7b  ldc.i4.0
0x26b7c  stloc.0
0x26b7d  br       loc_26C07
0x26b82  ldarg.2
0x26b83  brtrue.s loc_26B9F
0x26b85  ldc.i4   0x1280595
0x26b8a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x26b8f  ldc.i4.s 0x64
0x26b91  ldstr    aShouldwritecoo_0// "ShouldWriteCookie: 'false'. SessionSecu"...
0x26b96  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x26b9b  ldc.i4.0
0x26b9c  stloc.0
0x26b9d  br.s     loc_26C07
0x26b9f  ldarg.2
0x26ba0  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimTypes::get_TokenReference()
0x26ba5  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSessionSecurityTokenExtensions::GetSingleClaim(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken, string)
0x26baa  dup
0x26bab  stloc.1
0x26bac  brtrue.s loc_26BC8
0x26bae  ldc.i4   0x1280596
0x26bb3  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x26bb8  ldc.i4.s 0x64
0x26bba  ldstr    aShouldwritecoo_1// "ShouldWriteCookie: 'false'. TokenRefere"...
0x26bbf  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x26bc4  ldc.i4.0
0x26bc5  stloc.0
0x26bc6  br.s     loc_26C07
0x26bc8  ldloc.1
0x26bc9  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x26bce  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x26bd3  brfalse.s loc_26BEF
0x26bd5  ldc.i4   0x1280597
0x26bda  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x26bdf  ldc.i4.s 0x64
0x26be1  ldstr    aShouldwritecoo_2// "ShouldWriteCookie: 'false'. TokenRefere"...
0x26be6  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x26beb  ldc.i4.0
0x26bec  stloc.0
0x26bed  br.s     loc_26C07
0x26bef  ldc.i4   0x1280598
0x26bf4  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x26bf9  ldc.i4.s 0x64
0x26bfb  ldstr    aShouldwritecoo_3// "ShouldWriteCookie: 'true'."
0x26c00  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x26c05  ldc.i4.1
0x26c06  stloc.0
0x26c07  ldloc.0
0x26c08  ret
```
