# Microsoft.SharePoint.IdentityModel.SPSecurityTokenService::TryGetTokenAvfFromOutputClaims

- ea: `0x1f170`
- end: `0x1f2b0`
- name: `Microsoft.SharePoint.IdentityModel.SPSecurityTokenService::TryGetTokenAvfFromOutputClaims`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1ef60`

## callees

- `0x1f170`

## string_xrefs

- `0x1f191`: `Supplied claimsIdentity was null.`
- `0x1f1b4`: `Supplied claimsIdentity.Claims was null.`
- `0x1f28e`: `Failed to get token AVF from output claims. Exception: '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0x1f170  ldc.i4.0
0x1f171  stloc.0
0x1f172  ldarg.2
0x1f173  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x1f178  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0x1f17d  stobj    valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x1f182  ldarg.1
0x1f183  brtrue.s loc_1F1A0
0x1f185  ldc.i4   0x7A0514
0x1f18a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1f18f  ldc.i4.s 0xA
0x1f191  ldstr    aSuppliedClaims// "Supplied claimsIdentity was null."
0x1f196  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1f19b  br       loc_1F26D
0x1f1a0  ldarg.1
0x1f1a1  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x1f1a6  brtrue.s loc_1F1C3
0x1f1a8  ldc.i4   0x7A0515
0x1f1ad  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1f1b2  ldc.i4.s 0xA
0x1f1b4  ldstr    aSuppliedClaims_0// "Supplied claimsIdentity.Claims was null"...
0x1f1b9  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1f1be  br       loc_1F26D
0x1f1c3  ldarg.1
0x1f1c4  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x1f1c9  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimTypes::get_AuthenticationValidFromUtc()
0x1f1ce  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimCollectionExtensions::GetSingleClaim(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection, string)
0x1f1d3  stloc.1
0x1f1d4  ldloc.1
0x1f1d5  brtrue.s loc_1F1FF
0x1f1d7  ldc.i4   0x7A0516
0x1f1dc  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1f1e1  ldc.i4.s 0x32
0x1f1e3  ldstr    aAvfClaimNotPre// "AVF claim not present. Claim type: '{0}"...
0x1f1e8  ldc.i4.1
0x1f1e9  newarr   [mscorlib]System.Object
0x1f1ee  stloc.3
0x1f1ef  ldloc.3
0x1f1f0  ldc.i4.0
0x1f1f1  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimTypes::get_AuthenticationValidFromUtc()
0x1f1f6  stelem.ref
0x1f1f7  ldloc.3
0x1f1f8  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1f1fd  br.s     loc_1F26D
0x1f1ff  ldloc.1
0x1f200  ldarg.2
0x1f201  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimExtensions::TryGetValueAsFileTimeUtc(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>&)
0x1f206  brtrue.s loc_1F233
0x1f208  ldc.i4   0x7A0517
0x1f20d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1f212  ldc.i4.s 0xA
0x1f214  ldstr    aFailedToParseA_1// "Failed to parse AVF from claim. Claim t"...
0x1f219  ldc.i4.1
0x1f21a  newarr   [mscorlib]System.Object
0x1f21f  stloc.s  4
0x1f221  ldloc.s  4
0x1f223  ldc.i4.0
0x1f224  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimTypes::get_AuthenticationValidFromUtc()
0x1f229  stelem.ref
0x1f22a  ldloc.s  4
0x1f22c  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1f231  br.s     loc_1F26D
0x1f233  ldc.i4.1
0x1f234  stloc.0
0x1f235  ldc.i4   0x7A0518
0x1f23a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1f23f  ldc.i4.s 0x64
0x1f241  ldstr    aGotAvfFromClai// "Got AVF from claim. Claim type: '{0}', "...
0x1f246  ldc.i4.2
0x1f247  newarr   [mscorlib]System.Object
0x1f24c  stloc.s  5
0x1f24e  ldloc.s  5
0x1f250  ldc.i4.0
0x1f251  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimTypes::get_AuthenticationValidFromUtc()
0x1f256  stelem.ref
0x1f257  ldloc.s  5
0x1f259  ldc.i4.1
0x1f25a  ldarg.2
0x1f25b  ldobj    valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x1f260  box      valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x1f265  stelem.ref
0x1f266  ldloc.s  5
0x1f268  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1f26d  leave.s  loc_1F2AE
0x1f26f  stloc.2
0x1f270  ldc.i4.0
0x1f271  stloc.0
0x1f272  ldarg.2
0x1f273  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0x1f278  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0x1f27d  stobj    valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x1f282  ldc.i4   0x7A0519
0x1f287  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1f28c  ldc.i4.s 0xA
0x1f28e  ldstr    aFailedToGetTok_0// "Failed to get token AVF from output cla"...
0x1f293  ldc.i4.1
0x1f294  newarr   [mscorlib]System.Object
0x1f299  stloc.s  6
0x1f29b  ldloc.s  6
0x1f29d  ldc.i4.0
0x1f29e  ldloc.2
0x1f29f  callvirt instance string [mscorlib]System.Object::ToString()
0x1f2a4  stelem.ref
0x1f2a5  ldloc.s  6
0x1f2a7  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1f2ac  leave.s  loc_1F2AE
0x1f2ae  ldloc.0
0x1f2af  ret
```
