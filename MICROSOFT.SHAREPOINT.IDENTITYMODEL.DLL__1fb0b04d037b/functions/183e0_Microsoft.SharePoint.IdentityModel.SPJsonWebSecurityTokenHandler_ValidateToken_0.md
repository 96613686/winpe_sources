# Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::ValidateToken_0

- ea: `0x183e0`
- end: `0x1852c`
- name: `Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::ValidateToken_0`
- size: `332`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x5b90`

## callees

- `0x16a10`
- `0x18180`
- `0x183e0`
- `0x18530`
- `0x186e0`
- `0x189a0`
- `0x19090`

## string_xrefs

- `0x183f9`: `token`
- `0x183ef`: `The token is null.`
- `0x184f9`: `TokenNotIssuedByInternalSTS`
- `0x18418`: `The rawProofToken is null.`
- `0x18423`: `rawProofToken`
- `0x1844a`: `Json token has no identities, no proof token validation required.`
- `0x1847c`: `Json token has no proof key requirement present, returning the result.`
- `0x184a1`: `Json token has no proof key claim is empty.`
- `0x184ea`: `Json token isn't internally minted, proof keys disallowed.`

## pseudocode

```c

```

## disassembly

```asm
0x183e0  ldarg.1
0x183e1  brtrue.s loc_18404
0x183e3  ldc.i4   0x65040D
0x183e8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::get_Category()
0x183ed  ldc.i4.s 0xA
0x183ef  ldstr    aTheTokenIsNull// "The token is null."
0x183f4  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x183f9  ldstr    aToken// "token"
0x183fe  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x18403  throw
0x18404  ldarg.2
0x18405  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x1840a  brfalse.s loc_1842E
0x1840c  ldc.i4   0x65040E
0x18411  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::get_Category()
0x18416  ldc.i4.s 0xA
0x18418  ldstr    aTheRawprooftok// "The rawProofToken is null."
0x1841d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x18422  ldnull
0x18423  ldstr    aRawprooftoken// "rawProofToken"
0x18428  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x1842d  throw
0x1842e  ldarg.0
0x1842f  ldarg.1
0x18430  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::ValidateToken(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken token)
0x18435  stloc.0
0x18436  ldloc.0
0x18437  callvirt instance int32 [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Count()
0x1843c  brtrue.s loc_18456
0x1843e  ldc.i4   0x142116
0x18443  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::get_Category()
0x18448  ldc.i4.s 0x64
0x1844a  ldstr    aJsonTokenHasNo_0// "Json token has no identities, no proof "...
0x1844f  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x18454  ldloc.0
0x18455  ret
0x18456  ldloc.0
0x18457  ldc.i4.0
0x18458  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Item(int32)
0x1845d  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x18462  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimTypes::get_ProofKey()
0x18467  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimCollectionExtensions::GetSingleClaim(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection, string)
0x1846c  stloc.1
0x1846d  ldloc.1
0x1846e  brtrue.s loc_18488
0x18470  ldc.i4   0x142117
0x18475  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::get_Category()
0x1847a  ldc.i4.s 0x64
0x1847c  ldstr    aJsonTokenHasNo_1// "Json token has no proof key requirement"...
0x18481  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x18486  ldloc.0
0x18487  ret
0x18488  ldloc.1
0x18489  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x1848e  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x18493  brfalse.s loc_184C6
0x18495  ldc.i4   0x142118
0x1849a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::get_Category()
0x1849f  ldc.i4.s 0xA
0x184a1  ldstr    aJsonTokenHasNo_2// "Json token has no proof key claim is em"...
0x184a6  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x184ab  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x184b0  ldstr    aThumbrpintmiss// "ThumbrpintMissing"
0x184b5  ldc.i4.0
0x184b6  newarr   [mscorlib]System.Object
0x184bb  call     string [Microsoft.SharePoint]Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo, string, object[])
0x184c0  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x184c5  throw
0x184c6  ldstr    aSharepoint// "SharePoint"
0x184cb  ldloc.0
0x184cc  ldc.i4.0
0x184cd  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Item(int32)
0x184d2  call     string Microsoft.SharePoint.IdentityModel.SPClaimsIdentityExtensions::GetIssuerName(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity identity)
0x184d7  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x184dc  brfalse.s loc_1850F
0x184de  ldc.i4   0x142119
0x184e3  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::get_Category()
0x184e8  ldc.i4.s 0x64
0x184ea  ldstr    aJsonTokenIsnTI// "Json token isn't internally minted, pro"...
0x184ef  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x184f4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x184f9  ldstr    aTokennotissued// "TokenNotIssuedByInternalSTS"
0x184fe  ldc.i4.0
0x184ff  newarr   [mscorlib]System.Object
0x18504  call     string [Microsoft.SharePoint]Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo, string, object[])
0x18509  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1850e  throw
0x1850f  ldarg.2
0x18510  ldloc.1
0x18511  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x18516  call     class Microsoft.SharePoint.IdentityModel.SPProofTokenContext Microsoft.SharePoint.IdentityModel.SPProofTokenContext::FromRawToken(string proofToken, string encodedThumbprint)
0x1851b  stloc.2
0x1851c  ldloc.0
0x1851d  ldloc.2
0x1851e  call     void Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::ValidateActorMatchesProofKey(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection identities, class Microsoft.SharePoint.IdentityModel.SPProofTokenContext proofToken)
0x18523  ldarg.0
0x18524  ldloc.2
0x18525  call     instance void Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::ValidateProofToken(class Microsoft.SharePoint.IdentityModel.SPProofTokenContext proofToken)
0x1852a  ldloc.0
0x1852b  ret
```
