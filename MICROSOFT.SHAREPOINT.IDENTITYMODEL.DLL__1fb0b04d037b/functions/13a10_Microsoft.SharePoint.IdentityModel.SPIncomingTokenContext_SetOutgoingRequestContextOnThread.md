# Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::SetOutgoingRequestContextOnThread

- ea: `0x13a10`
- end: `0x13b2a`
- name: `Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::SetOutgoingRequestContextOnThread`
- size: `282`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x139d0`

## callees

- `0x13590`
- `0x137a0`
- `0x13a10`
- `0x149b0`

## string_xrefs

- `0x13a6c`: `user_impersonation`
- `0x13a1c`: `Set Evo outgoing token context on thread`
- `0x13a85`: `Incoming token scope is User_impersonation, so clear scope for outgoing calls.`

## pseudocode

```c

```

## disassembly

```asm
0x13a10  ldc.i4   0x1255607
0x13a15  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x13a1a  ldc.i4.s 0x32
0x13a1c  ldstr    aSetEvoOutgoing_0// "Set Evo outgoing token context on threa"...
0x13a21  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x13a26  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPOutgoingContext::.ctor()
0x13a2b  stloc.0
0x13a2c  ldloc.0
0x13a2d  ldstr    aScope// "scope"
0x13a32  call     string Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::GetClaimValueFromSecurityToken(string claimType)
0x13a37  stfld    string [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPOutgoingContext::ScpClaim
0x13a3c  ldloc.0
0x13a3d  ldfld    string [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPOutgoingContext::ScpClaim
0x13a42  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x13a47  brfalse.s loc_13A59
0x13a49  ldloc.0
0x13a4a  ldstr    aScp// "scp"
0x13a4f  call     string Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::GetClaimValueFromSecurityToken(string claimType)
0x13a54  stfld    string [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPOutgoingContext::ScpClaim
0x13a59  ldloc.0
0x13a5a  ldfld    string [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPOutgoingContext::ScpClaim
0x13a5f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x13a64  brtrue.s loc_13AA7
0x13a66  ldloc.0
0x13a67  ldfld    string [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPOutgoingContext::ScpClaim
0x13a6c  ldstr    aUserImpersonat// "user_impersonation"
0x13a71  ldc.i4.3
0x13a72  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x13a77  brfalse.s loc_13AA7
0x13a79  ldc.i4   0x1255608
0x13a7e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x13a83  ldc.i4.s 0x32
0x13a85  ldstr    aIncomingTokenS// "Incoming token scope is User_impersonat"...
0x13a8a  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x13a8f  ldloc.0
0x13a90  ldsfld   string [mscorlib]System.String::Empty
0x13a95  stfld    string [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPOutgoingContext::ScpClaim
0x13a9a  ldloc.0
0x13a9b  ldsfld   string [mscorlib]System.String::Empty
0x13aa0  stfld    string [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPOutgoingContext::ClientAppId
0x13aa5  br.s     loc_13AE5
0x13aa7  ldloc.0
0x13aa8  ldstr    aClientappid// "clientappid"
0x13aad  call     string Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::GetClaimValueFromSecurityToken(string claimType)
0x13ab2  stfld    string [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPOutgoingContext::ClientAppId
0x13ab7  ldloc.0
0x13ab8  ldfld    string [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPOutgoingContext::ClientAppId
0x13abd  brtrue.s loc_13AE5
0x13abf  ldc.i4   0x1255609
0x13ac4  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x13ac9  ldc.i4.s 0x32
0x13acb  ldstr    aClientappidCla// "ClientAppId claim does not exist. Tryin"...
0x13ad0  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x13ad5  ldloc.0
0x13ad6  ldstr    aAppid// "appid"
0x13adb  call     string Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::GetClaimValueFromSecurityToken(string claimType)
0x13ae0  stfld    string [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPOutgoingContext::ClientAppId
0x13ae5  ldloc.0
0x13ae6  ldstr    aRoles// "roles"
0x13aeb  call     string Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::GetClaimValueFromSecurityToken(string claimType)
0x13af0  stfld    string [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPOutgoingContext::RoleClaim
0x13af5  ldloc.0
0x13af6  ldarg.0
0x13af7  call     instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPIncomingOAuthIdentityType Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::get_IdentityType()
0x13afc  stfld    valuetype [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPIncomingOAuthIdentityType [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPOutgoingContext::IdentityType
0x13b01  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPServerToServerProtocolConstants::IPAddressClaimForOAuthOutgoing
0x13b06  ldstr    a02042018// "02/04/2018"
0x13b0b  ldstr    aSppopIpaddress// "SPPOP_IPAddressClaimForOAuthOutgoingKil"...
0x13b10  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid, string, string)
0x13b15  brtrue.s loc_13B23
0x13b17  ldloc.0
0x13b18  ldarg.0
0x13b19  call     instance string Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::get_IPAddress()
0x13b1e  stfld    string [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPOutgoingContext::IPAddress
0x13b23  ldloc.0
0x13b24  call     T0x2B000006
0x13b29  ret
```
