# Microsoft.SharePoint.IdentityModel.SPAuthenticationAlgorithmValidator::IsAssertedOrInternallyTransformedToken

- ea: `0x9ab0`
- end: `0x9b85`
- name: `Microsoft.SharePoint.IdentityModel.SPAuthenticationAlgorithmValidator::IsAssertedOrInternallyTransformedToken`
- size: `213`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x9970`

## callees

- `0x9ab0`
- `0x1bf90`

## string_xrefs

- `0x9ad3`: `securityToken`
- `0x9b44`: `service_asserted_app_v1`
- `0x9ac8`: `The token is not a JSON web security token.`
- `0x9af2`: `The token does not have an actor token, therefore it cannot be an asserted token.`
- `0x9b5d`: `The token is application asserted user or service asserted application token.`
- `0x9b77`: `The version does not indicate the asserted token type.`

## pseudocode

```c

```

## disassembly

```asm
0x9ab0  ldc.i4.0
0x9ab1  stloc.0
0x9ab2  ldarg.1
0x9ab3  isinst   [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken
0x9ab8  stloc.1
0x9ab9  ldloc.1
0x9aba  brtrue.s loc_9ADE
0x9abc  ldc.i4   0x2021F694
0x9ac1  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x9ac6  ldc.i4.s 0xA
0x9ac8  ldstr    aTheTokenIsNotA_0// "The token is not a JSON web security to"...
0x9acd  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x9ad2  ldnull
0x9ad3  ldstr    aSecuritytoken// "securityToken"
0x9ad8  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x9add  throw
0x9ade  ldloc.1
0x9adf  callvirt instance class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_ActorToken()
0x9ae4  brtrue.s loc_9B03
0x9ae6  ldc.i4   0x2021F695
0x9aeb  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x9af0  ldc.i4.s 0x64
0x9af2  ldstr    aTheTokenDoesNo_1// "The token does not have an actor token,"...
0x9af7  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x9afc  ldc.i4.0
0x9afd  stloc.0
0x9afe  br       loc_9B83
0x9b03  ldnull
0x9b04  stloc.2
0x9b05  ldloc.1
0x9b06  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Claims()
0x9b0b  brfalse.s loc_9B35
0x9b0d  ldloc.1
0x9b0e  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Claims()
0x9b13  ldstr    aVer// "ver"
0x9b18  call     class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenExtensions::GetSingleClaim(class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> self, string claimType)
0x9b1d  brfalse.s loc_9B35
0x9b1f  ldloc.1
0x9b20  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Claims()
0x9b25  ldstr    aVer// "ver"
0x9b2a  call     class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenExtensions::GetSingleClaim(class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> self, string claimType)
0x9b2f  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_Value()
0x9b34  stloc.2
0x9b35  ldloc.2
0x9b36  ldstr    aAppAssertedUse// "app_asserted_user_v1"
0x9b3b  ldc.i4.5
0x9b3c  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x9b41  brtrue.s loc_9B51
0x9b43  ldloc.2
0x9b44  ldstr    aServiceAsserte// "service_asserted_app_v1"
0x9b49  ldc.i4.5
0x9b4a  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x9b4f  brfalse.s loc_9B6B
0x9b51  ldc.i4   0x2021F141
0x9b56  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x9b5b  ldc.i4.s 0x64
0x9b5d  ldstr    aTheTokenIsAppl// "The token is application asserted user "...
0x9b62  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x9b67  ldc.i4.1
0x9b68  stloc.0
0x9b69  br.s     loc_9B83
0x9b6b  ldc.i4   0x2021F144
0x9b70  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x9b75  ldc.i4.s 0x64
0x9b77  ldstr    aTheVersionDoes// "The version does not indicate the asser"...
0x9b7c  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x9b81  ldc.i4.0
0x9b82  stloc.0
0x9b83  ldloc.0
0x9b84  ret
```
