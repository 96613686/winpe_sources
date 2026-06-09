# Microsoft.SharePoint.IdentityModel.SPAuthenticationAlgorithmValidator::DoesTokenHaveValidAlgorithm

- ea: `0x9970`
- end: `0x9a79`
- name: `Microsoft.SharePoint.IdentityModel.SPAuthenticationAlgorithmValidator::DoesTokenHaveValidAlgorithm`
- size: `265`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x98f0`

## callees

- `0x9970`
- `0x9a80`
- `0x9ab0`
- `0x9b90`

## string_xrefs

- `0x9991`: `incomingToken`
- `0x9986`: `The token is not a JSON web security token.`
- `0x99b2`: `The token is not a JSON web security token.`
- `0x99bc`: `The token does not have valid headers.`
- `0x99de`: `The token has a valid algorithm in header.`
- `0x99fe`: `The actor token must have a valid algorithm in header.`
- `0x9a21`: `The asserted or internally transformed token does not have a valid algorithm, actor token algorithm is already validated.`
- `0x9a51`: `The ACS token has a valid algorithm in header.`
- `0x9a6b`: `The token is not an asserted token and found .`

## pseudocode

```c

```

## disassembly

```asm
0x9970  ldarg.1
0x9971  isinst   [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken
0x9976  stloc.0
0x9977  ldloc.0
0x9978  brtrue.s loc_999C
0x997a  ldc.i4   0x20220512
0x997f  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x9984  ldc.i4.s 0xA
0x9986  ldstr    aTheTokenIsNotA_0// "The token is not a JSON web security to"...
0x998b  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x9990  ldnull
0x9991  ldstr    aIncomingtoken// "incomingToken"
0x9996  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x999b  throw
0x999c  ldloc.0
0x999d  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::CreateHeaderClaims()
0x99a2  stloc.1
0x99a3  ldloc.1
0x99a4  brtrue.s loc_99C7
0x99a6  ldc.i4   0x20220513
0x99ab  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x99b0  ldc.i4.s 0xA
0x99b2  ldstr    aTheTokenIsNotA_0// "The token is not a JSON web security to"...
0x99b7  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x99bc  ldstr    aTheTokenDoesNo_0// "The token does not have valid headers."
0x99c1  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0x99c6  throw
0x99c7  ldc.i4.0
0x99c8  stloc.2
0x99c9  ldarg.0
0x99ca  ldloc.1
0x99cb  call     instance bool Microsoft.SharePoint.IdentityModel.SPAuthenticationAlgorithmValidator::HasValidAlgorithm(class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> headers)
0x99d0  brfalse.s loc_99EF
0x99d2  ldc.i4   0x20220514
0x99d7  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x99dc  ldc.i4.s 0x64
0x99de  ldstr    aTheTokenHasAVa// "The token has a valid algorithm in head"...
0x99e3  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x99e8  ldc.i4.1
0x99e9  stloc.2
0x99ea  br       loc_9A77
0x99ef  ldarg.2
0x99f0  brfalse.s loc_9A0C
0x99f2  ldc.i4   0x20220515
0x99f7  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x99fc  ldc.i4.s 0xA
0x99fe  ldstr    aTheActorTokenM// "The actor token must have a valid algor"...
0x9a03  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x9a08  ldc.i4.0
0x9a09  stloc.2
0x9a0a  br.s     loc_9A77
0x9a0c  ldarg.0
0x9a0d  ldloc.0
0x9a0e  call     instance bool Microsoft.SharePoint.IdentityModel.SPAuthenticationAlgorithmValidator::IsAssertedOrInternallyTransformedToken(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken securityToken)
0x9a13  brfalse.s loc_9A2F
0x9a15  ldc.i4   0x20220516
0x9a1a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x9a1f  ldc.i4.s 0x64
0x9a21  ldstr    aTheAssertedOrI// "The asserted or internally transformed "...
0x9a26  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x9a2b  ldc.i4.1
0x9a2c  stloc.2
0x9a2d  br.s     loc_9A77
0x9a2f  ldloc.0
0x9a30  callvirt instance class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_ActorToken()
0x9a35  brfalse.s loc_9A5F
0x9a37  ldarg.0
0x9a38  ldloc.0
0x9a39  callvirt instance class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_ActorToken()
0x9a3e  call     instance bool Microsoft.SharePoint.IdentityModel.SPAuthenticationAlgorithmValidator::IsAcsToken(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken jsonToken)
0x9a43  brfalse.s loc_9A5F
0x9a45  ldc.i4   0x2021F693
0x9a4a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x9a4f  ldc.i4.s 0x64
0x9a51  ldstr    aTheAcsTokenHas// "The ACS token has a valid algorithm in "...
0x9a56  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x9a5b  ldc.i4.1
0x9a5c  stloc.2
0x9a5d  br.s     loc_9A77
0x9a5f  ldc.i4   0x20220517
0x9a64  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x9a69  ldc.i4.s 0xA
0x9a6b  ldstr    aTheTokenIsNotA_1// "The token is not an asserted token and "...
0x9a70  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x9a75  ldc.i4.0
0x9a76  stloc.2
0x9a77  ldloc.2
0x9a78  ret
```
