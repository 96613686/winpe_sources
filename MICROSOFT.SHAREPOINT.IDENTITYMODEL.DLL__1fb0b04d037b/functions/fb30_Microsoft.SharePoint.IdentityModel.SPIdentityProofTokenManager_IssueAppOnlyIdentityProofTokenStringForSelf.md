# Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenManager::IssueAppOnlyIdentityProofTokenStringForSelf

- ea: `0xfb30`
- end: `0xfbe5`
- name: `Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenManager::IssueAppOnlyIdentityProofTokenStringForSelf`
- size: `181`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0xfa00`

## callees

- `0xf780`
- `0xf7a0`
- `0xfb30`
- `0x10190`
- `0x102c0`

## string_xrefs

- `0xfb5a`: `proofToken`
- `0xfb74`: `Refresh Proof Token`
- `0xfba4`: `SPIdentityProofTokenManager: Identity token using Proof token request. EndPoint: '{0}', ProofToken: '{1}' AppId: '{2}'`

## pseudocode

```c

```

## disassembly

```asm
0xfb30  ldnull
0xfb31  ldarg.0
0xfb32  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.OAuth2EndpointIdentity::op_Equality(class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.OAuth2EndpointIdentity, class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.OAuth2EndpointIdentity)
0xfb37  brfalse.s loc_FB44
0xfb39  ldstr    aEndpoint// "endpoint"
0xfb3e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xfb43  throw
0xfb44  ldarg.1
0xfb45  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xfb4a  brfalse.s loc_FB57
0xfb4c  ldstr    aAppid_0// "appId"
0xfb51  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xfb56  throw
0xfb57  ldarg.2
0xfb58  brtrue.s loc_FB65
0xfb5a  ldstr    aProoftoken_1// "proofToken"
0xfb5f  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xfb64  throw
0xfb65  ldarg.2
0xfb66  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.IdentityModel.SPProofTokenCacheItem::get_Expiry()
0xfb6b  ldarg.s  4
0xfb6d  call     bool [mscorlib]System.DateTime::op_LessThanOrEqual(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xfb72  brfalse.s loc_FB7F
0xfb74  ldstr    aRefreshProofTo// "Refresh Proof Token"
0xfb79  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenExpiredException::.ctor(string)
0xfb7e  throw
0xfb7f  ldarg.s  4
0xfb81  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xfb86  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xfb8b  brfalse.s loc_FB98
0xfb8d  ldstr    aExpiryParamete// "Expiry parameter is less than current d"...
0xfb92  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xfb97  throw
0xfb98  ldc.i4   0x1463297
0xfb9d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0xfba2  ldc.i4.s 0x32
0xfba4  ldstr    aSpidentityproo_6// "SPIdentityProofTokenManager: Identity t"...
0xfba9  ldc.i4.3
0xfbaa  newarr   [mscorlib]System.Object
0xfbaf  stloc.1
0xfbb0  ldloc.1
0xfbb1  ldc.i4.0
0xfbb2  ldarg.0
0xfbb3  stelem.ref
0xfbb4  ldloc.1
0xfbb5  ldc.i4.1
0xfbb6  ldarg.2
0xfbb7  stelem.ref
0xfbb8  ldloc.1
0xfbb9  ldc.i4.2
0xfbba  ldarg.1
0xfbbb  stelem.ref
0xfbbc  ldloc.1
0xfbbd  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xfbc2  ldarg.0
0xfbc3  callvirt instance string [mscorlib]System.Object::ToString()
0xfbc8  ldarg.2
0xfbc9  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SymmetricSecurityKey Microsoft.SharePoint.IdentityModel.SPProofTokenCacheItem::get_SecurityKey()
0xfbce  ldnull
0xfbcf  ldarg.3
0xfbd0  ldc.i4.0
0xfbd1  ldc.i4.1
0xfbd2  ldnull
0xfbd3  ldarg.0
0xfbd4  ldarg.1
0xfbd5  ldc.i4.0
0xfbd6  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenManager::GetOutboundClaimsForLoopback(class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPIdentityContext identityContext, string endPointUrl, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPOAuthTokenScenario scenario, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPOAuthProofTokenTypes proofTokenType, string encodedSiteId, class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.OAuth2EndpointIdentity endpoint, string appId, [opt] bool readonlyProofToken)
0xfbdb  ldarg.s  4
0xfbdd  call     string Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenManager::CreateIdentityTokenString(string audience, class [System.IdentityModel]System.IdentityModel.Tokens.SymmetricSecurityKey securityKey, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> claims, valuetype [mscorlib]System.DateTime expiry)
0xfbe2  stloc.0
0xfbe3  ldloc.0
0xfbe4  ret
```
