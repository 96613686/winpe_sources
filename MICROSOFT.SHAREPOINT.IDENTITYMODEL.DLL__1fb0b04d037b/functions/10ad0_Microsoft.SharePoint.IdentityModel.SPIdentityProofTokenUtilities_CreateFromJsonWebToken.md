# Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenUtilities::CreateFromJsonWebToken

- ea: `0x10ad0`
- end: `0x10bc4`
- name: `Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenUtilities::CreateFromJsonWebToken`
- size: `244`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x27a0`
- `0x5b90`

## callees

- `0x8740`
- `0x8800`
- `0x10ad0`
- `0x10de0`

## string_xrefs

- `0x10ad9`: `proofTokenString`
- `0x10aed`: `identityTokenString`
- `0x10b15`: `CreateFromJsonWebToken: Proof token is not a valid JWT string.`
- `0x10b1f`: `Proof token is not JWT`
- `0x10b41`: `CreateFromJsonWebToken: Identity token is not a valid JWT string.`
- `0x10b4b`: `Identity token is not JWT`
- `0x10b90`: `CreateFromJsonWebToken: Created identity didn't pass audience validation. Exception: {0}`
- `0x10bb8`: `CreateFromJsonWebToken: Identity token represents an anonymous request.`

## pseudocode

```c

```

## disassembly

```asm
0x10ad0  ldarg.0
0x10ad1  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x10ad6  brfalse.s loc_10AE4
0x10ad8  ldnull
0x10ad9  ldstr    aProoftokenstri// "proofTokenString"
0x10ade  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x10ae3  throw
0x10ae4  ldarg.1
0x10ae5  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x10aea  brfalse.s loc_10AF8
0x10aec  ldnull
0x10aed  ldstr    aIdentitytokens// "identityTokenString"
0x10af2  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x10af7  throw
0x10af8  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityServices.RequestApplicationSecurityTokenResponse/NonValidatingJsonWebSecurityTokenHandler::.ctor()
0x10afd  stloc.0
0x10afe  ldloc.0
0x10aff  ldarg.0
0x10b00  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityTokenHandler::ReadToken(string)
0x10b05  stloc.1
0x10b06  ldloc.1
0x10b07  brtrue.s loc_10B2A
0x10b09  ldc.i4   0x35F7CB
0x10b0e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x10b13  ldc.i4.s 0xA
0x10b15  ldstr    aCreatefromjson// "CreateFromJsonWebToken: Proof token is "...
0x10b1a  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x10b1f  ldstr    aProofTokenIsNo// "Proof token is not JWT"
0x10b24  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x10b29  throw
0x10b2a  ldloc.0
0x10b2b  ldarg.1
0x10b2c  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityTokenHandler::ReadToken(string)
0x10b31  stloc.2
0x10b32  ldloc.2
0x10b33  brtrue.s loc_10B56
0x10b35  ldc.i4   0x35F7CC
0x10b3a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x10b3f  ldc.i4.s 0xA
0x10b41  ldstr    aCreatefromjson_0// "CreateFromJsonWebToken: Identity token "...
0x10b46  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x10b4b  ldstr    aIdentityTokenI// "Identity token is not JWT"
0x10b50  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x10b55  throw
0x10b56  ldnull
0x10b57  stloc.3
0x10b58  ldloc.2
0x10b59  isinst   [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken
0x10b5e  stloc.s  4
0x10b60  ldloc.s  4
0x10b62  brfalse.s loc_10B6D
0x10b64  ldloc.s  4
0x10b66  call     bool Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenUtilities::IsAnonymousIdentity(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken self)
0x10b6b  brtrue.s loc_10BAC
0x10b6d  ldloc.2
0x10b6e  ldloc.1
0x10b6f  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPIdentityProofToken::.ctor(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken, class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken)
0x10b74  stloc.3
0x10b75  newobj   instance void Microsoft.SharePoint.IdentityModel.SPAudienceValidatingIdentityProofTokenHandler::.ctor()
0x10b7a  ldloc.3
0x10b7b  call     instance void Microsoft.SharePoint.IdentityModel.SPAudienceValidatingIdentityProofTokenHandler::ValidateAudience(class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPIdentityProofToken identityProofToken)
0x10b80  leave.s  loc_10BC2
0x10b82  stloc.s  5
0x10b84  ldc.i4   0x35F7CD
0x10b89  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x10b8e  ldc.i4.s 0x14
0x10b90  ldstr    aCreatefromjson_1// "CreateFromJsonWebToken: Created identit"...
0x10b95  ldc.i4.1
0x10b96  newarr   [mscorlib]System.Object
0x10b9b  stloc.s  6
0x10b9d  ldloc.s  6
0x10b9f  ldc.i4.0
0x10ba0  ldloc.s  5
0x10ba2  stelem.ref
0x10ba3  ldloc.s  6
0x10ba5  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x10baa  rethrow
0x10bac  ldc.i4   0x35F7CE
0x10bb1  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x10bb6  ldc.i4.s 0x32
0x10bb8  ldstr    aCreatefromjson_2// "CreateFromJsonWebToken: Identity token "...
0x10bbd  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x10bc2  ldloc.3
0x10bc3  ret
```
