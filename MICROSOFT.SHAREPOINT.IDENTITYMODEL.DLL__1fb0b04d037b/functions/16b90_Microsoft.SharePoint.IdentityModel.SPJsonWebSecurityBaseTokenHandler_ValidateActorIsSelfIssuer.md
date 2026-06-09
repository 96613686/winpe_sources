# Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::ValidateActorIsSelfIssuer

- ea: `0x16b90`
- end: `0x16e75`
- name: `Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::ValidateActorIsSelfIssuer`
- size: `741`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x16a10`

## callees

- `0x14f70`
- `0x15000`
- `0x15090`
- `0x169c0`
- `0x16b90`
- `0x179d0`
- `0x17b50`
- `0x189a0`

## string_xrefs

- `0x16ba9`: `token`
- `0x16bd5`: `token`
- `0x16b9f`: `The token is null.`
- `0x16bca`: `The token is not a JsonWebSecurityToken.`
- `0x16bef`: `The tokenIdentities is null.`
- `0x16bf9`: `tokenIdentities`
- `0x16c18`: `Json token has no identities to validate.`
- `0x16c3a`: `Json token's identity to validate is null.`
- `0x16c5b`: `Json token's identity to validate has null actor.`
- `0x16c9d`: `Json token issuer is not of type SPTrustedSecurityTokenService. IssuerName: '{0}', ActualType: '{1}'.`
- `0x16cf6`: `Json token issuer is not self issuer. IssuerName: '{0}'.`
- `0x16d52`: `This is a preauth, an appplususerwopi or apponly wopi token. Therefore we will not try to match actorName and token issuer.`
- `0x16d7a`: `This is a AppOnly proof token. Therefore we will not try to match actorName and token issuer.`
- `0x16d9e`: `This is a loopback token. Therefore we will not try to match actorName and token issuer.`
- `0x16dc6`: `Json token's identity actor doesn't have NameId!`
- `0x16e14`: `Json token issuer Issuer is marked as self issuer but is asserting a different NameId. IssuerName: '{0}', NameId: '{1}', TokenIssuer: '{2}'.`

## pseudocode

```c

```

## disassembly

```asm
0x16b90  ldarg.1
0x16b91  brtrue.s loc_16BB4
0x16b93  ldc.i4   0x6503DF
0x16b98  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x16b9d  ldc.i4.s 0xA
0x16b9f  ldstr    aTheTokenIsNull// "The token is null."
0x16ba4  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x16ba9  ldstr    aToken// "token"
0x16bae  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x16bb3  throw
0x16bb4  ldarg.1
0x16bb5  isinst   [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken
0x16bba  stloc.0
0x16bbb  ldloc.0
0x16bbc  brtrue.s loc_16BE0
0x16bbe  ldc.i4   0x6503E0
0x16bc3  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x16bc8  ldc.i4.s 0xA
0x16bca  ldstr    aTheTokenIsNotA_3// "The token is not a JsonWebSecurityToken"...
0x16bcf  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x16bd4  ldnull
0x16bd5  ldstr    aToken// "token"
0x16bda  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x16bdf  throw
0x16be0  ldarg.2
0x16be1  brtrue.s loc_16C04
0x16be3  ldc.i4   0x6503E1
0x16be8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x16bed  ldc.i4.s 0xA
0x16bef  ldstr    aTheTokenidenti// "The tokenIdentities is null."
0x16bf4  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x16bf9  ldstr    aTokenidentitie// "tokenIdentities"
0x16bfe  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x16c03  throw
0x16c04  ldarg.2
0x16c05  callvirt instance int32 [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Count()
0x16c0a  brtrue.s loc_16C23
0x16c0c  ldc.i4   0x1DC7C7
0x16c11  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x16c16  ldc.i4.s 0x64
0x16c18  ldstr    aJsonTokenHasNo// "Json token has no identities to validat"...
0x16c1d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x16c22  ret
0x16c23  ldarg.2
0x16c24  ldc.i4.0
0x16c25  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Item(int32)
0x16c2a  stloc.1
0x16c2b  ldloc.1
0x16c2c  brtrue.s loc_16C45
0x16c2e  ldc.i4   0x1DC7C8
0x16c33  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x16c38  ldc.i4.s 0x64
0x16c3a  ldstr    aJsonTokenSIden// "Json token's identity to validate is nu"...
0x16c3f  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x16c44  ret
0x16c45  ldloc.1
0x16c46  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Actor()
0x16c4b  stloc.2
0x16c4c  ldloc.2
0x16c4d  brtrue.s loc_16C66
0x16c4f  ldc.i4   0x1DC7C9
0x16c54  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x16c59  ldc.i4.s 0x64
0x16c5b  ldstr    aJsonTokenSIden_0// "Json token's identity to validate has n"...
0x16c60  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x16c65  ret
0x16c66  ldloc.2
0x16c67  call     string Microsoft.SharePoint.IdentityModel.SPClaimsIdentityExtensions::GetIssuerName(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity identity)
0x16c6c  stloc.3
0x16c6d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_LocalOrThrow()
0x16c72  stloc.s  4
0x16c74  ldloc.s  4
0x16c76  ldloc.3
0x16c77  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPLoginProviderBase [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::GetLoginProviderByName(string)
0x16c7c  stloc.s  5
0x16c7e  ldloc.s  5
0x16c80  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedSecurityTokenService
0x16c85  stloc.s  6
0x16c87  ldnull
0x16c88  ldloc.s  6
0x16c8a  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x16c8f  brfalse.s loc_16CE1
0x16c91  ldc.i4   0x1DC7CA
0x16c96  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x16c9b  ldc.i4.s 0xA
0x16c9d  ldstr    aJsonTokenIssue// "Json token issuer is not of type SPTrus"...
0x16ca2  ldc.i4.2
0x16ca3  newarr   [mscorlib]System.Object
0x16ca8  stloc.s  0xA
0x16caa  ldloc.s  0xA
0x16cac  ldc.i4.0
0x16cad  ldloc.3
0x16cae  stelem.ref
0x16caf  ldloc.s  0xA
0x16cb1  ldc.i4.1
0x16cb2  ldloc.s  5
0x16cb4  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x16cb9  callvirt instance string [mscorlib]System.Object::ToString()
0x16cbe  stelem.ref
0x16cbf  ldloc.s  0xA
0x16cc1  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x16cc6  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16ccb  ldstr    aTypenotsupport// "TypeNotSupported"
0x16cd0  ldc.i4.0
0x16cd1  newarr   [mscorlib]System.Object
0x16cd6  call     string [Microsoft.SharePoint]Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo, string, object[])
0x16cdb  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x16ce0  throw
0x16ce1  ldloc.s  6
0x16ce3  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedSecurityTokenService::get_IsSelfIssuer()
0x16ce8  brtrue.s loc_16D10
0x16cea  ldc.i4   0x1DC7CB
0x16cef  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x16cf4  ldc.i4.s 0x32
0x16cf6  ldstr    aJsonTokenIssue_0// "Json token issuer is not self issuer. I"...
0x16cfb  ldc.i4.1
0x16cfc  newarr   [mscorlib]System.Object
0x16d01  stloc.s  0xB
0x16d03  ldloc.s  0xB
0x16d05  ldc.i4.0
0x16d06  ldloc.3
0x16d07  stelem.ref
0x16d08  ldloc.s  0xB
0x16d0a  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x16d0f  ret
0x16d10  ldc.i4   0x2B3D
0x16d15  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x16d1a  stloc.s  7
0x16d1c  ldc.i4   0x374E
0x16d21  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x16d26  pop
0x16d27  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPWOPIHost::get_IsPreAuthWopiFeatureEnabled()
0x16d2c  brfalse.s loc_16D5D
0x16d2e  ldloc.0
0x16d2f  call     bool Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::IsPreAuthWopiToken(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken token)
0x16d34  brtrue.s loc_16D46
0x16d36  ldloc.0
0x16d37  call     bool Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::IsAppPlusUserWopiToken(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken token)
0x16d3c  brtrue.s loc_16D46
0x16d3e  ldloc.0
0x16d3f  call     bool Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::IsAppOnlyWopiToken(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken token)
0x16d44  brfalse.s loc_16D5D
0x16d46  ldc.i4   0x100184F
0x16d4b  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x16d50  ldc.i4.s 0x32
0x16d52  ldstr    aThisIsAPreauth// "This is a preauth, an appplususerwopi o"...
0x16d57  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x16d5c  ret
0x16d5d  ldloc.s  7
0x16d5f  brfalse.s loc_16D85
0x16d61  ldloc.0
0x16d62  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Claims()
0x16d67  call     bool Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::IsAppOnlyProofToken(class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> claims)
0x16d6c  brfalse.s loc_16D85
0x16d6e  ldc.i4   0x146329B
0x16d73  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x16d78  ldc.i4.s 0x32
0x16d7a  ldstr    aThisIsAApponly// "This is a AppOnly proof token. Therefor"...
0x16d7f  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x16d84  ret
0x16d85  ldloc.0
0x16d86  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Claims()
0x16d8b  call     bool Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::IsLoopbackToken(class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> claims)
0x16d90  brfalse.s loc_16DA9
0x16d92  ldc.i4   0x164F39E
0x16d97  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x16d9c  ldc.i4.s 0x32
0x16d9e  ldstr    aThisIsALoopbac// "This is a loopback token. Therefore we "...
0x16da3  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x16da8  ret
0x16da9  ldloc.2
0x16daa  call     class [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPIdentityClaimSet [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPIdentityClaimSet::CreateFromClaimsIdentity(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity)
0x16daf  stloc.s  8
0x16db1  ldloc.s  8
0x16db3  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPIdentityClaimSet::get_NameId()
0x16db8  brtrue.s loc_16DEB
0x16dba  ldc.i4   0x1DC7CC
0x16dbf  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x16dc4  ldc.i4.s 0xA
0x16dc6  ldstr    aJsonTokenSIden_1// "Json token's identity actor doesn't hav"...
0x16dcb  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x16dd0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x16dd5  ldstr    aActordoesnotha// "ActorDoesNotHaveNameIdentifier"
0x16dda  ldc.i4.0
0x16ddb  newarr   [mscorlib]System.Object
0x16de0  call     string [Microsoft.SharePoint]Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo, string, object[])
0x16de5  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x16dea  throw
0x16deb  ldloc.s  8
0x16ded  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPIdentityClaimSet::get_NameId()
0x16df2  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x16df7  stloc.s  9
0x16df9  ldloc.s  9
0x16dfb  ldloc.0
0x16dfc  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Issuer()
0x16e01  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedNameIdComparer::Matches(string, string)
0x16e06  brtrue.s loc_16E74
0x16e08  ldc.i4   0x1DC7CD
0x16e0d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x16e12  ldc.i4.s 0x32
0x16e14  ldstr    aJsonTokenIssue_1// "Json token issuer Issuer is marked as s"...
0x16e19  ldc.i4.3
0x16e1a  newarr   [mscorlib]System.Object
0x16e1f  stloc.s  0xC
0x16e21  ldloc.s  0xC
0x16e23  ldc.i4.0
0x16e24  ldloc.3
0x16e25  stelem.ref
0x16e26  ldloc.s  0xC
0x16e28  ldc.i4.1
0x16e29  ldloc.s  8
0x16e2b  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPIdentityClaimSet::get_NameId()
0x16e30  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x16e35  dup
0x16e36  brtrue.s loc_16E3E
0x16e38  pop
0x16e39  ldsfld   string [mscorlib]System.String::Empty
0x16e3e  stelem.ref
0x16e3f  ldloc.s  0xC
0x16e41  ldc.i4.2
0x16e42  ldloc.0
0x16e43  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Issuer()
0x16e48  dup
0x16e49  brtrue.s loc_16E51
0x16e4b  pop
0x16e4c  ldsfld   string [mscorlib]System.String::Empty
0x16e51  stelem.ref
0x16e52  ldloc.s  0xC
0x16e54  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x16e59  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x16e5e  ldstr    aIssueridentity// "IssuerIdentityDoesNotMatchActor"
0x16e63  ldc.i4.0
0x16e64  newarr   [mscorlib]System.Object
0x16e69  call     string [Microsoft.SharePoint]Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo, string, object[])
0x16e6e  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenException::.ctor(string)
0x16e73  throw
0x16e74  ret
```
