# Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenUtilities::ValidateHashedProofTokenAdditionally

- ea: `0x10c30`
- end: `0x10ca2`
- name: `Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenUtilities::ValidateHashedProofTokenAdditionally`
- size: `114`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x5b90`

## callees

- `0x10c30`
- `0x10cb0`

## string_xrefs

- `0x10c33`: `token`
- `0x10c4a`: `[SPIdentityProofTokenUtilities] Validating hashed proof token signature.`
- `0x10c75`: `[SPIdentityProofTokenUtilies] Token is not properly signed.`
- `0x10c91`: `[SPIdentityProofTokenUtilities] Validating token issuer is internal STS.`

## pseudocode

```c

```

## disassembly

```asm
0x10c30  ldarg.0
0x10c31  brtrue.s loc_10C3E
0x10c33  ldstr    aToken// "token"
0x10c38  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x10c3d  throw
0x10c3e  ldc.i4   0x2021D502
0x10c43  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x10c48  ldc.i4.s 0x32
0x10c4a  ldstr    aSpidentityproo_40// "[SPIdentityProofTokenUtilities] Validat"...
0x10c4f  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x10c54  ldarg.0
0x10c55  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_IssuerToken()
0x10c5a  brfalse.s loc_10C69
0x10c5c  ldarg.0
0x10c5d  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_IssuerToken()
0x10c62  isinst   Microsoft.SharePoint.IdentityModel.SPHashedProofSecretSecurityToken
0x10c67  brtrue.s loc_10C85
0x10c69  ldc.i4   0x2021D503
0x10c6e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x10c73  ldc.i4.s 0xA
0x10c75  ldstr    aSpidentityproo_41// "[SPIdentityProofTokenUtilies] Token is "...
0x10c7a  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x10c7f  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPInvalidTokenSignatureOAuthException::.ctor()
0x10c84  throw
0x10c85  ldc.i4   0x2021D504
0x10c8a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x10c8f  ldc.i4.s 0x32
0x10c91  ldstr    aSpidentityproo_42// "[SPIdentityProofTokenUtilities] Validat"...
0x10c96  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x10c9b  ldarg.0
0x10c9c  call     void Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenUtilities::ValidateIssuer(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken token)
0x10ca1  ret
```
