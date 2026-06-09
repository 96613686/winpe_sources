# Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenService::Issue

- ea: `0x79a0`
- end: `0x7eb6`
- name: `Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenService::Issue`
- size: `1302`
- prototype: ``
- caller_count: `0`
- callee_count: `21`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x79a0`
- `0x7ec0`
- `0x81e0`
- `0x8200`
- `0x8260`
- `0x8280`
- `0x8290`
- `0x82c0`
- `0x8320`
- `0x8390`
- `0x83c0`
- `0x8590`
- `0x85a0`
- `0x85c0`
- `0x85d0`
- `0x85e0`
- `0x85f0`
- `0x8600`
- `0x8610`
- `0x8620`
- `0x8630`

## string_xrefs

- `0x79ae`: `SelfIssuedTokenResponse`
- `0x7ad6`: `Loopback lifetime set to default configuration`
- `0x7bb5`: `Loopback lifetime set to default configuration`
- `0x7c5a`: `Loopback lifetime set to default configuration`
- `0x7aff`: `impersonation/issue`
- `0x7bf9`: `WopiAppOnlyTokenFeature`
- `0x7d03`: `SPPOP_ESTSTokenCacheFeature`

## pseudocode

```c

```

## disassembly

```asm
0x79a0  ldarg.1
0x79a1  brtrue.s loc_79AE
0x79a3  ldstr    aRequest// "request"
0x79a8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x79ad  throw
0x79ae  ldstr    aSelfissuedtoke// "SelfIssuedTokenResponse"
0x79b3  ldc.i4.s 0x32
0x79b5  ldc.i4.0
0x79b6  newarr   [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x79bb  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.TraceSeverity, class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[])
0x79c0  stloc.0
0x79c1  ldarg.0
0x79c2  ldfld    class Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenServiceConfiguration Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenService::configuration
0x79c7  callvirt instance string Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenServiceConfiguration::get_IssuerName()
0x79cc  stloc.1
0x79cd  ldarg.1
0x79ce  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.IdentityServices.RequestApplicationSecurityToken::get_NameId()
0x79d3  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x79d8  brtrue.s loc_79E1
0x79da  ldarg.1
0x79db  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.IdentityServices.RequestApplicationSecurityToken::get_NameId()
0x79e0  stloc.1
0x79e1  ldloca.s 2
0x79e3  initobj  [mscorlib]System.TimeSpan
0x79e9  ldnull
0x79ea  stloc.3
0x79eb  ldsfld   string [mscorlib]System.String::Empty
0x79f0  stloc.s  4
0x79f2  ldarg.1
0x79f3  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.IdentityServices.RequestApplicationSecurityToken::get_RequestType()
0x79f8  ldstr    aApplicationIss// "application/issue"
0x79fd  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x7a02  brtrue.s loc_7A1D
0x7a04  ldarg.0
0x7a05  ldfld    class Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenServiceConfiguration Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenService::configuration
0x7a0a  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenServiceConfiguration::get_AccessTokenLifetime()
0x7a0f  stloc.2
0x7a10  ldarg.0
0x7a11  ldloc.1
0x7a12  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenService::GetOutboundClaimsForApplicationToken(string nameIdentifier)
0x7a17  stloc.3
0x7a18  br       loc_7DF1
0x7a1d  ldarg.1
0x7a1e  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.IdentityServices.RequestApplicationSecurityToken::get_RequestType()
0x7a23  ldstr    aDelegationIssu// "delegation/issue"
0x7a28  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x7a2d  brtrue.s loc_7A48
0x7a2f  ldarg.0
0x7a30  ldfld    class Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenServiceConfiguration Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenService::configuration
0x7a35  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenServiceConfiguration::get_AccessTokenLifetime()
0x7a3a  stloc.2
0x7a3b  ldarg.0
0x7a3c  ldloc.1
0x7a3d  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenService::GetOutboundClaimsForDelegationToken(string nameIdentifier)
0x7a42  stloc.3
0x7a43  br       loc_7DF1
0x7a48  ldarg.1
0x7a49  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.IdentityServices.RequestApplicationSecurityToken::get_RequestType()
0x7a4e  ldstr    aAuthenticatorI// "authenticator/issue"
0x7a53  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x7a58  brtrue.s loc_7A72
0x7a5a  ldarg.0
0x7a5b  ldfld    class Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenServiceConfiguration Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenService::configuration
0x7a60  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenServiceConfiguration::get_AuthenticatorTokenLifetime()
0x7a65  stloc.2
0x7a66  ldarg.0
0x7a67  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenService::GetOutboundClaimsForAuthenticatorToken()
0x7a6c  stloc.3
0x7a6d  br       loc_7DF1
0x7a72  ldarg.1
0x7a73  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.IdentityServices.RequestApplicationSecurityToken::get_RequestType()
0x7a78  ldstr    aLoopbackIssue// "loopback/issue"
0x7a7d  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x7a82  brtrue.s loc_7AF9
0x7a84  ldarg.1
0x7a85  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.IdentityServices.RequestApplicationSecurityToken::get_LoopbackLifetime()
0x7a8a  brfalse.s loc_7ACA
0x7a8c  ldc.i4   0x120C01E
0x7a91  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x7a96  ldc.i4.s 0x32
0x7a98  ldstr    aLoopbackLifeti// "Loopback lifetime set to:{0}"
0x7a9d  ldc.i4.1
0x7a9e  newarr   [mscorlib]System.Object
0x7aa3  stloc.s  0x10
0x7aa5  ldloc.s  0x10
0x7aa7  ldc.i4.0
0x7aa8  ldarg.1
0x7aa9  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.IdentityServices.RequestApplicationSecurityToken::get_LoopbackLifetime()
0x7aae  box      [mscorlib]System.Int32
0x7ab3  stelem.ref
0x7ab4  ldloc.s  0x10
0x7ab6  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x7abb  ldarg.1
0x7abc  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.IdentityServices.RequestApplicationSecurityToken::get_LoopbackLifetime()
0x7ac1  conv.r8
0x7ac2  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0x7ac7  stloc.2
0x7ac8  br.s     loc_7AEC
0x7aca  ldc.i4   0x120C01F
0x7acf  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x7ad4  ldc.i4.s 0x64
0x7ad6  ldstr    aLoopbackLifeti_0// "Loopback lifetime set to default config"...
0x7adb  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x7ae0  ldarg.0
0x7ae1  ldfld    class Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenServiceConfiguration Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenService::configuration
0x7ae6  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenServiceConfiguration::get_LoopbackTokenLifetime()
0x7aeb  stloc.2
0x7aec  ldarg.0
0x7aed  ldarg.1
0x7aee  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenService::GetOutboundClaimsForLoopbackToken(class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityServices.RequestApplicationSecurityToken request)
0x7af3  stloc.3
0x7af4  br       loc_7DF1
0x7af9  ldarg.1
0x7afa  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.IdentityServices.RequestApplicationSecurityToken::get_RequestType()
0x7aff  ldstr    aImpersonationI// "impersonation/issue"
0x7b04  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x7b09  brtrue.s loc_7B24
0x7b0b  ldarg.0
0x7b0c  ldfld    class Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenServiceConfiguration Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenService::configuration
0x7b11  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenServiceConfiguration::get_ImpersonationTokenLifetime()
0x7b16  stloc.2
0x7b17  ldarg.0
0x7b18  ldarg.1
0x7b19  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenService::GetOutboundClaimsForImpersonationToken(class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityServices.RequestApplicationSecurityToken request)
0x7b1e  stloc.3
0x7b1f  br       loc_7DF1
0x7b24  ldarg.1
0x7b25  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.IdentityServices.RequestApplicationSecurityToken::get_RequestType()
0x7b2a  ldstr    aPreauthwopiIss// "preauthwopi/issue"
0x7b2f  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x7b34  brtrue.s loc_7B51
0x7b36  ldarg.0
0x7b37  ldfld    class Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenServiceConfiguration Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenService::configuration
0x7b3c  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenServiceConfiguration::get_PreAuthWopiTokenLifetime()
0x7b41  stloc.2
0x7b42  ldarg.0
0x7b43  ldarg.1
0x7b44  ldc.i4.1
0x7b45  ldc.i4.0
0x7b46  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenService::GetOutboundClaimsForAppPlusUserWopiToken(class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityServices.RequestApplicationSecurityToken request, bool shortLived, bool isAppOnly)
0x7b4b  stloc.3
0x7b4c  br       loc_7DF1
0x7b51  ldarg.1
0x7b52  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.IdentityServices.RequestApplicationSecurityToken::get_RequestType()
0x7b57  ldstr    aAppplususerwop_0// "appplususerwopi/issue"
0x7b5c  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x7b61  brtrue.s loc_7BDA
0x7b63  ldarg.1
0x7b64  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.IdentityServices.RequestApplicationSecurityToken::get_LoopbackLifetime()
0x7b69  brfalse.s loc_7BA9
0x7b6b  ldc.i4   0x120C020
0x7b70  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x7b75  ldc.i4.s 0x32
0x7b77  ldstr    aLoopbackLifeti// "Loopback lifetime set to:{0}"
0x7b7c  ldc.i4.1
0x7b7d  newarr   [mscorlib]System.Object
0x7b82  stloc.s  0x11
0x7b84  ldloc.s  0x11
0x7b86  ldc.i4.0
0x7b87  ldarg.1
0x7b88  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.IdentityServices.RequestApplicationSecurityToken::get_LoopbackLifetime()
0x7b8d  box      [mscorlib]System.Int32
0x7b92  stelem.ref
0x7b93  ldloc.s  0x11
0x7b95  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x7b9a  ldarg.1
0x7b9b  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.IdentityServices.RequestApplicationSecurityToken::get_LoopbackLifetime()
0x7ba0  conv.r8
0x7ba1  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0x7ba6  stloc.2
0x7ba7  br.s     loc_7BCB
0x7ba9  ldc.i4   0x120C021
0x7bae  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x7bb3  ldc.i4.s 0x64
0x7bb5  ldstr    aLoopbackLifeti_0// "Loopback lifetime set to default config"...
0x7bba  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x7bbf  ldarg.0
0x7bc0  ldfld    class Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenServiceConfiguration Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenService::configuration
0x7bc5  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenServiceConfiguration::get_AppPlusUserWopiTokenLifetime()
0x7bca  stloc.2
0x7bcb  ldarg.0
0x7bcc  ldarg.1
0x7bcd  ldc.i4.0
0x7bce  ldc.i4.0
0x7bcf  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenService::GetOutboundClaimsForAppPlusUserWopiToken(class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityServices.RequestApplicationSecurityToken request, bool shortLived, bool isAppOnly)
0x7bd4  stloc.3
0x7bd5  br       loc_7DF1
0x7bda  ldarg.1
0x7bdb  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.IdentityServices.RequestApplicationSecurityToken::get_RequestType()
0x7be0  ldstr    aApponlywopiIss// "apponlywopi/issue"
0x7be5  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x7bea  brtrue   loc_7C7F
0x7bef  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPWOPIHost::WopiAppOnlyTokenFeature
0x7bf4  ldstr    a05312016// "05/31/2016"
0x7bf9  ldstr    aWopiapponlytok// "WopiAppOnlyTokenFeature"
0x7bfe  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid, string, string)
0x7c03  brtrue   loc_7DF1
0x7c08  ldarg.1
0x7c09  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.IdentityServices.RequestApplicationSecurityToken::get_LoopbackLifetime()
0x7c0e  brfalse.s loc_7C4E
0x7c10  ldc.i4   0x12487D6
0x7c15  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x7c1a  ldc.i4.s 0x32
0x7c1c  ldstr    aLoopbackLifeti// "Loopback lifetime set to:{0}"
0x7c21  ldc.i4.1
0x7c22  newarr   [mscorlib]System.Object
0x7c27  stloc.s  0x12
0x7c29  ldloc.s  0x12
0x7c2b  ldc.i4.0
0x7c2c  ldarg.1
0x7c2d  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.IdentityServices.RequestApplicationSecurityToken::get_LoopbackLifetime()
0x7c32  box      [mscorlib]System.Int32
0x7c37  stelem.ref
0x7c38  ldloc.s  0x12
0x7c3a  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x7c3f  ldarg.1
0x7c40  callvirt instance int32 [Microsoft.SharePoint]Microsoft.SharePoint.IdentityServices.RequestApplicationSecurityToken::get_LoopbackLifetime()
0x7c45  conv.r8
0x7c46  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMinutes(float64)
0x7c4b  stloc.2
0x7c4c  br.s     loc_7C70
0x7c4e  ldc.i4   0x12487D7
0x7c53  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x7c58  ldc.i4.s 0x64
0x7c5a  ldstr    aLoopbackLifeti_0// "Loopback lifetime set to default config"...
0x7c5f  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x7c64  ldarg.0
0x7c65  ldfld    class Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenServiceConfiguration Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenService::configuration
0x7c6a  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenServiceConfiguration::get_AppPlusUserWopiTokenLifetime()
0x7c6f  stloc.2
0x7c70  ldarg.0
0x7c71  ldarg.1
0x7c72  ldc.i4.0
0x7c73  ldc.i4.1
0x7c74  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenService::GetOutboundClaimsForAppPlusUserWopiToken(class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityServices.RequestApplicationSecurityToken request, bool shortLived, bool isAppOnly)
0x7c79  stloc.3
0x7c7a  br       loc_7DF1
0x7c7f  ldarg.1
0x7c80  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.IdentityServices.RequestApplicationSecurityToken::get_RequestType()
0x7c85  ldstr    aProofIssue// "proof/issue"
0x7c8a  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x7c8f  brtrue.s loc_7CC4
0x7c91  ldnull
0x7c92  stloc.s  5
0x7c94  ldarg.0
0x7c95  ldfld    class Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenServiceConfiguration Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenService::configuration
0x7c9a  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenServiceConfiguration::get_ProofTokenLifetime()
0x7c9f  stloc.2
0x7ca0  ldarg.0
0x7ca1  ldarg.1
0x7ca2  ldloca.s 5
0x7ca4  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenService::GetOutboundClaimsForProofToken(class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityServices.RequestApplicationSecurityToken request, [out] class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPSymmetricKeyClaim& securityKey)
0x7ca9  stloc.3
0x7caa  ldloc.s  5
0x7cac  brfalse  loc_7DF1
0x7cb1  ldloc.s  5
0x7cb3  callvirt instance unsigned int8[] [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPSymmetricKeyClaim::get_SymmetricKey()
0x7cb8  call     string [mscorlib]System.Convert::ToBase64String(unsigned int8[])
0x7cbd  stloc.s  4
0x7cbf  br       loc_7DF1
0x7cc4  ldarg.1
0x7cc5  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.IdentityServices.RequestApplicationSecurityToken::get_RequestType()
0x7cca  ldstr    aEstsIssue// "ests/issue"
0x7ccf  call     int32 [mscorlib]System.String::CompareOrdinal(string, string)
0x7cd4  brtrue   loc_7D76
0x7cd9  ldarg.0
0x7cda  ldarg.1
0x7cdb  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.IdentityServices.RequestApplicationSecurityToken::get_AppliesTo()
0x7ce0  ldarg.1
0x7ce1  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.IdentityServices.RequestApplicationSecurityToken::get_ApplicationContext()
0x7ce6  call     instance class [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationResult Microsoft.SharePoint.IdentityModel.SPApplicationSecurityTokenService::IssueEstsToken(string estsEndpoint, string resource)
0x7ceb  stloc.s  6
0x7ced  ldloca.s 7
0x7cef  ldstr    a6fb777bd5db34e// "6fb777bd-5db3-4e81-ad55-06708dc49e1f"
0x7cf4  call     instance void [mscorlib]System.Guid::.ctor(string)
0x7cf9  ldnull
0x7cfa  stloc.s  8
0x7cfc  ldloc.s  7
0x7cfe  ldstr    a05312017// "05/31/2017"
0x7d03  ldstr    aSppopEststoken// "SPPOP_ESTSTokenCacheFeature"
0x7d08  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid, string, string)
0x7d0d  brtrue.s loc_7D3F
0x7d0f  ldloc.s  6
0x7d11  callvirt instance string [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationResult::get_AccessToken()
0x7d16  ldloc.s  6
0x7d18  callvirt instance valuetype [mscorlib]System.DateTimeOffset [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationResult::get_ExpiresOn()
0x7d1d  stloc.s  0x13
0x7d1f  ldloca.s 0x13
0x7d21  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTimeOffset::get_UtcDateTime()
0x7d26  ldloc.s  6
0x7d28  callvirt instance valuetype [mscorlib]System.DateTimeOffset [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationResult::get_ExpiresOn()
0x7d2d  stloc.s  0x14
0x7d2f  ldloca.s 0x14
0x7d31  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTimeOffset::get_UtcDateTime()
0x7d36  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.IdentityServices.RequestApplicationSecurityTokenResponse::.ctor(string, valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x7d3b  stloc.s  8
0x7d3d  br.s     loc_7D6D
0x7d3f  ldloc.s  6
0x7d41  callvirt instance string [Microsoft.IdentityModel.Clients.ActiveDirectory]Microsoft.IdentityModel.Clients.ActiveDirectory.AuthenticationResult::get_AccessToken()
0x7d46  ldloc.s  6
  ... truncated ...
```
