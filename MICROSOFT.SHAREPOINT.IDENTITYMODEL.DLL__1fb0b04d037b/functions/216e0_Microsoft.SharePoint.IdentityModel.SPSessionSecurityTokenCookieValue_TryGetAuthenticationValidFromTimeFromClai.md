# Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::TryGetAuthenticationValidFromTimeFromClaimsIdentity

- ea: `0x216e0`
- end: `0x217ba`
- name: `Microsoft.SharePoint.IdentityModel.SPSessionSecurityTokenCookieValue::TryGetAuthenticationValidFromTimeFromClaimsIdentity`
- size: `218`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x21610`

## callees

- `0x216e0`

## string_xrefs

- `0x21744`: `No token AVF claim in output claims.`
- `0x21767`: `Failed to get token AVF from output claims with exception. Exception: '{0}'`
- `0x2178b`: `Read token AVF from output claims. Token AVF: '{0}' Result: '{1}'.`

## pseudocode

```c

```

## disassembly

```asm
0x216e0  ldarg.2
0x216e1  initobj  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x216e7  ldc.i4.0
0x216e8  stloc.0
0x216e9  ldarg.1
0x216ea  brtrue.s loc_21704
0x216ec  ldc.i4   0x5D489B
0x216f1  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x216f6  ldc.i4.s 0xA
0x216f8  ldstr    aOutputClaimsId// "Output claims identity was null."
0x216fd  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x21702  br.s     loc_2177F
0x21704  ldarg.1
0x21705  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x2170a  brtrue.s loc_21724
0x2170c  ldc.i4   0x5D489C
0x21711  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x21716  ldc.i4.s 0xA
0x21718  ldstr    aOutputClaimsId_0// "Output claims identity claims were null"...
0x2171d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x21722  br.s     loc_2177F
0x21724  ldarg.1
0x21725  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x2172a  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimTypes::get_AuthenticationValidFromUtc()
0x2172f  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimCollectionExtensions::GetSingleClaim(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection, string)
0x21734  stloc.1
0x21735  ldloc.1
0x21736  brtrue.s loc_21750
0x21738  ldc.i4   0x5D489E
0x2173d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x21742  ldc.i4.s 0x32
0x21744  ldstr    aNoTokenAvfClai// "No token AVF claim in output claims."
0x21749  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x2174e  br.s     loc_21758
0x21750  ldloc.1
0x21751  ldarg.2
0x21752  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimExtensions::TryGetValueAsFileTimeUtc(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>&)
0x21757  stloc.0
0x21758  leave.s  loc_2177F
0x2175a  stloc.2
0x2175b  ldc.i4   0x5D489D
0x21760  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x21765  ldc.i4.s 0xA
0x21767  ldstr    aFailedToGetTok_1// "Failed to get token AVF from output cla"...
0x2176c  ldc.i4.1
0x2176d  newarr   [mscorlib]System.Object
0x21772  stloc.3
0x21773  ldloc.3
0x21774  ldc.i4.0
0x21775  ldloc.2
0x21776  stelem.ref
0x21777  ldloc.3
0x21778  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x2177d  leave.s  loc_2177F
0x2177f  ldc.i4   0x7588CC
0x21784  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x21789  ldc.i4.s 0x32
0x2178b  ldstr    aReadTokenAvfFr// "Read token AVF from output claims. Toke"...
0x21790  ldc.i4.2
0x21791  newarr   [mscorlib]System.Object
0x21796  stloc.s  4
0x21798  ldloc.s  4
0x2179a  ldc.i4.0
0x2179b  ldarg.2
0x2179c  ldobj    valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x217a1  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x217a6  stelem.ref
0x217a7  ldloc.s  4
0x217a9  ldc.i4.1
0x217aa  ldloc.0
0x217ab  box      [mscorlib]System.Boolean
0x217b0  stelem.ref
0x217b1  ldloc.s  4
0x217b3  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x217b8  ldloc.0
0x217b9  ret
```
