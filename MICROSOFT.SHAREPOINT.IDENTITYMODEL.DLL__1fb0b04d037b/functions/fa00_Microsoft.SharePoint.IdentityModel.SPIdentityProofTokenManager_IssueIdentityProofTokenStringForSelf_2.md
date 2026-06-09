# Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenManager::IssueIdentityProofTokenStringForSelf_2

- ea: `0xfa00`
- end: `0xfb30`
- name: `Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenManager::IssueIdentityProofTokenStringForSelf_2`
- size: `304`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0xf9d0`
- `0xf9f0`

## callees

- `0xf780`
- `0xf7a0`
- `0xfa00`
- `0xfb30`
- `0xfbf0`
- `0x10190`
- `0x102b0`

## string_xrefs

- `0xfa25`: `proofToken`
- `0xfaf2`: `SPIdentityProofTokenManager: Identity token using Proof token request. EndPoint: '{0}', IdentityContext: '{1}', ProofToken: '{2}'`
- `0xfa3f`: `Refresh Proof Token`
- `0xfa8c`: `SPIdentityProofTokenManager: Incoming context is AppOnly, Issue AppOnly Proof token.`
- `0xfaca`: `SPIdentityProofTokenManager: Incoming context is AppPlusUser, Issue AppPlusOnly Proof token.`

## pseudocode

```c

```

## disassembly

```asm
0xfa00  ldnull
0xfa01  ldarg.0
0xfa02  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.OAuth2EndpointIdentity::op_Equality(class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.OAuth2EndpointIdentity, class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.OAuth2EndpointIdentity)
0xfa07  brfalse.s loc_FA14
0xfa09  ldstr    aEndpoint// "endpoint"
0xfa0e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xfa13  throw
0xfa14  ldarg.1
0xfa15  brtrue.s loc_FA22
0xfa17  ldstr    aIdentitycontex// "identityContext"
0xfa1c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xfa21  throw
0xfa22  ldarg.2
0xfa23  brtrue.s loc_FA30
0xfa25  ldstr    aProoftoken_1// "proofToken"
0xfa2a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xfa2f  throw
0xfa30  ldarg.2
0xfa31  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.IdentityModel.SPProofTokenCacheItem::get_Expiry()
0xfa36  ldarg.s  4
0xfa38  call     bool [mscorlib]System.DateTime::op_LessThanOrEqual(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xfa3d  brfalse.s loc_FA4A
0xfa3f  ldstr    aRefreshProofTo// "Refresh Proof Token"
0xfa44  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenExpiredException::.ctor(string)
0xfa49  throw
0xfa4a  ldarg.s  4
0xfa4c  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0xfa51  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xfa56  brfalse.s loc_FA63
0xfa58  ldstr    aExpiryParamete// "Expiry parameter is less than current d"...
0xfa5d  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string)
0xfa62  throw
0xfa63  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPAppRequestContext [Microsoft.SharePoint]Microsoft.SharePoint.SPAppRequestContext::get_Current()
0xfa68  stloc.0
0xfa69  ldc.i4   0x2B3D
0xfa6e  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0xfa73  brfalse.s loc_FAA7
0xfa75  ldloc.0
0xfa76  brfalse.s loc_FAA7
0xfa78  ldloc.0
0xfa79  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPAppRequestContext::get_IsAppOnlyRequest()
0xfa7e  brfalse.s loc_FAA7
0xfa80  ldc.i4   0x14D5684
0xfa85  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0xfa8a  ldc.i4.s 0x32
0xfa8c  ldstr    aSpidentityproo_4// "SPIdentityProofTokenManager: Incoming c"...
0xfa91  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xfa96  ldarg.0
0xfa97  ldloc.0
0xfa98  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPAppRequestContext::get_ClientId()
0xfa9d  ldarg.2
0xfa9e  ldarg.3
0xfa9f  ldarg.s  4
0xfaa1  call     string Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenManager::IssueAppOnlyIdentityProofTokenStringForSelf(class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.OAuth2EndpointIdentity endpoint, string appId, class Microsoft.SharePoint.IdentityModel.SPProofTokenCacheItem proofToken, string endPointUrl, valuetype [mscorlib]System.DateTime expiry)
0xfaa6  ret
0xfaa7  ldc.i4   0x374E
0xfaac  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0xfab1  brfalse.s loc_FAE6
0xfab3  ldloc.0
0xfab4  brfalse.s loc_FAE6
0xfab6  ldloc.0
0xfab7  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.SPAppRequestContext::get_IsAppOnlyRequest()
0xfabc  brtrue.s loc_FAE6
0xfabe  ldc.i4   0x164F38B
0xfac3  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0xfac8  ldc.i4.s 0x32
0xfaca  ldstr    aSpidentityproo_5// "SPIdentityProofTokenManager: Incoming c"...
0xfacf  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xfad4  ldarg.0
0xfad5  ldarg.1
0xfad6  ldloc.0
0xfad7  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.SPAppRequestContext::get_ClientId()
0xfadc  ldarg.2
0xfadd  ldarg.3
0xfade  ldarg.s  4
0xfae0  call     string Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenManager::IssueAppPlusUserIdentityProofTokenStringForSelf(class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.OAuth2EndpointIdentity endpoint, class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPIdentityContext identityContext, string appId, class Microsoft.SharePoint.IdentityModel.SPProofTokenCacheItem proofToken, string endPointUrl, valuetype [mscorlib]System.DateTime expiry)
0xfae5  ret
0xfae6  ldc.i4   0x35F7C5
0xfaeb  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0xfaf0  ldc.i4.s 0x32
0xfaf2  ldstr    aSpidentityproo_3// "SPIdentityProofTokenManager: Identity t"...
0xfaf7  ldc.i4.3
0xfaf8  newarr   [mscorlib]System.Object
0xfafd  stloc.2
0xfafe  ldloc.2
0xfaff  ldc.i4.0
0xfb00  ldarg.0
0xfb01  stelem.ref
0xfb02  ldloc.2
0xfb03  ldc.i4.1
0xfb04  ldarg.1
0xfb05  stelem.ref
0xfb06  ldloc.2
0xfb07  ldc.i4.2
0xfb08  ldarg.2
0xfb09  stelem.ref
0xfb0a  ldloc.2
0xfb0b  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xfb10  ldarg.0
0xfb11  callvirt instance string [mscorlib]System.Object::ToString()
0xfb16  ldarg.2
0xfb17  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SymmetricSecurityKey Microsoft.SharePoint.IdentityModel.SPProofTokenCacheItem::get_SecurityKey()
0xfb1c  ldarg.1
0xfb1d  ldarg.3
0xfb1e  ldarg.s  5
0xfb20  ldc.i4.0
0xfb21  call     class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenManager::GetOutboundClaimsForLoopback(class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPIdentityContext identityContext, string endPointUrl, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPOAuthTokenScenario scenario, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPOAuthProofTokenTypes proofTokenType)
0xfb26  ldarg.s  4
0xfb28  call     string Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenManager::CreateIdentityTokenString(string audience, class [System.IdentityModel]System.IdentityModel.Tokens.SymmetricSecurityKey securityKey, class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> claims, valuetype [mscorlib]System.DateTime expiry)
0xfb2d  stloc.1
0xfb2e  ldloc.1
0xfb2f  ret
```
