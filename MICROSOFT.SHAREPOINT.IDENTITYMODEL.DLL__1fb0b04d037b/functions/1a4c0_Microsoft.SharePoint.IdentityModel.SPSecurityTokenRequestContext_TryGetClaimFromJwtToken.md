# Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::TryGetClaimFromJwtToken

- ea: `0x1a4c0`
- end: `0x1a5a6`
- name: `Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::TryGetClaimFromJwtToken`
- size: `230`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1a430`
- `0x1b5b0`
- `0x1b670`

## callees

- `0x1a4c0`
- `0x1bf90`

## string_xrefs

- `0x1a4d4`: `TryGetClaimFromJwtToken: Token is null.`
- `0x1a4f7`: `TryGetClaimFromJwtToken: No claims available on the token.`
- `0x1a51f`: `TryGetClaimFromJwtToken: Did not find claim. ClaimType: '{0}'.`
- `0x1a548`: `TryGetClaimFromJwtToken: Found claim. ClaimType: '{0}', Value: '{1}'.`
- `0x1a57f`: `TryGetClaimFromJwtToken: Unexpected exception. Exception: '{0}', ClaimType: '{1}'.`

## pseudocode

```c

```

## disassembly

```asm
0x1a4c0  ldc.i4.0
0x1a4c1  stloc.0
0x1a4c2  ldarg.3
0x1a4c3  ldnull
0x1a4c4  stind.ref
0x1a4c5  ldarg.1
0x1a4c6  brtrue.s loc_1A4E3
0x1a4c8  ldc.i4   0x1405313
0x1a4cd  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1a4d2  ldc.i4.s 0xA
0x1a4d4  ldstr    aTrygetclaimfro// "TryGetClaimFromJwtToken: Token is null."
0x1a4d9  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1a4de  br       loc_1A56B
0x1a4e3  ldarg.1
0x1a4e4  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Claims()
0x1a4e9  brtrue.s loc_1A503
0x1a4eb  ldc.i4   0x1405314
0x1a4f0  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1a4f5  ldc.i4.s 0xA
0x1a4f7  ldstr    aTrygetclaimfro_0// "TryGetClaimFromJwtToken: No claims avai"...
0x1a4fc  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1a501  br.s     loc_1A56B
0x1a503  ldarg.1
0x1a504  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Claims()
0x1a509  ldarg.2
0x1a50a  call     class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenExtensions::GetSingleClaim(class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> self, string claimType)
0x1a50f  dup
0x1a510  stloc.1
0x1a511  brtrue.s loc_1A537
0x1a513  ldc.i4   0x1405315
0x1a518  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1a51d  ldc.i4.s 0x64
0x1a51f  ldstr    aTrygetclaimfro_1// "TryGetClaimFromJwtToken: Did not find c"...
0x1a524  ldc.i4.1
0x1a525  newarr   [mscorlib]System.Object
0x1a52a  stloc.3
0x1a52b  ldloc.3
0x1a52c  ldc.i4.0
0x1a52d  ldarg.2
0x1a52e  stelem.ref
0x1a52f  ldloc.3
0x1a530  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1a535  br.s     loc_1A56B
0x1a537  ldc.i4.1
0x1a538  stloc.0
0x1a539  ldarg.3
0x1a53a  ldloc.1
0x1a53b  stind.ref
0x1a53c  ldc.i4   0x1405316
0x1a541  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1a546  ldc.i4.s 0x64
0x1a548  ldstr    aTrygetclaimfro_2// "TryGetClaimFromJwtToken: Found claim. C"...
0x1a54d  ldc.i4.2
0x1a54e  newarr   [mscorlib]System.Object
0x1a553  stloc.s  4
0x1a555  ldloc.s  4
0x1a557  ldc.i4.0
0x1a558  ldarg.2
0x1a559  stelem.ref
0x1a55a  ldloc.s  4
0x1a55c  ldc.i4.1
0x1a55d  ldloc.1
0x1a55e  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_Value()
0x1a563  stelem.ref
0x1a564  ldloc.s  4
0x1a566  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1a56b  leave.s  loc_1A5A4
0x1a56d  stloc.2
0x1a56e  ldc.i4.0
0x1a56f  stloc.0
0x1a570  ldarg.3
0x1a571  ldnull
0x1a572  stind.ref
0x1a573  ldc.i4   0x1405317
0x1a578  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1a57d  ldc.i4.s 0xA
0x1a57f  ldstr    aTrygetclaimfro_3// "TryGetClaimFromJwtToken: Unexpected exc"...
0x1a584  ldc.i4.2
0x1a585  newarr   [mscorlib]System.Object
0x1a58a  stloc.s  5
0x1a58c  ldloc.s  5
0x1a58e  ldc.i4.0
0x1a58f  ldloc.2
0x1a590  callvirt instance string [mscorlib]System.Object::ToString()
0x1a595  stelem.ref
0x1a596  ldloc.s  5
0x1a598  ldc.i4.1
0x1a599  ldarg.2
0x1a59a  stelem.ref
0x1a59b  ldloc.s  5
0x1a59d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1a5a2  leave.s  loc_1A5A4
0x1a5a4  ldloc.0
0x1a5a5  ret
```
