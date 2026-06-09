# Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenManager::IssueAppPlusUserIdentityProofTokenStringForSelf

- ea: `0xfbf0`
- end: `0xfcb0`
- name: `Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenManager::IssueAppPlusUserIdentityProofTokenStringForSelf`
- size: `192`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0xfa00`

## callees

- `0xf780`
- `0xf7a0`
- `0xfbf0`
- `0x10190`
- `0x102c0`

## string_xrefs

- `0xfc28`: `proofToken`
- `0xfc42`: `Refresh Proof Token`
- `0xfc72`: `SPIdentityProofTokenManager: Identity token using Proof token request. EndPoint: '{0}', AppId: '{2}'`

## pseudocode

```c

```

## disassembly

```asm
0xfbf0  ldnull
0xfbf1  ldarg.0
0xfbf2  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.OAuth2EndpointIdentity::op_Equality(class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.OAuth2EndpointIdentity, class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.OAuth2EndpointIdentity)
0xfbf7  brfalse.s loc_FC04
0xfbf9  ldstr    aEndpoint// "endpoint"
0xfbfe  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xfc03  throw
0xfc04  ldarg.1
0xfc05  brtrue.s loc_FC12
0xfc07  ldstr    aIdentitycontex// "identityContext"
0xfc0c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xfc11  throw
0xfc12  ldarg.2
0xfc13  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xfc18  brfalse.s loc_FC25
0xfc1a  ldstr    aAppid_0// "appId"
0xfc1f  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xfc24  throw
0xfc25  ldarg.3
0xfc26  brtrue.s loc_FC33
0xfc28  ldstr    aProoftoken_1// "proofToken"
0xfc2d  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xfc32  throw
0xfc33  ldarg.3
0xfc34  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.IdentityModel.SPProofTokenCacheItem::get_Expiry()
0xfc39  ldarg.s  5
0xfc3b  call     bool [mscorlib]System.DateTime::op_LessThanOrEqual(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xfc40  brfalse.s loc_FC4D
0xfc42  ldstr    aRefreshProofTo// "Refresh Proof Token"
0xfc47  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenExpiredException::.ctor(string)
0xfc4c  throw
0xfc4d  ldarg.s  5
0xfc4f  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xfc54  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xfc59  brfalse.s loc_FC66
0xfc5b  ldstr    aExpiryParamete// "Expiry parameter is less than current d"...
0xfc60  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xfc65  throw
0xfc66  ldc.i4   0x164F38C
0xfc6b  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0xfc70  ldc.i4.s 0x32
0xfc72  ldstr    aSpidentityproo_7// "SPIdentityProofTokenManager: Identity t"...
0xfc77  ldc.i4.2
0xfc78  newarr   [mscorlib]System.Object
0xfc7d  stloc.1
0xfc7e  ldloc.1
0xfc7f  ldc.i4.0
0xfc80  ldarg.0
0xfc81  stelem.ref
0xfc82  ldloc.1
0xfc83  ldc.i4.1
0xfc84  ldarg.2
0xfc85  stelem.ref
0xfc86  ldloc.1
0xfc87  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xfc8c  ldarg.0
0xfc8d  callvirt instance string [mscorlib]System.Object::ToString()
0xfc92  ldarg.3
0xfc93  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SymmetricSecurityKey Microsoft.SharePoint.IdentityModel.SPProofTokenCacheItem::get_SecurityKey()
0xfc98  ldarg.1
0xfc99  ldarg.s  4
0xfc9b  ldc.i4.0
0xfc9c  ldc.i4.2
0xfc9d  ldnull
0xfc9e  ldarg.0
0xfc9f  ldarg.2
0xfca0  ldc.i4.0
0xfca1  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenManager::GetOutboundClaimsForLoopback(class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPIdentityContext identityContext, string endPointUrl, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPOAuthTokenScenario scenario, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPOAuthProofTokenTypes proofTokenType, string encodedSiteId, class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.OAuth2EndpointIdentity endpoint, string appId, [opt] bool readonlyProofToken)
0xfca6  ldarg.s  5
0xfca8  call     string Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenManager::CreateIdentityTokenString(string audience, class [System.IdentityModel]System.IdentityModel.Tokens.SymmetricSecurityKey securityKey, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> claims, valuetype [mscorlib]System.DateTime expiry)
0xfcad  stloc.0
0xfcae  ldloc.0
0xfcaf  ret
```
