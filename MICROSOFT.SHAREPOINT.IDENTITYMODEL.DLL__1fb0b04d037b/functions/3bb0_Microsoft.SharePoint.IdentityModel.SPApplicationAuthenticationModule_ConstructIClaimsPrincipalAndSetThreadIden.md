# Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::ConstructIClaimsPrincipalAndSetThreadIdentity

- ea: `0x3bb0`
- end: `0x41d8`
- name: `Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::ConstructIClaimsPrincipalAndSetThreadIdentity`
- size: `1576`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `registry_config, broker_com_uri`

## callers

- `0x3110`

## callees

- `0x3bb0`
- `0x41e0`
- `0x4210`
- `0x4270`
- `0x44c0`
- `0x48c0`
- `0x4900`
- `0x4930`
- `0x4940`
- `0x4970`
- `0x4990`
- `0x4e90`
- `0x5150`
- `0x59f0`
- `0x5b90`
- `0x10da0`
- `0x11ca0`
- `0x122e0`
- `0x13550`
- `0x13570`
- `0x13590`
- `0x135d0`
- `0x13610`
- `0x139d0`
- `0x13e00`
- `0x13e80`
- `0x14f10`
- `0x14f40`

## string_xrefs

- `0x3c34`: `Log Client Id and Token Type.`
- `0x3bdb`: `ConstructIClaimsPrincipalAndSetThreadIdentity`
- `0x3fb3`: `ConstructIClaimsPrincipalAndSetThreadIdentity`
- `0x405c`: `ConstructIClaimsPrincipalAndSetThreadIdentity`
- `0x3c0a`: `SPApplicationAuthenticationModule: Couldn't find a valid token in the request.`
- `0x3ca9`: `SPApplicationAuthenticationModule: Token received is not JsonWebSecurityToken.`
- `0x3cca`: `SPApplicationAuthenticationModule: Anonymous user + Application request, setting thread identity to anonymous.`
- `0x3d29`: `SPApplicationAuthenticationModule: Incoming token doesn't have user identity.`
- `0x3d8d`: `SPApplicationAuthenticationModule: ConstructIClaimsPrincipalAndSetThreadIdentity: App Asserted User V1 token, so making ClientAppId identity as incoming identity.`
- `0x3dda`: `SPApplicationAuthenticationModule: Tenant ID is null, so using incomingActorIdentity to get Tenant Id.`
- `0x3e07`: `SPApplicationAuthenticationModule: Client App Id is null, so using incomingActorIdentity to get Client App Id.`
- `0x3e92`: `Successfully generated client App Identity and set it as incomingActorIdentity. Client App Name Id: '{0}'`
- `0x3f1f`: `SPApplicationAuthenticationModule: ConstructIClaimsPrincipalAndSetThreadIdentity: App Asserted User V1 token, so keep actor identity as incoming identity.`
- `0x3f39`: `SPApplicationAuthenticationModule: Incoming token contains actor. Trying to attach it to current thread. Incoming Actor Identity: '{0}'`
- `0x3f7c`: `SPApplicationAuthenticationModule: Incoming token does not contain an actor.`
- `0x3fe6`: `Setting thread identity using token from Cache`
- `0x402d`: `SPApplicationAuthenticationModule: Signed in using token cache.`
- `0x4095`: `SPApplicationAuthenticationModule: Signed in using proof token.`
- `0x40d7`: `SPApplicationAuthenticationModule: Signed in using loopback token.`
- `0x40f2`: `SPApplicationAuthenticationModule: Cannot sign in using loopback token, since it has requiresAuthenticationToken flag.`
- `0x4122`: `SPApplicationAuthenticationModule: Signed in using user token cache.`
- `0x4192`: `access_token`

## pseudocode

```c

```

## disassembly

```asm
0x3bb0  ldarg.2
0x3bb1  brtrue.s loc_3BBE
0x3bb3  ldstr    aHttpcontext// "httpContext"
0x3bb8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x3bbd  throw
0x3bbe  ldarg.3
0x3bbf  brtrue.s loc_3BCC
0x3bc1  ldstr    aFam// "fam"
0x3bc6  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x3bcb  throw
0x3bcc  ldarg.s  4
0x3bce  ldstr    asc_336C0// ""
0x3bd3  stind.ref
0x3bd4  ldnull
0x3bd5  stloc.1
0x3bd6  ldc.i4   0x271D
0x3bdb  ldstr    aConstructiclai// "ConstructIClaimsPrincipalAndSetThreadId"...
0x3be0  ldstr    aDDbsElZltDevSt// "d:\\dbs\\el\\zlt\\dev\\sts\\identitymod"...
0x3be5  ldc.i4   0x2ED
0x3bea  call     class [Microsoft.Cobalt.Base]Cobalt.PerformanceTracing.ComponentTracer [Microsoft.Cobalt.Base]Cobalt.PerformanceTracing.ComponentTracer::Create(valuetype [Microsoft.Cobalt.Base]Cobalt.ComponentId, string, string, int32)
0x3bef  stloc.s  0x12
0x3bf1  ldarg.0
0x3bf2  ldarg.2
0x3bf3  ldloca.s 0
0x3bf5  ldloca.s 1
0x3bf7  call     instance bool Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::TryExtractAndValidateToken(class [System.Web]System.Web.HttpContext httpContext, [out] class Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext& tokenContext, [out] class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPIdentityProofToken& identityProofToken)
0x3bfc  brtrue.s loc_3C1C
0x3bfe  ldc.i4   0xCB29A
0x3c03  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x3c08  ldc.i4.s 0x32
0x3c0a  ldstr    aSpapplicationa_16// "SPApplicationAuthenticationModule: Coul"...
0x3c0f  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x3c14  ldc.i4.0
0x3c15  stloc.s  0x11
0x3c17  leave    loc_41D5
0x3c1c  leave.s  loc_3C2A
0x3c1e  ldloc.s  0x12
0x3c20  brfalse.s loc_3C29
0x3c22  ldloc.s  0x12
0x3c24  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x3c29  endfinally
0x3c2a  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::LogClientIdAndTokenType
0x3c2f  ldstr    a01102018// "01/10/2018"
0x3c34  ldstr    aLogClientIdAnd// "Log Client Id and Token Type."
0x3c39  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid, string, string)
0x3c3e  brtrue.s loc_3C53
0x3c40  ldarg.s  4
0x3c42  ldloc.0
0x3c43  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPIncomingOAuthIdentityType Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::get_IdentityType()
0x3c48  box      [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPIncomingOAuthIdentityType
0x3c4d  callvirt instance string [mscorlib]System.Object::ToString()
0x3c52  stind.ref
0x3c53  ldloc.0
0x3c54  callvirt instance void Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::SetOnThread()
0x3c59  ldloc.0
0x3c5a  callvirt instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPIncomingTokenType Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::get_TokenType()
0x3c5f  ldc.i4.3
0x3c60  beq.s    loc_3C8E
0x3c62  ldarg.1
0x3c63  brfalse.s loc_3C8E
0x3c65  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_LocalOrThrow()
0x3c6a  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_AllowOAuthOverHttp()
0x3c6f  brtrue.s loc_3C8E
0x3c71  ldsfld   string [System]System.Uri::UriSchemeHttps
0x3c76  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAlternateUrl::get_ContextUri()
0x3c7b  callvirt instance string [System]System.Uri::get_Scheme()
0x3c80  ldc.i4.5
0x3c81  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x3c86  brtrue.s loc_3C8E
0x3c88  ldarg.1
0x3c89  call     void Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::SendSSLRequiredResponse(class [System.Web]System.Web.HttpApplication httpApplication)
0x3c8e  ldloc.0
0x3c8f  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::get_SecurityToken()
0x3c94  isinst   [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken
0x3c99  stloc.2
0x3c9a  ldloc.2
0x3c9b  brtrue.s loc_3CB5
0x3c9d  ldc.i4   0x199540
0x3ca2  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x3ca7  ldc.i4.s 0xA
0x3ca9  ldstr    aSpapplicationa_17// "SPApplicationAuthenticationModule: Toke"...
0x3cae  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x3cb3  ldc.i4.0
0x3cb4  ret
0x3cb5  ldarg.0
0x3cb6  ldarg.2
0x3cb7  call     instance bool Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::HandleAnonymousRequest(class [System.Web]System.Web.HttpContext context)
0x3cbc  brfalse.s loc_3CEC
0x3cbe  ldc.i4   0x1DC7C6
0x3cc3  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x3cc8  ldc.i4.s 0x32
0x3cca  ldstr    aSpapplicationa_18// "SPApplicationAuthenticationModule: Anon"...
0x3ccf  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x3cd4  ldloc.2
0x3cd5  call     bool Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::IsLoopbackToken(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken token)
0x3cda  brfalse.s loc_3CE3
0x3cdc  ldarg.0
0x3cdd  ldloc.2
0x3cde  call     instance void Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::SetIncomingApplicationContext(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken token)
0x3ce3  ldarg.0
0x3ce4  ldloc.2
0x3ce5  call     instance void Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::SetIncomingApplicationScope(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken token)
0x3cea  ldc.i4.1
0x3ceb  ret
0x3cec  ldc.i4   0x29BA
0x3cf1  ldc.i4.3
0x3cf2  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPConfigUtility::IsCodeEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPConfigUtility/FlightEnvironment)
0x3cf7  brfalse  loc_3FA0
0x3cfc  ldloc.0
0x3cfd  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::get_Identity()
0x3d02  callvirt instance int32 [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Count()
0x3d07  ldc.i4.0
0x3d08  ble      loc_3F88
0x3d0d  ldloc.0
0x3d0e  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::get_Identity()
0x3d13  ldc.i4.0
0x3d14  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Item(int32)
0x3d19  stloc.3
0x3d1a  ldloc.3
0x3d1b  brtrue.s loc_3D35
0x3d1d  ldc.i4   0x782421
0x3d22  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x3d27  ldc.i4.s 0xA
0x3d29  ldstr    aSpapplicationa_19// "SPApplicationAuthenticationModule: Inco"...
0x3d2e  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x3d33  ldc.i4.0
0x3d34  ret
0x3d35  ldloc.3
0x3d36  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Actor()
0x3d3b  stloc.s  4
0x3d3d  ldc.i4   0x2B3C
0x3d42  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x3d47  brfalse  loc_3F29
0x3d4c  ldc.i4   0x2B36
0x3d51  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x3d56  stloc.s  5
0x3d58  ldloc.3
0x3d59  call     bool Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::IsServiceAssertedAppV1(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity claimsIdentity)
0x3d5e  stloc.s  6
0x3d60  ldloc.3
0x3d61  call     bool Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::IsAppAssertedUserV1(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity claimsIdentity)
0x3d66  brtrue.s loc_3D76
0x3d68  ldloc.s  5
0x3d6a  brfalse  loc_3F13
0x3d6f  ldloc.s  6
0x3d71  brfalse  loc_3F13
0x3d76  ldloc.3
0x3d77  call     bool Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::IsClientAppAsIdentityAllowed(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity identity)
0x3d7c  brfalse  loc_3F13
0x3d81  ldc.i4   0x10638CA
0x3d86  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x3d8b  ldc.i4.s 0x32
0x3d8d  ldstr    aSpapplicationa_20// "SPApplicationAuthenticationModule: Cons"...
0x3d92  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x3d97  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentity::.ctor()
0x3d9c  stloc.s  7
0x3d9e  ldloc.3
0x3d9f  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x3da4  ldstr    aTid// "tid"
0x3da9  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimCollectionExtensions::GetSingleClaim(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection, string)
0x3dae  stloc.s  8
0x3db0  ldloc.3
0x3db1  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x3db6  ldstr    aClientappid// "clientappid"
0x3dbb  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimCollectionExtensions::GetSingleClaim(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection, string)
0x3dc0  stloc.s  9
0x3dc2  ldloc.s  5
0x3dc4  brfalse.s loc_3E24
0x3dc6  ldloc.s  6
0x3dc8  brfalse.s loc_3E24
0x3dca  ldloc.s  8
0x3dcc  brtrue.s loc_3DF7
0x3dce  ldc.i4   0x141B861
0x3dd3  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x3dd8  ldc.i4.s 0x32
0x3dda  ldstr    aSpapplicationa_21// "SPApplicationAuthenticationModule: Tena"...
0x3ddf  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x3de4  ldloc.s  4
0x3de6  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x3deb  ldstr    aTid// "tid"
0x3df0  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimCollectionExtensions::GetSingleClaim(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection, string)
0x3df5  stloc.s  8
0x3df7  ldloc.s  9
0x3df9  brtrue.s loc_3E24
0x3dfb  ldc.i4   0x141B862
0x3e00  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x3e05  ldc.i4.s 0x32
0x3e07  ldstr    aSpapplicationa_22// "SPApplicationAuthenticationModule: Clie"...
0x3e0c  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x3e11  ldloc.s  4
0x3e13  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x3e18  ldstr    aClientappid// "clientappid"
0x3e1d  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimCollectionExtensions::GetSingleClaim(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection, string)
0x3e22  stloc.s  9
0x3e24  ldloc.s  8
0x3e26  brfalse  loc_3EFB
0x3e2b  ldloc.s  9
0x3e2d  brfalse  loc_3EFB
0x3e32  ldloc.s  9
0x3e34  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x3e39  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3e3e  brtrue   loc_3EFB
0x3e43  ldloc.s  8
0x3e45  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x3e4a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x3e4f  brtrue   loc_3EFB
0x3e54  ldloc.s  7
0x3e56  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x3e5b  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimTypes::get_NameId()
0x3e60  ldloc.s  9
0x3e62  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x3e67  ldstr    asc_350C2// "@"
0x3e6c  ldloc.s  8
0x3e6e  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x3e73  call     string [mscorlib]System.String::Concat(string, string, string)
0x3e78  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::.ctor(string, string)
0x3e7d  callvirt instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection::Add(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim)
0x3e82  ldloc.s  7
0x3e84  stloc.s  4
0x3e86  ldc.i4   0x1096782
0x3e8b  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x3e90  ldc.i4.s 0x32
0x3e92  ldstr    aSuccessfullyGe// "Successfully generated client App Ident"...
0x3e97  ldc.i4.1
0x3e98  newarr   [mscorlib]System.Object
0x3e9d  stloc.s  0x13
0x3e9f  ldloc.s  0x13
0x3ea1  ldc.i4.0
0x3ea2  ldloc.s  9
0x3ea4  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x3ea9  ldstr    asc_350C2// "@"
0x3eae  ldloc.s  8
0x3eb0  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x3eb5  call     string [mscorlib]System.String::Concat(string, string, string)
0x3eba  stelem.ref
0x3ebb  ldloc.s  0x13
0x3ebd  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x3ec2  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPWOPIHost::get_IsPreAuthWopiFeatureEnabled()
0x3ec7  brfalse.s loc_3F29
0x3ec9  ldc.i4   0x32D1
0x3ece  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x3ed3  brfalse.s loc_3F29
0x3ed5  ldloc.3
0x3ed6  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Actor()
0x3edb  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x3ee0  ldstr    aAppid// "appid"
0x3ee5  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimCollectionExtensions::GetSingleClaim(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection, string)
0x3eea  stloc.s  0xA
0x3eec  ldloc.0
0x3eed  ldloc.s  0xA
0x3eef  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x3ef4  callvirt instance void Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::TryToSetAssertingAppSetOnSharedRequestContext(string assertingAppName)
0x3ef9  br.s     loc_3F29
0x3efb  ldc.i4   0x1096783
0x3f00  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x3f05  ldc.i4.s 0xA
0x3f07  ldstr    aFailedToGenera// "Failed to generated client App Identity"...
0x3f0c  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x3f11  br.s     loc_3F29
0x3f13  ldc.i4   0x10638CB
0x3f18  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x3f1d  ldc.i4.s 0x32
0x3f1f  ldstr    aSpapplicationa_23// "SPApplicationAuthenticationModule: Cons"...
0x3f24  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x3f29  ldloc.s  4
0x3f2b  brfalse.s loc_3F70
0x3f2d  ldc.i4   0x782422
0x3f32  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x3f37  ldc.i4.s 0x32
0x3f39  ldstr    aSpapplicationa_24// "SPApplicationAuthenticationModule: Inco"...
0x3f3e  ldc.i4.1
0x3f3f  newarr   [mscorlib]System.Object
0x3f44  stloc.s  0x14
0x3f46  ldloc.s  0x14
0x3f48  ldc.i4.0
0x3f49  ldloc.s  4
0x3f4b  callvirt instance string [mscorlib]System.Security.Principal.IIdentity::get_Name()
0x3f50  stelem.ref
0x3f51  ldloc.s  0x14
0x3f53  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x3f58  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAlternateUrl::get_ContextUri()
0x3f5d  ldloc.s  4
0x3f5f  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::CreateLocalActorIdentity(class [System]System.Uri contextUri, class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity incomingActorIdentity)
0x3f64  stloc.s  0xB
0x3f66  ldarg.0
0x3f67  ldloc.s  0xB
0x3f69  call     instance void Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::AttachActorIdentityToThread(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity actorIdentity)
0x3f6e  br.s     loc_3FA0
0x3f70  ldc.i4   0x782423
0x3f75  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x3f7a  ldc.i4.s 0xA
0x3f7c  ldstr    aSpapplicationa_25// "SPApplicationAuthenticationModule: Inco"...
0x3f81  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x3f86  br.s     loc_3FA0
0x3f88  ldc.i4   0x782440
0x3f8d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x3f92  ldc.i4.s 0xA
0x3f94  ldstr    aSpapplicationa_26// "SPApplicationAuthenticationModule: Iden"...
0x3f99  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x3f9e  ldc.i4.0
  ... truncated ...
```
