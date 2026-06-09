# Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::GetIssuerName

- ea: `0x17580`
- end: `0x176d5`
- name: `Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::GetIssuerName`
- size: `341`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x10da0`
- `0x169c0`
- `0x17580`
- `0x17890`
- `0x17d40`

## string_xrefs

- `0x17599`: `token`
- `0x1758f`: `The token is null.`
- `0x175c6`: `Found hashed proof token, returning token issuer.`
- `0x17603`: `The token hanlder configuration doesn't allow for json tokens without signatures.`
- `0x1762c`: `Actor token doesn't exist on json token.`
- `0x1765a`: `The token hanlder configuration doesn't allow for json actor tokens without signatures.`
- `0x17688`: `The json actor token is not for an identity trusted for delegation.`
- `0x176b1`: `The json token issuer name is emtpy.`

## pseudocode

```c

```

## disassembly

```asm
0x17580  ldarg.1
0x17581  brtrue.s loc_175A4
0x17583  ldc.i4   0x650407
0x17588  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x1758d  ldc.i4.s 0xA
0x1758f  ldstr    aTheTokenIsNull// "The token is null."
0x17594  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x17599  ldstr    aToken// "token"
0x1759e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x175a3  throw
0x175a4  ldc.i4   0x373
0x175a9  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x175ae  stloc.0
0x175af  ldloc.0
0x175b0  brfalse.s loc_175D7
0x175b2  ldarg.1
0x175b3  call     bool Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenUtilities::IsHashedProofToken(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken token)
0x175b8  brfalse.s loc_175D7
0x175ba  ldc.i4   0x148F8DB
0x175bf  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x175c4  ldc.i4.s 0x32
0x175c6  ldstr    aFoundHashedPro_0// "Found hashed proof token, returning tok"...
0x175cb  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x175d0  ldarg.1
0x175d1  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Issuer()
0x175d6  ret
0x175d7  ldarg.1
0x175d8  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_IssuerToken()
0x175dd  brtrue   loc_176CD
0x175e2  ldarg.0
0x175e3  call     instance class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityTokenRequirement [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityTokenHandler::get_JsonWebSecurityTokenRequirement()
0x175e8  brfalse.s loc_175F7
0x175ea  ldarg.0
0x175eb  call     instance class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityTokenRequirement [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityTokenHandler::get_JsonWebSecurityTokenRequirement()
0x175f0  callvirt instance bool [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityTokenRequirement::get_AllowActorToken()
0x175f5  brtrue.s loc_17618
0x175f7  ldc.i4   0x20B1DE
0x175fc  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x17601  ldc.i4.s 0xA
0x17603  ldstr    aTheTokenHanlde// "The token hanlder configuration doesn't"...
0x17608  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1760d  ldstr    aIssuerisnottru// "IssuerIsNotTrusted"
0x17612  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenException::.ctor(string)
0x17617  throw
0x17618  ldarg.1
0x17619  callvirt instance class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_ActorToken()
0x1761e  brtrue.s loc_17641
0x17620  ldc.i4   0x20B1DF
0x17625  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x1762a  ldc.i4.s 0x14
0x1762c  ldstr    aActorTokenDoes// "Actor token doesn't exist on json token"...
0x17631  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x17636  ldstr    aIssuerisnottru// "IssuerIsNotTrusted"
0x1763b  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenException::.ctor(string)
0x17640  throw
0x17641  ldarg.1
0x17642  callvirt instance class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_ActorToken()
0x17647  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_IssuerToken()
0x1764c  brtrue.s loc_1766F
0x1764e  ldc.i4   0x20B1E0
0x17653  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x17658  ldc.i4.s 0x14
0x1765a  ldstr    aTheTokenHanlde_0// "The token hanlder configuration doesn't"...
0x1765f  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x17664  ldstr    aIssuerisnottru// "IssuerIsNotTrusted"
0x17669  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenException::.ctor(string)
0x1766e  throw
0x1766f  ldarg.1
0x17670  callvirt instance class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_ActorToken()
0x17675  call     bool Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::IsTrustedForDelegation(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken identity)
0x1767a  brtrue.s loc_17698
0x1767c  ldc.i4   0x20B1E1
0x17681  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x17686  ldc.i4.s 0x14
0x17688  ldstr    aTheJsonActorTo// "The json actor token is not for an iden"...
0x1768d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x17692  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPActorNotTrustedForDelegationOAuthException::.ctor()
0x17697  throw
0x17698  ldarg.1
0x17699  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Issuer()
0x1769e  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x176a3  brfalse.s loc_176C6
0x176a5  ldc.i4   0x20B1E2
0x176aa  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x176af  ldc.i4.s 0xA
0x176b1  ldstr    aTheJsonTokenIs// "The json token issuer name is emtpy."
0x176b6  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x176bb  ldstr    aIssuerisnottru// "IssuerIsNotTrusted"
0x176c0  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenException::.ctor(string)
0x176c5  throw
0x176c6  ldarg.1
0x176c7  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Issuer()
0x176cc  ret
0x176cd  ldarg.0
0x176ce  ldarg.1
0x176cf  call     instance string Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::GetIssuerNameFromIssuerToken(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken token)
0x176d4  ret
```
