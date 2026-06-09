# Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::SetSharedRequestContextOnThread

- ea: `0x13b30`
- end: `0x13dfc`
- name: `Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::SetSharedRequestContextOnThread`
- size: `716`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x139d0`

## callees

- `0x135f0`
- `0x13b30`
- `0x149b0`
- `0x14a60`

## string_xrefs

- `0x13b8e`: `ConsolidateWopiTokens`
- `0x13b6a`: `ShareByLinkWithProofToken`
- `0x13be0`: `WopiAppOnlyTokenFeature`
- `0x13ba6`: `Reading wopi token claim type`
- `0x13cb8`: `Wopi token claim type is {0}`
- `0x13ce8`: `Setting SPSharedRequestContext on thread with:  tid: {0} scp: {1} appctx: {2} ispreauth: {3} isappplususerwopi: {4} isapponlywopi: {5}`
- `0x13d57`: `Token should not have both 'preauth' and 'appplususerwopi' claims set to true.`
- `0x13daa`: `Setting SPSharedRequestContext on thread with:  tid: {0} scp: {1} appctx: {2} app_displayname: {3} isnoauth: {4}`

## pseudocode

```c

```

## disassembly

```asm
0x13b30  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPSharedRequestContext::.ctor()
0x13b35  stloc.0
0x13b36  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPWOPIHost::get_IsPreAuthWopiFeatureEnabled()
0x13b3b  brfalse  loc_13D62
0x13b40  ldloc.0
0x13b41  ldstr    aTid// "tid"
0x13b46  call     string Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::GetClaimValueFromSecurityToken(string claimType)
0x13b4b  stfld    string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPSharedRequestContext::TidClaim
0x13b50  ldloc.0
0x13b51  ldstr    aAppctx// "appctx"
0x13b56  call     string Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::GetClaimValueFromSecurityToken(string claimType)
0x13b5b  stfld    string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPSharedRequestContext::AppCtxClaim
0x13b60  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::ShareByLinkWithProofToken
0x13b65  ldstr    a03292017// "03/29/2017"
0x13b6a  ldstr    aSharebylinkwit// "ShareByLinkWithProofToken"
0x13b6f  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid, string, string)
0x13b74  brtrue.s loc_13B82
0x13b76  ldloc.0
0x13b77  ldarg.0
0x13b78  call     instance bool Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::get_IsProofTokenScenario()
0x13b7d  stfld    bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPSharedRequestContext::IsProofTokenScenario
0x13b82  ldnull
0x13b83  stloc.1
0x13b84  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPWOPIHost::WopiTokenConsolidationFeature
0x13b89  ldstr    a04192016// "04/19/2016"
0x13b8e  ldstr    aConsolidatewop// "ConsolidateWopiTokens"
0x13b93  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid, string, string)
0x13b98  brtrue.s loc_13BBB
0x13b9a  ldc.i4   0x11D374D
0x13b9f  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x13ba4  ldc.i4.s 0x32
0x13ba6  ldstr    aReadingWopiTok_0// "Reading wopi token claim type"
0x13bab  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x13bb0  ldsfld   string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPServerToServerProtocolConstants::WopiTokenTypeClaimType
0x13bb5  call     string Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::GetClaimValueFromSecurityToken(string claimType)
0x13bba  stloc.1
0x13bbb  ldloc.1
0x13bbc  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x13bc1  brfalse  loc_13C6A
0x13bc6  ldloc.0
0x13bc7  ldstr    aScp// "scp"
0x13bcc  call     string Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::GetClaimValueFromSecurityToken(string claimType)
0x13bd1  stfld    string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPSharedRequestContext::PermClaim
0x13bd6  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPWOPIHost::WopiAppOnlyTokenFeature
0x13bdb  ldstr    a05312016// "05/31/2016"
0x13be0  ldstr    aWopiapponlytok// "WopiAppOnlyTokenFeature"
0x13be5  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid, string, string)
0x13bea  brtrue.s loc_13C09
0x13bec  ldloc.0
0x13bed  ldfld    string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPSharedRequestContext::PermClaim
0x13bf2  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x13bf7  brfalse.s loc_13C09
0x13bf9  ldloc.0
0x13bfa  ldstr    aRoles// "roles"
0x13bff  call     string Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::GetClaimValueFromSecurityToken(string claimType)
0x13c04  stfld    string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPSharedRequestContext::PermClaim
0x13c09  ldsfld   string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPServerToServerProtocolConstants::PreAuthTokenClaimType
0x13c0e  call     string Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::GetClaimValueFromSecurityToken(string claimType)
0x13c13  stloc.2
0x13c14  ldsfld   string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPServerToServerProtocolConstants::AppPlusUserWopiTokenClaimType
0x13c19  call     string Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::GetClaimValueFromSecurityToken(string claimType)
0x13c1e  stloc.3
0x13c1f  ldloc.2
0x13c20  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x13c25  brfalse.s loc_13C30
0x13c27  ldloc.0
0x13c28  ldc.i4.0
0x13c29  stfld    bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPSharedRequestContext::IsPreAuthWopiRequest
0x13c2e  br.s     loc_13C42
0x13c30  ldloc.0
0x13c31  ldloc.2
0x13c32  ldstr    aTrue// "true"
0x13c37  ldc.i4.5
0x13c38  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x13c3d  stfld    bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPSharedRequestContext::IsPreAuthWopiRequest
0x13c42  ldloc.3
0x13c43  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x13c48  brfalse.s loc_13C56
0x13c4a  ldloc.0
0x13c4b  ldc.i4.0
0x13c4c  stfld    bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPSharedRequestContext::IsAppPlusUserWopiRequest
0x13c51  br       loc_13CDC
0x13c56  ldloc.0
0x13c57  ldloc.3
0x13c58  ldstr    aTrue// "true"
0x13c5d  ldc.i4.5
0x13c5e  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x13c63  stfld    bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPSharedRequestContext::IsAppPlusUserWopiRequest
0x13c68  br.s     loc_13CDC
0x13c6a  ldloc.0
0x13c6b  ldstr    aWopiAp// "wopi_ap"
0x13c70  call     string Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::GetClaimValueFromSecurityToken(string claimType)
0x13c75  stfld    string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPSharedRequestContext::PermClaim
0x13c7a  ldloc.1
0x13c7b  ldloca.s 4
0x13c7d  call     T0x2B000016
0x13c82  brfalse.s loc_13CAC
0x13c84  ldloc.s  4
0x13c86  ldc.i4.1
0x13c87  bne.un.s loc_13C92
0x13c89  ldloc.0
0x13c8a  ldc.i4.1
0x13c8b  stfld    bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPSharedRequestContext::IsAppPlusUserWopiRequest
0x13c90  br.s     loc_13CAC
0x13c92  ldloc.s  4
0x13c94  ldc.i4.2
0x13c95  bne.un.s loc_13CA0
0x13c97  ldloc.0
0x13c98  ldc.i4.1
0x13c99  stfld    bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPSharedRequestContext::IsPreAuthWopiRequest
0x13c9e  br.s     loc_13CAC
0x13ca0  ldloc.s  4
0x13ca2  ldc.i4.3
0x13ca3  bne.un.s loc_13CAC
0x13ca5  ldloc.0
0x13ca6  ldc.i4.1
0x13ca7  stfld    bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPSharedRequestContext::IsAppOnlyWopiRequest
0x13cac  ldc.i4   0x11D374E
0x13cb1  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x13cb6  ldc.i4.s 0x32
0x13cb8  ldstr    aWopiTokenClaim// "Wopi token claim type is {0}"
0x13cbd  ldc.i4.1
0x13cbe  newarr   [mscorlib]System.Object
0x13cc3  stloc.s  5
0x13cc5  ldloc.s  5
0x13cc7  ldc.i4.0
0x13cc8  ldloc.s  4
0x13cca  box      [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WopiTokenType
0x13ccf  callvirt instance string [mscorlib]System.Object::ToString()
0x13cd4  stelem.ref
0x13cd5  ldloc.s  5
0x13cd7  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x13cdc  ldc.i4   0x1001843
0x13ce1  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x13ce6  ldc.i4.s 0x32
0x13ce8  ldstr    aSettingSpshare// "Setting SPSharedRequestContext on threa"...
0x13ced  ldc.i4.6
0x13cee  newarr   [mscorlib]System.Object
0x13cf3  stloc.s  6
0x13cf5  ldloc.s  6
0x13cf7  ldc.i4.0
0x13cf8  ldloc.0
0x13cf9  ldfld    string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPSharedRequestContext::TidClaim
0x13cfe  stelem.ref
0x13cff  ldloc.s  6
0x13d01  ldc.i4.1
0x13d02  ldloc.0
0x13d03  ldfld    string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPSharedRequestContext::PermClaim
0x13d08  stelem.ref
0x13d09  ldloc.s  6
0x13d0b  ldc.i4.2
0x13d0c  ldloc.0
0x13d0d  ldfld    string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPSharedRequestContext::AppCtxClaim
0x13d12  stelem.ref
0x13d13  ldloc.s  6
0x13d15  ldc.i4.3
0x13d16  ldloc.0
0x13d17  ldflda   bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPSharedRequestContext::IsPreAuthWopiRequest
0x13d1c  call     instance string [mscorlib]System.Boolean::ToString()
0x13d21  stelem.ref
0x13d22  ldloc.s  6
0x13d24  ldc.i4.4
0x13d25  ldloc.0
0x13d26  ldflda   bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPSharedRequestContext::IsAppPlusUserWopiRequest
0x13d2b  call     instance string [mscorlib]System.Boolean::ToString()
0x13d30  stelem.ref
0x13d31  ldloc.s  6
0x13d33  ldc.i4.5
0x13d34  ldloc.0
0x13d35  ldflda   bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPSharedRequestContext::IsAppOnlyWopiRequest
0x13d3a  call     instance string [mscorlib]System.Boolean::ToString()
0x13d3f  stelem.ref
0x13d40  ldloc.s  6
0x13d42  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x13d47  ldloc.0
0x13d48  ldfld    bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPSharedRequestContext::IsPreAuthWopiRequest
0x13d4d  brfalse.s loc_13D62
0x13d4f  ldloc.0
0x13d50  ldfld    bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPSharedRequestContext::IsAppPlusUserWopiRequest
0x13d55  brfalse.s loc_13D62
0x13d57  ldstr    aTokenShouldNot// "Token should not have both 'preauth' an"...
0x13d5c  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x13d61  throw
0x13d62  ldloc.0
0x13d63  ldstr    aAppDisplayname// "app_displayname"
0x13d68  call     string Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::GetClaimValueFromActorOrSecurityToken(string claimType)
0x13d6d  stfld    string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPSharedRequestContext::AppDisplayNameClaim
0x13d72  ldc.i4   0x2B3C
0x13d77  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x13d7c  brfalse.s loc_13D9E
0x13d7e  ldloc.0
0x13d7f  ldsfld   string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPServerToServerProtocolConstants::ClientAppDisplayName
0x13d84  call     string Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::GetClaimValueFromSecurityToken(string claimType)
0x13d89  stfld    string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPSharedRequestContext::ClientAppDisplayNameClaim
0x13d8e  ldloc.0
0x13d8f  ldstr    aVer// "ver"
0x13d94  call     string Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::GetClaimValueFromSecurityToken(string claimType)
0x13d99  stfld    string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPSharedRequestContext::ClientAppTokenVersionClaim
0x13d9e  ldc.i4   0x111E540
0x13da3  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x13da8  ldc.i4.s 0x32
0x13daa  ldstr    aSettingSpshare_0// "Setting SPSharedRequestContext on threa"...
0x13daf  ldc.i4.5
0x13db0  newarr   [mscorlib]System.Object
0x13db5  stloc.s  7
0x13db7  ldloc.s  7
0x13db9  ldc.i4.0
0x13dba  ldloc.0
0x13dbb  ldfld    string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPSharedRequestContext::TidClaim
0x13dc0  stelem.ref
0x13dc1  ldloc.s  7
0x13dc3  ldc.i4.1
0x13dc4  ldloc.0
0x13dc5  ldfld    string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPSharedRequestContext::PermClaim
0x13dca  stelem.ref
0x13dcb  ldloc.s  7
0x13dcd  ldc.i4.2
0x13dce  ldloc.0
0x13dcf  ldfld    string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPSharedRequestContext::AppCtxClaim
0x13dd4  stelem.ref
0x13dd5  ldloc.s  7
0x13dd7  ldc.i4.3
0x13dd8  ldloc.0
0x13dd9  ldfld    string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPSharedRequestContext::AppDisplayNameClaim
0x13dde  stelem.ref
0x13ddf  ldloc.s  7
0x13de1  ldc.i4.4
0x13de2  ldloc.0
0x13de3  ldflda   bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPSharedRequestContext::IsPreAuthWopiRequest
0x13de8  call     instance string [mscorlib]System.Boolean::ToString()
0x13ded  stelem.ref
0x13dee  ldloc.s  7
0x13df0  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x13df5  ldloc.0
0x13df6  call     T0x2B000017
0x13dfb  ret
```
