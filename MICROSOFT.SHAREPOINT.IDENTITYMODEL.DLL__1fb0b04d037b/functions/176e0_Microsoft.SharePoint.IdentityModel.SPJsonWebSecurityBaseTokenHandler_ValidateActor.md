# Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::ValidateActor

- ea: `0x176e0`
- end: `0x17885`
- name: `Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::ValidateActor`
- size: `421`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x16a10`

## callees

- `0x10da0`
- `0x176e0`
- `0x17a00`
- `0x17aa0`
- `0x17b50`
- `0x1bf90`
- `0x2c520`

## string_xrefs

- `0x17735`: `ValidateActor: Actor token should be null for loopback token.`
- `0x1775e`: `ValidateActor: Issuer token is missing.`
- `0x177d8`: `ValidateActor: Can't find actor token claim in ActorToken.`
- `0x17801`: `ValidateActor: Actor token is user token.`

## pseudocode

```c

```

## disassembly

```asm
0x176e0  ldc.i4   0x310C78A
0x176e5  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x176ea  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenHandler()
0x176ef  ldstr    aIdentity// "identity"
0x176f4  ldarg.0
0x176f5  call     void Microsoft.SharePoint.IdentityModel.SPArgumentHelper::LogAndThrowOnNull(unsigned int32 id, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat category, string name, object value)
0x176fa  ldarg.0
0x176fb  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Claims()
0x17700  call     bool Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::IsLoopbackToken(class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> claims)
0x17705  brfalse  loc_177B4
0x1770a  ldarg.0
0x1770b  call     bool Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenUtilities::IsHashedProofToken(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken token)
0x17710  brtrue   loc_177B4
0x17715  ldarg.0
0x17716  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Claims()
0x1771b  ldsfld   string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPServerToServerProtocolConstants::ActorTokenClaimType
0x17720  call     class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenExtensions::GetSingleClaim(class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> self, string claimType)
0x17725  stloc.0
0x17726  ldloc.0
0x17727  brfalse.s loc_17745
0x17729  ldc.i4   0x310C78B
0x1772e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenHandler()
0x17733  ldc.i4.s 0xA
0x17735  ldstr    aValidateactorA// "ValidateActor: Actor token should be nu"...
0x1773a  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1773f  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPActorNotTrustedForDelegationOAuthException::.ctor()
0x17744  throw
0x17745  ldarg.0
0x17746  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Issuer()
0x1774b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x17750  brfalse.s loc_1776E
0x17752  ldc.i4   0x310C78C
0x17757  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenHandler()
0x1775c  ldc.i4.s 0xA
0x1775e  ldstr    aValidateactorI// "ValidateActor: Issuer token is missing."
0x17763  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x17768  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPActorNotTrustedForDelegationOAuthException::.ctor()
0x1776d  throw
0x1776e  ldarg.0
0x1776f  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Issuer()
0x17774  ldstr    a0000000300000f// "00000003-0000-0ff1-ce00-000000000000"
0x17779  ldc.i4.1
0x1777a  callvirt instance int32 [mscorlib]System.String::IndexOf(string, valuetype [mscorlib]System.StringComparison)
0x1777f  brtrue.s loc_17798
0x17781  ldc.i4   0x31177D6
0x17786  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenHandler()
0x1778b  ldc.i4.s 0x64
0x1778d  ldstr    aValidateactorI_0// "ValidateActor: Issuer is SharePoint."
0x17792  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x17797  ret
0x17798  ldc.i4   0x310C78D
0x1779d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenHandler()
0x177a2  ldc.i4.s 0xA
0x177a4  ldstr    aValidateactorI_1// "ValidateActor: Issuer is NOT sharepoint"...
0x177a9  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x177ae  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPActorNotTrustedForDelegationOAuthException::.ctor()
0x177b3  throw
0x177b4  ldarg.0
0x177b5  callvirt instance class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_ActorToken()
0x177ba  brfalse  loc_17884
0x177bf  ldarg.0
0x177c0  callvirt instance class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_ActorToken()
0x177c5  call     bool Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::IsActorToken(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken accessToken)
0x177ca  brtrue.s loc_177E8
0x177cc  ldc.i4   0x2358709A
0x177d1  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenHandler()
0x177d6  ldc.i4.s 0xA
0x177d8  ldstr    aValidateactorC// "ValidateActor: Can't find actor token c"...
0x177dd  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x177e2  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPActorNotTrustedForDelegationOAuthException::.ctor()
0x177e7  throw
0x177e8  ldarg.0
0x177e9  callvirt instance class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_ActorToken()
0x177ee  call     bool Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::IsUserToken(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken accessToken)
0x177f3  brfalse.s loc_17811
0x177f5  ldc.i4   0x310C78E
0x177fa  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenHandler()
0x177ff  ldc.i4.s 0xA
0x17801  ldstr    aValidateactorA_0// "ValidateActor: Actor token is user toke"...
0x17806  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1780b  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPActorNotTrustedForDelegationOAuthException::.ctor()
0x17810  throw
0x17811  ldarg.0
0x17812  callvirt instance class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_ActorToken()
0x17817  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Claims()
0x1781c  ldstr    aTid// "tid"
0x17821  call     class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenExtensions::GetSingleClaim(class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> self, string claimType)
0x17826  stloc.1
0x17827  ldarg.0
0x17828  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Claims()
0x1782d  ldstr    aTid// "tid"
0x17832  call     class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenExtensions::GetSingleClaim(class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> self, string claimType)
0x17837  stloc.2
0x17838  ldloc.1
0x17839  brfalse.s loc_1786E
0x1783b  ldloc.2
0x1783c  brfalse.s loc_1786E
0x1783e  ldloc.1
0x1783f  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_Value()
0x17844  ldloc.2
0x17845  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_Value()
0x1784a  ldc.i4.5
0x1784b  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x17850  brtrue.s loc_17884
0x17852  ldc.i4   0x310C78F
0x17857  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenHandler()
0x1785c  ldc.i4.s 0xA
0x1785e  ldstr    aValidateactorT// "ValidateActor: Tid claims do not match."
0x17863  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x17868  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPActorNotTrustedForDelegationOAuthException::.ctor()
0x1786d  throw
0x1786e  ldc.i4   0x310C790
0x17873  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenHandler()
0x17878  ldc.i4.s 0x64
0x1787a  ldstr    aValidateactorT_0// "ValidateActor: Tid claims not found."
0x1787f  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x17884  ret
```
