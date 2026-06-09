# <GetOutboundClaimsForLoopback>d__3::MoveNext

- ea: `0x2d500`
- end: `0x2df4a`
- name: `<GetOutboundClaimsForLoopback>d__3::MoveNext`
- size: `2634`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x10220`
- `0x10310`
- `0x103b0`
- `0x105c0`
- `0x2d500`
- `0x2df70`
- `0x2dfd0`

## string_xrefs

- `0x2d591`: `SPIdentityProofTokenManager: Endpoint URL Value: '{0}'`
- `0x2d5c9`: `SPIdentityProofTokenManager: Html Decoded Value: '{0}'`
- `0x2d61c`: `SPIdentityProofTokenManager: EndpointUrl: '{0}' Hash Value: '{1}'`
- `0x2d6fd`: `SPPOP_AuthAddCorrelationIdInProofToken`
- `0x2d7f1`: `There is no SPSharedRequestContext in the thread context`
- `0x2d827`: `Readonly Proof Token request, use SPO App Display Name`
- `0x2d917`: `SPIdentityProofTokenManager: Create AppOnly Proof Token`
- `0x2d99b`: `SPIdentityProofTokenManager: endpointIdentity: '{0}' does not contain realm`
- `0x2d9d3`: `SPIdentityProofTokenManager: Realm from endpoint identity: '{0}' `
- `0x2da47`: `apponlyprooftoken`
- `0x2dadb`: `SPIdentityProofTokenManager: App principal permission is empty, so not adding role claim in proof token.`
- `0x2db51`: `SPIdentityProofTokenManager: No Role claim present on outgoing context, so not adding role claim in proof token.`
- `0x2dbad`: `SPIdentityProofTokenManager: User UPN property does not exist.`
- `0x2dbe0`: `SPIdentityProofTokenManager: User NameId property does not exist.`
- `0x2dc25`: `SPIdentityProofTokenManager: {0}`
- `0x2dc51`: `SPIdentityProofTokenManager: appId: '{0}' realm: '{1}'`
- `0x2dd4f`: `SPIdentityProofTokenManager: Readonly Proof Token, Use readonly permission`
- `0x2dde2`: `SPIdentityProofTokenManager: App principal permission is empty, so not adding scope claim in proof token.`
- `0x2de7e`: `SPPOP_AuthProofTokenTypeClaim`

## pseudocode

```c

```

## disassembly

```asm
0x2d500  ldarg.0
0x2d501  ldfld    int32 <GetOutboundClaimsForLoopback>d__3::<>1__state
0x2d506  stloc.2
0x2d507  ldloc.2
0x2d508  switch   loc_2D56E, loc_2D668, loc_2D6A1, loc_2D6D0, loc_2D740, loc_2D76A, loc_2D7A2, loc_2D8C2, loc_2DA31, loc_2DA65, loc_2DAC3, loc_2DB39, loc_2DC9E, loc_2DCCA, loc_2DCFB, loc_2DD2C, loc_2DD7D, loc_2DDCA, loc_2DF3D, loc_2DE59, loc_2DEBE, loc_2DEE6, loc_2DF36
0x2d569  br       loc_2DF3D
0x2d56e  ldarg.0
0x2d56f  ldc.i4.m1
0x2d570  stfld    int32 <GetOutboundClaimsForLoopback>d__3::<>1__state
0x2d575  ldarg.0
0x2d576  ldfld    string <GetOutboundClaimsForLoopback>d__3::endPointUrl
0x2d57b  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2d580  brtrue   loc_2D6A8
0x2d585  ldc.i4   0x12802CC
0x2d58a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x2d58f  ldc.i4.s 0x32
0x2d591  ldstr    aSpidentityproo_18// "SPIdentityProofTokenManager: Endpoint U"...
0x2d596  ldc.i4.1
0x2d597  newarr   [mscorlib]System.Object
0x2d59c  stloc.3
0x2d59d  ldloc.3
0x2d59e  ldc.i4.0
0x2d59f  ldarg.0
0x2d5a0  ldfld    string <GetOutboundClaimsForLoopback>d__3::endPointUrl
0x2d5a5  stelem.ref
0x2d5a6  ldloc.3
0x2d5a7  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x2d5ac  ldarg.0
0x2d5ad  ldarg.0
0x2d5ae  ldfld    string <GetOutboundClaimsForLoopback>d__3::endPointUrl
0x2d5b3  call     string [System.Web]System.Web.HttpUtility::UrlDecode(string)
0x2d5b8  stfld    string <GetOutboundClaimsForLoopback>d__3::endPointUrl
0x2d5bd  ldc.i4   0x12802CD
0x2d5c2  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x2d5c7  ldc.i4.s 0x32
0x2d5c9  ldstr    aSpidentityproo_19// "SPIdentityProofTokenManager: Html Decod"...
0x2d5ce  ldc.i4.1
0x2d5cf  newarr   [mscorlib]System.Object
0x2d5d4  stloc.s  4
0x2d5d6  ldloc.s  4
0x2d5d8  ldc.i4.0
0x2d5d9  ldarg.0
0x2d5da  ldfld    string <GetOutboundClaimsForLoopback>d__3::endPointUrl
0x2d5df  stelem.ref
0x2d5e0  ldloc.s  4
0x2d5e2  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x2d5e7  ldarg.0
0x2d5e8  ldarg.0
0x2d5e9  ldfld    string <GetOutboundClaimsForLoopback>d__3::endPointUrl
0x2d5ee  call     string Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenManager::GetHashValue(string endpointUrl)
0x2d5f3  stfld    string <GetOutboundClaimsForLoopback>d__3::<hashValue>5__4
0x2d5f8  ldarg.0
0x2d5f9  ldfld    string <GetOutboundClaimsForLoopback>d__3::<hashValue>5__4
0x2d5fe  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2d603  brfalse.s loc_2D610
0x2d605  ldstr    aEndpointurlHas// "EndpointUrl hashValue"
0x2d60a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x2d60f  throw
0x2d610  ldc.i4   0x114701B
0x2d615  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x2d61a  ldc.i4.s 0x32
0x2d61c  ldstr    aSpidentityproo_20// "SPIdentityProofTokenManager: EndpointUr"...
0x2d621  ldc.i4.2
0x2d622  newarr   [mscorlib]System.Object
0x2d627  stloc.s  5
0x2d629  ldloc.s  5
0x2d62b  ldc.i4.0
0x2d62c  ldarg.0
0x2d62d  ldfld    string <GetOutboundClaimsForLoopback>d__3::endPointUrl
0x2d632  stelem.ref
0x2d633  ldloc.s  5
0x2d635  ldc.i4.1
0x2d636  ldarg.0
0x2d637  ldfld    string <GetOutboundClaimsForLoopback>d__3::<hashValue>5__4
0x2d63c  stelem.ref
0x2d63d  ldloc.s  5
0x2d63f  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x2d644  ldarg.0
0x2d645  ldstr    aEndpointurl// "endpointurl"
0x2d64a  ldarg.0
0x2d64b  ldfld    string <GetOutboundClaimsForLoopback>d__3::<hashValue>5__4
0x2d650  newobj   instance void [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::.ctor(string, string)
0x2d655  stfld    class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim <GetOutboundClaimsForLoopback>d__3::<>2__current
0x2d65a  ldarg.0
0x2d65b  ldc.i4.1
0x2d65c  stfld    int32 <GetOutboundClaimsForLoopback>d__3::<>1__state
0x2d661  ldc.i4.1
0x2d662  stloc.1
0x2d663  leave    loc_2DF48
0x2d668  ldarg.0
0x2d669  ldc.i4.m1
0x2d66a  stfld    int32 <GetOutboundClaimsForLoopback>d__3::<>1__state
0x2d66f  ldarg.0
0x2d670  ldstr    aEndpointurllen// "endpointurlLength"
0x2d675  ldarg.0
0x2d676  ldfld    string <GetOutboundClaimsForLoopback>d__3::endPointUrl
0x2d67b  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2d680  stloc.s  6
0x2d682  ldloca.s 6
0x2d684  call     instance string [mscorlib]System.Int32::ToString()
0x2d689  newobj   instance void [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::.ctor(string, string)
0x2d68e  stfld    class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim <GetOutboundClaimsForLoopback>d__3::<>2__current
0x2d693  ldarg.0
0x2d694  ldc.i4.2
0x2d695  stfld    int32 <GetOutboundClaimsForLoopback>d__3::<>1__state
0x2d69a  ldc.i4.1
0x2d69b  stloc.1
0x2d69c  leave    loc_2DF48
0x2d6a1  ldarg.0
0x2d6a2  ldc.i4.m1
0x2d6a3  stfld    int32 <GetOutboundClaimsForLoopback>d__3::<>1__state
0x2d6a8  ldarg.0
0x2d6a9  ldstr    aIsloopback// "isloopback"
0x2d6ae  ldc.i4.1
0x2d6af  stloc.s  7
0x2d6b1  ldloca.s 7
0x2d6b3  call     instance string [mscorlib]System.Boolean::ToString()
0x2d6b8  newobj   instance void [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::.ctor(string, string)
0x2d6bd  stfld    class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim <GetOutboundClaimsForLoopback>d__3::<>2__current
0x2d6c2  ldarg.0
0x2d6c3  ldc.i4.3
0x2d6c4  stfld    int32 <GetOutboundClaimsForLoopback>d__3::<>1__state
0x2d6c9  ldc.i4.1
0x2d6ca  stloc.1
0x2d6cb  leave    loc_2DF48
0x2d6d0  ldarg.0
0x2d6d1  ldc.i4.m1
0x2d6d2  stfld    int32 <GetOutboundClaimsForLoopback>d__3::<>1__state
0x2d6d7  ldarg.0
0x2d6d8  ldc.i4   0x3722
0x2d6dd  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x2d6e2  stfld    bool <GetOutboundClaimsForLoopback>d__3::<readonlyProofTokenFlightEnabled>5__5
0x2d6e7  ldarg.0
0x2d6e8  ldfld    valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPOAuthTokenScenario <GetOutboundClaimsForLoopback>d__3::scenario
0x2d6ed  ldc.i4.3
0x2d6ee  bne.un   loc_2D8C9
0x2d6f3  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenManager::AddCorrelationIdInProofToken
0x2d6f8  ldstr    a07062017// "07/06/2017"
0x2d6fd  ldstr    aSppopAuthaddco// "SPPOP_AuthAddCorrelationIdInProofToken"
0x2d702  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid, string, string)
0x2d707  brtrue.s loc_2D747
0x2d709  ldarg.0
0x2d70a  ldsfld   string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPServerToServerProtocolConstants::CorrelationIdClaimType
0x2d70f  call     valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::CorrelationGetVisibleID()
0x2d714  stloc.s  8
0x2d716  ldloca.s 8
0x2d718  constrained. [mscorlib]System.Guid
0x2d71e  callvirt instance string [mscorlib]System.Object::ToString()
0x2d723  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPHttpUtility::Base64UrlEncode(string)
0x2d728  newobj   instance void [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::.ctor(string, string)
0x2d72d  stfld    class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim <GetOutboundClaimsForLoopback>d__3::<>2__current
0x2d732  ldarg.0
0x2d733  ldc.i4.4
0x2d734  stfld    int32 <GetOutboundClaimsForLoopback>d__3::<>1__state
0x2d739  ldc.i4.1
0x2d73a  stloc.1
0x2d73b  leave    loc_2DF48
0x2d740  ldarg.0
0x2d741  ldc.i4.m1
0x2d742  stfld    int32 <GetOutboundClaimsForLoopback>d__3::<>1__state
0x2d747  ldarg.0
0x2d748  ldstr    aVer// "ver"
0x2d74d  ldsfld   string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPServerToServerProtocolConstants::HashedProofToken
0x2d752  newobj   instance void [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::.ctor(string, string)
0x2d757  stfld    class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim <GetOutboundClaimsForLoopback>d__3::<>2__current
0x2d75c  ldarg.0
0x2d75d  ldc.i4.5
0x2d75e  stfld    int32 <GetOutboundClaimsForLoopback>d__3::<>1__state
0x2d763  ldc.i4.1
0x2d764  stloc.1
0x2d765  leave    loc_2DF48
0x2d76a  ldarg.0
0x2d76b  ldc.i4.m1
0x2d76c  stfld    int32 <GetOutboundClaimsForLoopback>d__3::<>1__state
0x2d771  ldarg.0
0x2d772  ldfld    string <GetOutboundClaimsForLoopback>d__3::encodedSiteId
0x2d777  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2d77c  brtrue.s loc_2D7A9
0x2d77e  ldarg.0
0x2d77f  ldsfld   string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPServerToServerProtocolConstants::SiteIdClaimType
0x2d784  ldarg.0
0x2d785  ldfld    string <GetOutboundClaimsForLoopback>d__3::encodedSiteId
0x2d78a  newobj   instance void [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::.ctor(string, string)
0x2d78f  stfld    class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim <GetOutboundClaimsForLoopback>d__3::<>2__current
0x2d794  ldarg.0
0x2d795  ldc.i4.6
0x2d796  stfld    int32 <GetOutboundClaimsForLoopback>d__3::<>1__state
0x2d79b  ldc.i4.1
0x2d79c  stloc.1
0x2d79d  leave    loc_2DF48
0x2d7a2  ldarg.0
0x2d7a3  ldc.i4.m1
0x2d7a4  stfld    int32 <GetOutboundClaimsForLoopback>d__3::<>1__state
0x2d7a9  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenManager::AppDisplayNameClaim
0x2d7ae  ldstr    a10302017// "10/30/2017"
0x2d7b3  ldstr    aSppopAuthappdi// "SPPOP_AuthAppDisplayNameClaim"
0x2d7b8  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid, string, string)
0x2d7bd  brtrue   loc_2D8C9
0x2d7c2  ldarg.0
0x2d7c3  call     T0x2B000013
0x2d7c8  stfld    class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPSharedRequestContext <GetOutboundClaimsForLoopback>d__3::<context>5__6
0x2d7cd  ldarg.0
0x2d7ce  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPSharedRequestContext <GetOutboundClaimsForLoopback>d__3::<context>5__6
0x2d7d3  brtrue.s loc_2D800
0x2d7d5  ldarg.0
0x2d7d6  ldfld    bool <GetOutboundClaimsForLoopback>d__3::<readonlyProofTokenFlightEnabled>5__5
0x2d7db  brfalse.s loc_2D7E5
0x2d7dd  ldarg.0
0x2d7de  ldfld    bool <GetOutboundClaimsForLoopback>d__3::readonlyProofToken
0x2d7e3  brtrue.s loc_2D800
0x2d7e5  ldc.i4   0x181E1D7
0x2d7ea  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x2d7ef  ldc.i4.s 0x32
0x2d7f1  ldstr    aThereIsNoSpsha// "There is no SPSharedRequestContext in t"...
0x2d7f6  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x2d7fb  br       loc_2D8C9
0x2d800  ldarg.0
0x2d801  ldsfld   string [mscorlib]System.String::Empty
0x2d806  stfld    string <GetOutboundClaimsForLoopback>d__3::<displayName>5__7
0x2d80b  ldarg.0
0x2d80c  ldfld    bool <GetOutboundClaimsForLoopback>d__3::<readonlyProofTokenFlightEnabled>5__5
0x2d811  brfalse.s loc_2D849
0x2d813  ldarg.0
0x2d814  ldfld    bool <GetOutboundClaimsForLoopback>d__3::readonlyProofToken
0x2d819  brfalse.s loc_2D849
0x2d81b  ldc.i4   0x181E1D8
0x2d820  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x2d825  ldc.i4.s 0x32
0x2d827  ldstr    aReadonlyProofT_0// "Readonly Proof Token request, use SPO A"...
0x2d82c  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x2d831  ldarg.0
0x2d832  ldsfld   string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPServerToServerProtocolConstants::SharepointReadOnlyApp
0x2d837  stfld    string <GetOutboundClaimsForLoopback>d__3::appId
0x2d83c  ldarg.0
0x2d83d  ldsfld   string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPServerToServerProtocolConstants::SharepointReadOnlyAppDisplayName
0x2d842  stfld    string <GetOutboundClaimsForLoopback>d__3::<displayName>5__7
0x2d847  br.s     loc_2D879
0x2d849  ldarg.0
0x2d84a  ldarg.0
0x2d84b  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPSharedRequestContext <GetOutboundClaimsForLoopback>d__3::<context>5__6
0x2d850  ldfld    string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPSharedRequestContext::ClientAppDisplayNameClaim
0x2d855  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2d85a  brfalse.s loc_2D869
0x2d85c  ldarg.0
0x2d85d  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPSharedRequestContext <GetOutboundClaimsForLoopback>d__3::<context>5__6
0x2d862  ldfld    string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPSharedRequestContext::AppDisplayNameClaim
0x2d867  br.s     loc_2D874
0x2d869  ldarg.0
0x2d86a  ldfld    class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPSharedRequestContext <GetOutboundClaimsForLoopback>d__3::<context>5__6
0x2d86f  ldfld    string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPSharedRequestContext::ClientAppDisplayNameClaim
0x2d874  stfld    string <GetOutboundClaimsForLoopback>d__3::<displayName>5__7
0x2d879  ldarg.0
0x2d87a  ldfld    string <GetOutboundClaimsForLoopback>d__3::<displayName>5__7
0x2d87f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2d884  brfalse.s loc_2D89E
0x2d886  ldc.i4   0x21C108D
0x2d88b  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x2d890  ldc.i4.s 0x32
0x2d892  ldstr    aTheDisplayName// "The display name claim was not found or"...
0x2d897  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x2d89c  br.s     loc_2D8C9
0x2d89e  ldarg.0
0x2d89f  ldstr    aAppDisplayname// "app_displayname"
0x2d8a4  ldarg.0
0x2d8a5  ldfld    string <GetOutboundClaimsForLoopback>d__3::<displayName>5__7
0x2d8aa  newobj   instance void [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::.ctor(string, string)
0x2d8af  stfld    class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim <GetOutboundClaimsForLoopback>d__3::<>2__current
0x2d8b4  ldarg.0
0x2d8b5  ldc.i4.7
0x2d8b6  stfld    int32 <GetOutboundClaimsForLoopback>d__3::<>1__state
0x2d8bb  ldc.i4.1
0x2d8bc  stloc.1
0x2d8bd  leave    loc_2DF48
0x2d8c2  ldarg.0
0x2d8c3  ldc.i4.m1
0x2d8c4  stfld    int32 <GetOutboundClaimsForLoopback>d__3::<>1__state
0x2d8c9  ldarg.0
0x2d8ca  ldc.i4   0x2B3D
0x2d8cf  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x2d8d4  stfld    bool <GetOutboundClaimsForLoopback>d__3::<appOnlyProofTokenFlight>5__8
0x2d8d9  ldarg.0
0x2d8da  ldc.i4   0x374E
0x2d8df  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x2d8e4  stfld    bool <GetOutboundClaimsForLoopback>d__3::<appPlusUserProofTokenFlightEnabled>5__9
0x2d8e9  ldarg.0
0x2d8ea  ldsfld   string [mscorlib]System.String::Empty
0x2d8ef  stfld    string <GetOutboundClaimsForLoopback>d__3::<realm>5__a
0x2d8f4  ldarg.0
0x2d8f5  ldfld    bool <GetOutboundClaimsForLoopback>d__3::<appOnlyProofTokenFlight>5__8
0x2d8fa  brfalse  loc_2DB60
0x2d8ff  ldarg.0
0x2d900  ldfld    valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPOAuthProofTokenTypes <GetOutboundClaimsForLoopback>d__3::proofTokenType
0x2d905  ldc.i4.1
0x2d906  bne.un   loc_2DB60
0x2d90b  ldc.i4   0x1463298
0x2d910  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x2d915  ldc.i4.s 0x32
0x2d917  ldstr    aSpidentityproo_21// "SPIdentityProofTokenManager: Create App"...
0x2d91c  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x2d921  ldarg.0
  ... truncated ...
```
