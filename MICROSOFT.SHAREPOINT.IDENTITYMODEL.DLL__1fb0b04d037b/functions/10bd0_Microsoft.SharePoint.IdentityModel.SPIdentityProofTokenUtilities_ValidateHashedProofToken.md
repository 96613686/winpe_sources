# Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenUtilities::ValidateHashedProofToken

- ea: `0x10bd0`
- end: `0x10c2b`
- name: `Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenUtilities::ValidateHashedProofToken`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x5b90`

## callees

- `0x10bd0`
- `0x10cb0`
- `0x10d00`

## string_xrefs

- `0x10bd3`: `token`
- `0x10be6`: `rawToken`
- `0x10bfd`: `SPApplicationAuthenticationModule: Validing hashed proof token signature.`
- `0x10c1a`: `SPApplicationAuthenticationModule: Validing token issuer is internal STS.`

## pseudocode

```c

```

## disassembly

```asm
0x10bd0  ldarg.0
0x10bd1  brtrue.s loc_10BDE
0x10bd3  ldstr    aToken// "token"
0x10bd8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x10bdd  throw
0x10bde  ldarg.1
0x10bdf  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x10be4  brfalse.s loc_10BF1
0x10be6  ldstr    aRawtoken// "rawToken"
0x10beb  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x10bf0  throw
0x10bf1  ldc.i4   0x148F8D5
0x10bf6  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x10bfb  ldc.i4.s 0x32
0x10bfd  ldstr    aSpapplicationa_109// "SPApplicationAuthenticationModule: Vali"...
0x10c02  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x10c07  ldarg.0
0x10c08  ldarg.1
0x10c09  call     void Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenUtilities::ValidateSignature(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken token, string rawToken)
0x10c0e  ldc.i4   0x148F8D6
0x10c13  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x10c18  ldc.i4.s 0x32
0x10c1a  ldstr    aSpapplicationa_110// "SPApplicationAuthenticationModule: Vali"...
0x10c1f  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x10c24  ldarg.0
0x10c25  call     void Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenUtilities::ValidateIssuer(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken token)
0x10c2a  ret
```
