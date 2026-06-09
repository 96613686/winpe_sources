# Microsoft.SharePoint.IdentityModel.SPSecurityTokenService::GetLogonIdentityClaim

- ea: `0x1dd10`
- end: `0x1def5`
- name: `Microsoft.SharePoint.IdentityModel.SPSecurityTokenService::GetLogonIdentityClaim`
- size: `485`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1d380`

## callees

- `0xeaa0`
- `0x198c0`
- `0x198d0`
- `0x198e0`
- `0x198f0`
- `0x19950`
- `0x1b820`
- `0x1b880`
- `0x1dd10`
- `0x2c520`

## string_xrefs

- `0x1dd9e`: `Incoming request is OAuth. Will try to get a logon identity claim accordingly.`
- `0x1ddad`: `Inside SPSecurityTokenService.GetLogonIdentityClaim; getting the identity claim from MapperOperations`
- `0x1de63`: `Incoming request in NOT OAuth. Getting the logon identity claim accordingly.`

## pseudocode

```c

```

## disassembly

```asm
0x1dd10  ldc.i4   0x1299223
0x1dd15  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x1dd1a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1dd1f  ldstr    aRequestinfo// "requestInfo"
0x1dd24  ldarg.0
0x1dd25  call     void Microsoft.SharePoint.IdentityModel.SPArgumentHelper::LogAndThrowOnNull(unsigned int32 id, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat category, string name, object value)
0x1dd2a  ldc.i4   0x1299240
0x1dd2f  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x1dd34  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1dd39  ldstr    aInputidentity// "inputIdentity"
0x1dd3e  ldarg.1
0x1dd3f  call     void Microsoft.SharePoint.IdentityModel.SPArgumentHelper::LogAndThrowOnNull(unsigned int32 id, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat category, string name, object value)
0x1dd44  ldc.i4   0x1299241
0x1dd49  call     unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.TaggingUtilities::ReserveTag(unsigned int32)
0x1dd4e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1dd53  ldstr    aOutputidentity// "outputIdentity"
0x1dd58  ldarg.2
0x1dd59  call     void Microsoft.SharePoint.IdentityModel.SPArgumentHelper::LogAndThrowOnNull(unsigned int32 id, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat category, string name, object value)
0x1dd5e  ldnull
0x1dd5f  stloc.0
0x1dd60  ldarg.0
0x1dd61  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityToken Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::get_SPRequest()
0x1dd66  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityTokenProperties [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityToken::get_Properties()
0x1dd6b  callvirt instance valuetype [mscorlib]System.Nullable`1<bool> [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityTokenProperties::get_IsOAuthRequest()
0x1dd70  stloc.1
0x1dd71  ldloca.s 1
0x1dd73  call     instance bool valuetype [mscorlib]System.Nullable`1<bool>::get_HasValue()
0x1dd78  brfalse  loc_1DE4E
0x1dd7d  ldloca.s 1
0x1dd7f  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<bool>::get_Value()
0x1dd84  brfalse  loc_1DE4E
0x1dd89  ldc.i4   0x11A4CB
0x1dd8e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1dd93  ldc.i4   0xC8
0x1dd98  ldarg.0
0x1dd99  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::GetLogMessagePrefix()
0x1dd9e  ldstr    aIncomingReques// "Incoming request is OAuth. Will try to "...
0x1dda3  call     string [mscorlib]System.String::Concat(string, string)
0x1dda8  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1ddad  ldstr    aInsideSpsecuri// "Inside SPSecurityTokenService.GetLogonI"...
0x1ddb2  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string)
0x1ddb7  stloc.3
0x1ddb8  ldarg.0
0x1ddb9  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPRequestSecurityToken Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::get_SPRequest()
0x1ddbe  callvirt instance class [System.ServiceModel]System.ServiceModel.EndpointAddress [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.WSTrustMessage::get_AppliesTo()
0x1ddc3  callvirt instance class [System]System.Uri [System.ServiceModel]System.ServiceModel.EndpointAddress::get_Uri()
0x1ddc8  ldarg.0
0x1ddc9  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::get_Identity()
0x1ddce  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x1ddd3  ldarg.3
0x1ddd4  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim Microsoft.SharePoint.IdentityModel.SPIdentityClaimMapperOperations::GetIdentityClaim(class [System]System.Uri contextUri, class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection inputClaims, valuetype SPCallingIdentityType callerType)
0x1ddd9  stloc.0
0x1ddda  leave.s  loc_1DDE6
0x1dddc  ldloc.3
0x1dddd  brfalse.s loc_1DDE5
0x1dddf  ldloc.3
0x1dde0  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1dde5  endfinally
0x1dde6  ldloc.0
0x1dde7  brfalse.s loc_1DE12
0x1dde9  ldc.i4   0x11A4CC
0x1ddee  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1ddf3  ldc.i4   0xC8
0x1ddf8  ldarg.0
0x1ddf9  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::GetLogMessagePrefix()
0x1ddfe  ldstr    aAUserSLogonIde// "A user's logon identity was successfull"...
0x1de03  call     string [mscorlib]System.String::Concat(string, string)
0x1de08  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1de0d  br       loc_1DEF3
0x1de12  ldc.i4   0x11A4CD
0x1de17  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1de1c  ldc.i4.s 0xA
0x1de1e  ldarg.0
0x1de1f  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::GetLogMessagePrefix()
0x1de24  ldstr    aCouldNotGetAnI// "Could not get an identity claim from th"...
0x1de29  call     string [mscorlib]System.String::Concat(string, string)
0x1de2e  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1de33  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x1de38  ldstr    aNoidentityclai// "NoIdentityClaimMapped"
0x1de3d  ldc.i4.0
0x1de3e  newarr   [mscorlib]System.Object
0x1de43  call     string [Microsoft.SharePoint]Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo, string, object[])
0x1de48  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x1de4d  throw
0x1de4e  ldc.i4   0x11A4CE
0x1de53  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1de58  ldc.i4   0xC8
0x1de5d  ldarg.0
0x1de5e  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::GetLogMessagePrefix()
0x1de63  ldstr    aIncomingReques_0// "Incoming request in NOT OAuth. Getting "...
0x1de68  call     string [mscorlib]System.String::Concat(string, string)
0x1de6d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1de72  ldarg.1
0x1de73  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x1de78  ldarg.0
0x1de79  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::get_LogonIdentityClaimType()
0x1de7e  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimCollectionExtensions::GetSingleClaim(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection, string)
0x1de83  stloc.2
0x1de84  ldc.i4.4
0x1de85  ldarg.0
0x1de86  callvirt instance valuetype Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestSource Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::get_Source()
0x1de8b  bne.un.s loc_1DEAB
0x1de8d  ldarg.2
0x1de8e  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x1de93  ldarg.0
0x1de94  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPLoginProviderBase Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::get_TrustedLoginProvider()
0x1de99  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedClaimTypeInformation [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPLoginProviderBase::get_IdentityClaimTypeInformation()
0x1de9e  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedClaimTypeInformation::get_MappedClaimType()
0x1dea3  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimCollectionExtensions::GetSingleClaim(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection, string)
0x1dea8  stloc.0
0x1dea9  br.s     loc_1DEF3
0x1deab  ldarg.0
0x1deac  callvirt instance valuetype Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestSource Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::get_Source()
0x1deb1  brfalse.s loc_1DEBC
0x1deb3  ldc.i4.1
0x1deb4  ldarg.0
0x1deb5  callvirt instance valuetype Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestSource Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::get_Source()
0x1deba  bne.un.s loc_1DEF1
0x1debc  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimTypes::get_UserLogonName()
0x1dec1  ldloc.2
0x1dec2  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x1dec7  ldloc.2
0x1dec8  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_ValueType()
0x1decd  ldstr    aSharepoint// "SharePoint"
0x1ded2  ldarg.0
0x1ded3  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimTypes::get_UserLogonName()
0x1ded8  callvirt instance string Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::OriginalIssuerForPrincipalClaims(string claimType)
0x1dedd  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::.ctor(string, string, string, string, string)
0x1dee2  stloc.0
0x1dee3  ldarg.2
0x1dee4  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x1dee9  ldloc.0
0x1deea  callvirt instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection::Add(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim)
0x1deef  br.s     loc_1DEF3
0x1def1  ldloc.2
0x1def2  stloc.0
0x1def3  ldloc.0
0x1def4  ret
```
