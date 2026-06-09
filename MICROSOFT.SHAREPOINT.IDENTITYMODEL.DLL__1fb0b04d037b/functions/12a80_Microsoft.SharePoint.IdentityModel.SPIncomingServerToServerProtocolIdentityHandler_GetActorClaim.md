# Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::GetActorClaim

- ea: `0x12a80`
- end: `0x12bcb`
- name: `Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::GetActorClaim`
- size: `331`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x123f0`
- `0x12960`

## callees

- `0x12a80`
- `0x12bd0`
- `0x12cd0`
- `0x12d10`
- `0x12eb0`
- `0x12f90`

## string_xrefs

- `0x12ad9`: `WopiAppOnlyTokenFeature`
- `0x12ba7`: `SPIncomingIdentityHandler: No TenantId claim. Is this ADFS Blue?`
- `0x12bbf`: `SPIncomingIdentityHandler: An evoSts app-only identity, so not building an actor claim to denote app-only.`

## pseudocode

```c

```

## disassembly

```asm
0x12a80  ldarg.0
0x12a81  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimTypes::get_Actor()
0x12a86  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimCollectionExtensions::GetSingleClaim(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection, string)
0x12a8b  stloc.0
0x12a8c  ldloc.0
0x12a8d  brtrue.s loc_12A9B
0x12a8f  ldarg.0
0x12a90  ldstr    aActor// "actor"
0x12a95  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimCollectionExtensions::GetSingleClaim(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection, string)
0x12a9a  stloc.0
0x12a9b  ldloc.0
0x12a9c  brtrue   loc_12BC9
0x12aa1  ldc.i4.0
0x12aa2  stloc.1
0x12aa3  ldc.i4.0
0x12aa4  stloc.2
0x12aa5  ldc.i4.0
0x12aa6  stloc.3
0x12aa7  ldc.i4   0x2912
0x12aac  ldnull
0x12aad  ldnull
0x12aae  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.DarkDeploymentUtility::IsFeatureEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId, class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext, class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb)
0x12ab3  brfalse.s loc_12ABC
0x12ab5  ldarg.0
0x12ab6  call     bool Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::IsEvoStsAppOnlyIdentity(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection claims)
0x12abb  stloc.1
0x12abc  ldc.i4   0x29C3
0x12ac1  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x12ac6  brfalse.s loc_12ACF
0x12ac8  ldarg.0
0x12ac9  call     bool Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::IsServiceAssertedAppV1(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection claims)
0x12ace  stloc.2
0x12acf  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPWOPIHost::WopiAppOnlyTokenFeature
0x12ad4  ldstr    a05312016// "05/31/2016"
0x12ad9  ldstr    aWopiapponlytok// "WopiAppOnlyTokenFeature"
0x12ade  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid, string, string)
0x12ae3  brtrue.s loc_12AEC
0x12ae5  ldarg.0
0x12ae6  call     bool Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::IsWopiAppOnlyIdentity(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection claims)
0x12aeb  stloc.3
0x12aec  ldc.i4.0
0x12aed  stloc.s  4
0x12aef  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPServerToServerProtocolConstants::OAuthCrossTenantFeature
0x12af4  ldstr    a09072016// "09/07/2016"
0x12af9  ldstr    aOauthCrossTena// "OAuth Cross Tenant Call."
0x12afe  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid, string, string)
0x12b03  brtrue.s loc_12B38
0x12b05  ldarg.0
0x12b06  call     bool Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::IsCrossTenantCall(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection claims)
0x12b0b  stloc.s  4
0x12b0d  ldc.i4   0x134A494
0x12b12  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x12b17  ldc.i4.s 0x32
0x12b19  ldstr    aGetactorclaimC// "GetActorClaim: Cross Tenant Call: '{0}'"...
0x12b1e  ldc.i4.1
0x12b1f  newarr   [mscorlib]System.Object
0x12b24  stloc.s  7
0x12b26  ldloc.s  7
0x12b28  ldc.i4.0
0x12b29  ldloc.s  4
0x12b2b  box      [mscorlib]System.Boolean
0x12b30  stelem.ref
0x12b31  ldloc.s  7
0x12b33  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x12b38  ldloc.1
0x12b39  brtrue.s loc_12BB3
0x12b3b  ldloc.2
0x12b3c  brtrue.s loc_12BB3
0x12b3e  ldloc.3
0x12b3f  brtrue.s loc_12BB3
0x12b41  ldloc.s  4
0x12b43  brtrue.s loc_12BB3
0x12b45  ldarg.0
0x12b46  ldstr    aAppid// "appid"
0x12b4b  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimCollectionExtensions::GetSingleClaim(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection, string)
0x12b50  stloc.0
0x12b51  ldarg.0
0x12b52  ldstr    aTid// "tid"
0x12b57  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimCollectionExtensions::GetSingleClaim(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection, string)
0x12b5c  stloc.s  5
0x12b5e  ldloc.s  5
0x12b60  brfalse.s loc_12B9B
0x12b62  ldloc.0
0x12b63  brfalse.s loc_12B9B
0x12b65  ldloc.0
0x12b66  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x12b6b  ldloc.s  5
0x12b6d  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x12b72  call     string Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::BuildActorClaim(string appIdValue, string tenantIdValue)
0x12b77  stloc.s  6
0x12b79  ldloc.0
0x12b7a  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_ClaimType()
0x12b7f  ldloc.s  6
0x12b81  ldloc.0
0x12b82  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_ValueType()
0x12b87  ldloc.0
0x12b88  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Issuer()
0x12b8d  ldloc.0
0x12b8e  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_OriginalIssuer()
0x12b93  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::.ctor(string, string, string, string, string)
0x12b98  stloc.0
0x12b99  br.s     loc_12BC9
0x12b9b  ldc.i4   0x4454D7
0x12ba0  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x12ba5  ldc.i4.s 0x32
0x12ba7  ldstr    aSpincomingiden_11// "SPIncomingIdentityHandler: No TenantId "...
0x12bac  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x12bb1  br.s     loc_12BC9
0x12bb3  ldc.i4   0x71A65E
0x12bb8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x12bbd  ldc.i4.s 0x32
0x12bbf  ldstr    aSpincomingiden_12// "SPIncomingIdentityHandler: An evoSts ap"...
0x12bc4  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x12bc9  ldloc.0
0x12bca  ret
```
