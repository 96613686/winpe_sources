# Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::ValidateTokenIssuer

- ea: `0x17070`
- end: `0x1727f`
- name: `Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::ValidateTokenIssuer`
- size: `527`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x16a10`
- `0x181f0`

## callees

- `0x10da0`
- `0x169c0`
- `0x17070`
- `0x17280`
- `0x17440`
- `0x1bf90`
- `0x283e0`

## string_xrefs

- `0x17089`: `token`
- `0x1707f`: `The token is null.`
- `0x170f7`: `Neither the json token nor the json token actor has an issuer.`
- `0x17101`: `Token is not signed`
- `0x1711b`: `Validating json actor token issuer.`
- `0x1721c`: `The actor token's outernameid claim is null or whitespace.`
- `0x1723e`: `The token's nameid doesn't match the actor's outernameid.`
- `0x17248`: `The token's nameid doesn't match the actor's outernameid.`
- `0x17262`: `Validating json token issuer.`

## pseudocode

```c

```

## disassembly

```asm
0x17070  ldarg.1
0x17071  brtrue.s loc_17094
0x17073  ldc.i4   0x6503E3
0x17078  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x1707d  ldc.i4.s 0xA
0x1707f  ldstr    aTheTokenIsNull// "The token is null."
0x17084  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x17089  ldstr    aToken// "token"
0x1708e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x17093  throw
0x17094  call     bool Microsoft.SharePoint.IdentityModel.SPClaimsUtility::IsEnableOldHashedProofTokenFormat()
0x17099  brfalse.s loc_170C8
0x1709b  ldc.i4   0x373
0x170a0  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x170a5  stloc.0
0x170a6  ldloc.0
0x170a7  brfalse.s loc_170C8
0x170a9  ldarg.1
0x170aa  call     bool Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenUtilities::IsHashedProofToken(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken token)
0x170af  brfalse.s loc_170C8
0x170b1  ldc.i4   0x148F8DA
0x170b6  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x170bb  ldc.i4.s 0x32
0x170bd  ldstr    aFoundHashedPro// "Found hashed proof tokem, skipping issu"...
0x170c2  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x170c7  ret
0x170c8  ldarg.1
0x170c9  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_IssuerToken()
0x170ce  brtrue   loc_17253
0x170d3  ldarg.1
0x170d4  callvirt instance class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_ActorToken()
0x170d9  brfalse.s loc_170E8
0x170db  ldarg.1
0x170dc  callvirt instance class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_ActorToken()
0x170e1  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_IssuerToken()
0x170e6  brtrue.s loc_1710C
0x170e8  ldc.i4   0x7CC189
0x170ed  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x170f2  ldc.i4   0xC8
0x170f7  ldstr    aNeitherTheJson// "Neither the json token nor the json tok"...
0x170fc  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x17101  ldstr    aTokenIsNotSign// "Token is not signed"
0x17106  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenException::.ctor(string)
0x1710b  throw
0x1710c  ldc.i4   0x7CC18A
0x17111  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x17116  ldc.i4   0xC8
0x1711b  ldstr    aValidatingJson_0// "Validating json actor token issuer."
0x17120  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x17125  ldarg.0
0x17126  ldarg.1
0x17127  callvirt instance class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_ActorToken()
0x1712c  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_IssuerToken()
0x17131  isinst   [System.IdentityModel]System.IdentityModel.Tokens.X509SecurityToken
0x17136  ldarg.1
0x17137  callvirt instance class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_ActorToken()
0x1713c  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Issuer()
0x17141  call     instance void Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::ValidateTokenIssuer(class [System.IdentityModel]System.IdentityModel.Tokens.X509SecurityToken signingKey, string tokenIssuer)
0x17146  ldnull
0x17147  stloc.1
0x17148  ldarg.1
0x17149  callvirt instance class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_ActorToken()
0x1714e  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Issuer()
0x17153  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x17158  brtrue.s loc_17188
0x1715a  ldarg.1
0x1715b  callvirt instance class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_ActorToken()
0x17160  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Issuer()
0x17165  ldc.i4.1
0x17166  newarr   [mscorlib]System.Char
0x1716b  stloc.s  7
0x1716d  ldloc.s  7
0x1716f  ldc.i4.0
0x17170  ldc.i4.s 0x40
0x17172  stelem.i2
0x17173  ldloc.s  7
0x17175  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x1717a  stloc.2
0x1717b  ldloc.2
0x1717c  ldlen
0x1717d  conv.i4
0x1717e  ldc.i4.0
0x1717f  bgt.s    loc_17184
0x17181  ldnull
0x17182  br.s     loc_17187
0x17184  ldloc.2
0x17185  ldc.i4.0
0x17186  ldelem.ref
0x17187  stloc.1
0x17188  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm::get_Local()
0x1718d  callvirt instance class [System]System.Collections.Generic.ISet`1<int32> [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFarm::get_ServerDebugFlags()
0x17192  ldsfld   int32 Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::AllowClassicWFMToken
0x17197  callvirt instance bool class [mscorlib]System.Collections.Generic.ICollection`1<int32>::Contains(var<u1>)
0x1719c  brtrue   loc_1727E
0x171a1  ldstr    a00000005000000// "00000005-0000-0000-c000-000000000000"
0x171a6  ldloc.1
0x171a7  call     bool [mscorlib]System.String::Equals(string, string)
0x171ac  brfalse  loc_1727E
0x171b1  ldnull
0x171b2  stloc.3
0x171b3  ldnull
0x171b4  stloc.s  4
0x171b6  ldarg.1
0x171b7  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Claims()
0x171bc  brfalse.s loc_171DF
0x171be  ldarg.1
0x171bf  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Claims()
0x171c4  ldstr    aNameid// "nameid"
0x171c9  call     class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenExtensions::GetSingleClaim(class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> self, string claimType)
0x171ce  stloc.s  5
0x171d0  ldloc.s  5
0x171d2  brtrue.s loc_171D7
0x171d4  ldnull
0x171d5  br.s     loc_171DE
0x171d7  ldloc.s  5
0x171d9  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_Value()
0x171de  stloc.3
0x171df  ldarg.1
0x171e0  callvirt instance class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_ActorToken()
0x171e5  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Claims()
0x171ea  brfalse.s loc_17213
0x171ec  ldarg.1
0x171ed  callvirt instance class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_ActorToken()
0x171f2  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Claims()
0x171f7  ldstr    aOuternameid// "outernameid"
0x171fc  call     class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenExtensions::GetSingleClaim(class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> self, string claimType)
0x17201  stloc.s  6
0x17203  ldloc.s  6
0x17205  brtrue.s loc_1720A
0x17207  ldnull
0x17208  br.s     loc_17211
0x1720a  ldloc.s  6
0x1720c  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_Value()
0x17211  stloc.s  4
0x17213  ldloc.s  4
0x17215  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x1721a  brfalse.s loc_17227
0x1721c  ldstr    aTheActorTokenS// "The actor token's outernameid claim is "...
0x17221  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenException::.ctor(string)
0x17226  throw
0x17227  ldloc.3
0x17228  ldloc.s  4
0x1722a  ldc.i4.4
0x1722b  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x17230  brtrue.s loc_1727E
0x17232  ldc.i4   0x1E246457
0x17237  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x1723c  ldc.i4.s 0xA
0x1723e  ldstr    aTheTokenSNamei// "The token's nameid doesn't match the ac"...
0x17243  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x17248  ldstr    aTheTokenSNamei// "The token's nameid doesn't match the ac"...
0x1724d  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenException::.ctor(string)
0x17252  throw
0x17253  ldc.i4   0x7CC18B
0x17258  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x1725d  ldc.i4   0xC8
0x17262  ldstr    aValidatingJson_1// "Validating json token issuer."
0x17267  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1726c  ldarg.0
0x1726d  ldarg.1
0x1726e  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_IssuerToken()
0x17273  ldarg.1
0x17274  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Issuer()
0x17279  call     instance void Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::ValidateTokenIssuer(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken issuerToken, string tokenIssuer)
0x1727e  ret
```
