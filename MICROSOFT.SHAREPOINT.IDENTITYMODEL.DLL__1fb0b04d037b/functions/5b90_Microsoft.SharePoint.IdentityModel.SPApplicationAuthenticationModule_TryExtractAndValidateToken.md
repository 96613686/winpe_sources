# Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::TryExtractAndValidateToken

- ea: `0x5b90`
- end: `0x6265`
- name: `Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::TryExtractAndValidateToken`
- size: `1749`
- prototype: ``
- caller_count: `1`
- callee_count: `28`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x3bb0`

## callees

- `0x30a0`
- `0x5b90`
- `0x6970`
- `0x6990`
- `0x6ab0`
- `0x6ca0`
- `0x6d40`
- `0x6e80`
- `0x6f00`
- `0x10650`
- `0x10a90`
- `0x10ad0`
- `0x10bd0`
- `0x10c30`
- `0x10da0`
- `0x11c20`
- `0x11c50`
- `0x134d0`
- `0x13600`
- `0x13620`
- `0x148f0`
- `0x14bc0`
- `0x14cb0`
- `0x183e0`
- `0x1c000`
- `0x283e0`
- `0x28420`
- `0x284f0`

## string_xrefs

- `0x5bd3`: `SPApplicationAuthenticationModule: Validate badger token.`
- `0x5c2c`: `OAuth Token: {0}`
- `0x5c54`: `Exception while decoding token: {0}`
- `0x5cbb`: `SPApplicationAuthenticationModule: Read Identity Proof Token`
- `0x5cca`: `TryExtractAndValidateToken`
- `0x5f62`: `TryExtractAndValidateToken`
- `0x5fbf`: `TryExtractAndValidateToken`
- `0x5d04`: `SPApplicationAuthenticationModule: Read Token`
- `0x5d31`: `SPApplicationAuthenticationModule: Invalid token or signature. Exception: {0}`
- `0x5d68`: `SPApplicationAuthenticationModule: Invalid token '{0}'`
- `0x5dc2`: `SPApplicationAuthenticationModule: preauth token detected and this endpoint is allowed. '{0}'`
- `0x5df6`: `SPApplicationAuthenticationModule: preauth token detected and this endpoint is not allowed. '{0}'`
- `0x5e28`: `InvalidAccessTokenOnEndPoint`
- `0x5ede`: `InvalidAccessTokenOnEndPoint`
- `0x5e7b`: `SPApplicationAuthenticationModule: appplususerwopi token detected and this endpoint is allowed. '{0}'`
- `0x5eac`: `SPApplicationAuthenticationModule: appplususerwopi token detected and this endpoint is not allowed. '{0}'`
- `0x5f20`: `SPApplicationAuthenticationModule: Proof token found and is sent to be validated.`
- `0x6078`: `SPApplicationAuthenticationModule: Proof token found and is sent to be validated.`
- `0x600c`: `ShareByLinkWithProofToken`
- `0x6156`: `ShareByLinkWithProofToken`
- `0x602c`: `SPApplicationAuthenticationModule: Verify if identity token is valid for current url.`
- `0x6082`: `Verifying Token + Proof Token`
- `0x60dd`: `Verifying Token`
- `0x6194`: `SPApplicationAuthenticationModule: Token has expired [ValidFrom:'{0}'], [ValidTo:'{1}']. Exception: `
- `0x6224`: `SPApplicationAuthenticationModule: Successfully handled authorization actor token.`
- `0x623c`: `SPApplicationAuthenticationModule: Authorization Actor Token validation failed.`
- `0x6246`: `Authorization Actor Token validation failed.`

## pseudocode

```c

```

## disassembly

```asm
0x5b90  ldarg.3
0x5b91  ldnull
0x5b92  stind.ref
0x5b93  ldarg.1
0x5b94  brtrue.s loc_5BA1
0x5b96  ldstr    aHttpcontext// "httpContext"
0x5b9b  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x5ba0  throw
0x5ba1  ldarg.2
0x5ba2  ldnull
0x5ba3  stind.ref
0x5ba4  ldnull
0x5ba5  stloc.0
0x5ba6  ldc.i4.0
0x5ba7  stloc.1
0x5ba8  ldloc.1
0x5ba9  brfalse.s loc_5BE7
0x5bab  ldc.i4   0x3777
0x5bb0  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x5bb5  brfalse.s loc_5BE7
0x5bb7  ldarg.0
0x5bb8  ldarg.1
0x5bb9  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x5bbe  ldloca.s 0
0x5bc0  call     instance bool Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::TryParseBadgerToken(class [System.Web]System.Web.HttpRequest request, [out] string& accessToken)
0x5bc5  brfalse.s loc_5BE7
0x5bc7  ldc.i4   0x215150F
0x5bcc  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x5bd1  ldc.i4.s 0x32
0x5bd3  ldstr    aSpapplicationa_84// "SPApplicationAuthenticationModule: Vali"...
0x5bd8  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x5bdd  ldarg.0
0x5bde  ldloc.0
0x5bdf  call     instance class [mscorlib]System.Security.Claims.ClaimsPrincipal Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::ValidateBadgerToken(string token)
0x5be4  pop
0x5be5  ldc.i4.1
0x5be6  ret
0x5be7  ldarg.0
0x5be8  ldarg.1
0x5be9  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x5bee  ldloca.s 0
0x5bf0  call     instance bool Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::TryParseOAuthToken(class [System.Web]System.Web.HttpRequest request, [out] string& accessToken)
0x5bf5  brtrue.s loc_5BF9
0x5bf7  ldc.i4.0
0x5bf8  ret
0x5bf9  ldloc.0
0x5bfa  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5bff  brfalse.s loc_5C19
0x5c01  ldc.i4   0xCB29F
0x5c06  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x5c0b  ldc.i4.s 0x64
0x5c0d  ldstr    aSpapplicationa_85// "SPApplicationAuthenticationModule: Auth"...
0x5c12  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x5c17  ldc.i4.0
0x5c18  ret
0x5c19  ldloc.0
0x5c1a  call     string Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::GetReadableTokenString(string token)
0x5c1f  stloc.2
0x5c20  ldc.i4   0x10054D4
0x5c25  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x5c2a  ldc.i4.s 0x32
0x5c2c  ldstr    aOauthToken0// "OAuth Token: {0}"
0x5c31  ldc.i4.1
0x5c32  newarr   [mscorlib]System.Object
0x5c37  stloc.s  0x14
0x5c39  ldloc.s  0x14
0x5c3b  ldc.i4.0
0x5c3c  ldloc.2
0x5c3d  stelem.ref
0x5c3e  ldloc.s  0x14
0x5c40  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x5c45  leave.s  loc_5C74
0x5c47  stloc.3
0x5c48  ldc.i4   0x10054D5
0x5c4d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x5c52  ldc.i4.s 0xA
0x5c54  ldstr    aExceptionWhile// "Exception while decoding token: {0}"
0x5c59  ldc.i4.1
0x5c5a  newarr   [mscorlib]System.Object
0x5c5f  stloc.s  0x15
0x5c61  ldloc.s  0x15
0x5c63  ldc.i4.0
0x5c64  ldloc.3
0x5c65  callvirt instance string [mscorlib]System.Object::ToString()
0x5c6a  stelem.ref
0x5c6b  ldloc.s  0x15
0x5c6d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x5c72  leave.s  loc_5C74
0x5c74  ldc.i4   0x25B8C6
0x5c79  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x5c7e  ldc.i4.s 0x64
0x5c80  ldstr    aOauthRequest// "OAuth Request!"
0x5c85  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x5c8a  ldnull
0x5c8b  stloc.s  4
0x5c8d  ldnull
0x5c8e  stloc.s  5
0x5c90  ldnull
0x5c91  stloc.s  6
0x5c93  ldc.i4   0x2B3E
0x5c98  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x5c9d  brfalse.s loc_5CF8
0x5c9f  ldarg.0
0x5ca0  ldarg.1
0x5ca1  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x5ca6  ldloca.s 6
0x5ca8  call     instance bool Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::TryParseProofToken(class [System.Web]System.Web.HttpRequest request, [out] string& proofToken)
0x5cad  brfalse.s loc_5CF8
0x5caf  ldc.i4   0x10D93CA
0x5cb4  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x5cb9  ldc.i4.s 0x32
0x5cbb  ldstr    aSpapplicationa_86// "SPApplicationAuthenticationModule: Read"...
0x5cc0  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x5cc5  ldc.i4   0x271E
0x5cca  ldstr    aTryextractandv// "TryExtractAndValidateToken"
0x5ccf  ldstr    aDDbsElZltDevSt// "d:\\dbs\\el\\zlt\\dev\\sts\\identitymod"...
0x5cd4  ldc.i4   0xB40
0x5cd9  call     class [Microsoft.Cobalt.Base]Cobalt.PerformanceTracing.ComponentTracer [Microsoft.Cobalt.Base]Cobalt.PerformanceTracing.ComponentTracer::Create(valuetype [Microsoft.Cobalt.Base]Cobalt.ComponentId, string, string, int32)
0x5cde  stloc.s  0x16
0x5ce0  ldloc.s  6
0x5ce2  ldloc.0
0x5ce3  call     class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPIdentityProofToken Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenUtilities::CreateFromJsonWebToken(string proofTokenString, string identityTokenString)
0x5ce8  stloc.s  5
0x5cea  leave.s  loc_5D21
0x5cec  ldloc.s  0x16
0x5cee  brfalse.s loc_5CF7
0x5cf0  ldloc.s  0x16
0x5cf2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5cf7  endfinally
0x5cf8  ldc.i4   0x2151510
0x5cfd  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x5d02  ldc.i4.s 0x32
0x5d04  ldstr    aSpapplicationa_87// "SPApplicationAuthenticationModule: Read"...
0x5d09  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x5d0e  ldarg.0
0x5d0f  call     instance class Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::get_JsonWebSecurityTokenHandler()
0x5d14  ldloc.0
0x5d15  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityTokenHandler::ReadToken(string)
0x5d1a  isinst   [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken
0x5d1f  stloc.s  4
0x5d21  leave.s  loc_5D89
0x5d23  stloc.s  7
0x5d25  ldc.i4   0x24465A
0x5d2a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x5d2f  ldc.i4.s 0x14
0x5d31  ldstr    aSpapplicationa_88// "SPApplicationAuthenticationModule: Inva"...
0x5d36  ldc.i4.1
0x5d37  newarr   [mscorlib]System.Object
0x5d3c  stloc.s  0x17
0x5d3e  ldloc.s  0x17
0x5d40  ldc.i4.0
0x5d41  ldloc.s  7
0x5d43  callvirt instance string [mscorlib]System.Object::ToString()
0x5d48  stelem.ref
0x5d49  ldloc.s  0x17
0x5d4b  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x5d50  ldc.i4   0x28C7
0x5d55  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x5d5a  brfalse.s loc_5D81
0x5d5c  ldc.i4   0x6943C6
0x5d61  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x5d66  ldc.i4.s 0x14
0x5d68  ldstr    aSpapplicationa_89// "SPApplicationAuthenticationModule: Inva"...
0x5d6d  ldc.i4.1
0x5d6e  newarr   [mscorlib]System.Object
0x5d73  stloc.s  0x18
0x5d75  ldloc.s  0x18
0x5d77  ldc.i4.0
0x5d78  ldloc.0
0x5d79  stelem.ref
0x5d7a  ldloc.s  0x18
0x5d7c  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x5d81  ldloc.s  7
0x5d83  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPInvalidTokenSignatureOAuthException::.ctor(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenException)
0x5d88  throw
0x5d89  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPWOPIHost::get_IsPreAuthWopiFeatureEnabled()
0x5d8e  brfalse  loc_5EF9
0x5d93  ldloc.s  4
0x5d95  call     bool Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::IsPreAuthRequest(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken token)
0x5d9a  brfalse  loc_5E43
0x5d9f  ldnull
0x5da0  stloc.s  8
0x5da2  ldarg.1
0x5da3  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x5da8  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x5dad  ldloca.s 8
0x5daf  call     bool Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::TryMatchAllowedApplicationPreAuthEndPoint(class [System]System.Uri uri, [out] class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint& endPoint)
0x5db4  brfalse.s loc_5DEA
0x5db6  ldc.i4   0x1001841
0x5dbb  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x5dc0  ldc.i4.s 0x32
0x5dc2  ldstr    aSpapplicationa_90// "SPApplicationAuthenticationModule: prea"...
0x5dc7  ldc.i4.1
0x5dc8  newarr   [mscorlib]System.Object
0x5dcd  stloc.s  0x19
0x5dcf  ldloc.s  0x19
0x5dd1  ldc.i4.0
0x5dd2  ldarg.1
0x5dd3  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x5dd8  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x5ddd  stelem.ref
0x5dde  ldloc.s  0x19
0x5de0  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x5de5  br       loc_5EF9
0x5dea  ldc.i4   0x1001842
0x5def  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x5df4  ldc.i4.s 0x32
0x5df6  ldstr    aSpapplicationa_91// "SPApplicationAuthenticationModule: prea"...
0x5dfb  ldc.i4.1
0x5dfc  newarr   [mscorlib]System.Object
0x5e01  stloc.s  0x1A
0x5e03  ldloc.s  0x1A
0x5e05  ldc.i4.0
0x5e06  ldarg.1
0x5e07  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x5e0c  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x5e11  stelem.ref
0x5e12  ldloc.s  0x1A
0x5e14  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x5e19  ldstr    aInvalidRequest// "invalid_request"
0x5e1e  ldc.i4   0x2DC6C1
0x5e23  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x5e28  ldstr    aInvalidaccesst// "InvalidAccessTokenOnEndPoint"
0x5e2d  ldc.i4.0
0x5e2e  newarr   [mscorlib]System.Object
0x5e33  call     string [Microsoft.SharePoint]Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo, string, object[])
0x5e38  ldc.i4   0x191
0x5e3d  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPOAuthException::.ctor(string, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPOAuthErrorCode, string, int32)
0x5e42  throw
0x5e43  ldloc.s  4
0x5e45  call     bool Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::IsAppPlusUserWopiRequest(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken token)
0x5e4a  brtrue.s loc_5E58
0x5e4c  ldloc.s  4
0x5e4e  call     bool Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::IsAppOnlyWopiRequest(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken token)
0x5e53  brfalse  loc_5EF9
0x5e58  ldnull
0x5e59  stloc.s  9
0x5e5b  ldarg.1
0x5e5c  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x5e61  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x5e66  ldloca.s 9
0x5e68  call     bool Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::TryMatchAllowedApplicationAppPlusUserWopiEndPoint(class [System]System.Uri uri, [out] class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.OAuth2.SPApplicationAuthenticationAllowedEndPoint& endPoint)
0x5e6d  brfalse.s loc_5EA0
0x5e6f  ldc.i4   0x111E522
0x5e74  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x5e79  ldc.i4.s 0x32
0x5e7b  ldstr    aSpapplicationa_92// "SPApplicationAuthenticationModule: appp"...
0x5e80  ldc.i4.1
0x5e81  newarr   [mscorlib]System.Object
0x5e86  stloc.s  0x1B
0x5e88  ldloc.s  0x1B
0x5e8a  ldc.i4.0
0x5e8b  ldarg.1
0x5e8c  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x5e91  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x5e96  stelem.ref
0x5e97  ldloc.s  0x1B
0x5e99  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x5e9e  br.s     loc_5EF9
0x5ea0  ldc.i4   0x111E523
0x5ea5  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x5eaa  ldc.i4.s 0x32
0x5eac  ldstr    aSpapplicationa_93// "SPApplicationAuthenticationModule: appp"...
0x5eb1  ldc.i4.1
0x5eb2  newarr   [mscorlib]System.Object
0x5eb7  stloc.s  0x1C
0x5eb9  ldloc.s  0x1C
0x5ebb  ldc.i4.0
0x5ebc  ldarg.1
0x5ebd  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x5ec2  callvirt instance class [System]System.Uri [System.Web]System.Web.HttpRequest::get_Url()
0x5ec7  stelem.ref
0x5ec8  ldloc.s  0x1C
0x5eca  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x5ecf  ldstr    aInvalidRequest// "invalid_request"
0x5ed4  ldc.i4   0x2DC6C1
0x5ed9  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x5ede  ldstr    aInvalidaccesst// "InvalidAccessTokenOnEndPoint"
0x5ee3  ldc.i4.0
0x5ee4  newarr   [mscorlib]System.Object
0x5ee9  call     string [Microsoft.SharePoint]Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo, string, object[])
0x5eee  ldc.i4   0x191
0x5ef3  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPOAuthException::.ctor(string, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPOAuthErrorCode, string, int32)
0x5ef8  throw
0x5ef9  ldc.i4   0x2B3E
0x5efe  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x5f03  brfalse  loc_605C
0x5f08  ldloc.s  6
0x5f0a  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x5f0f  brtrue   loc_605C
0x5f14  ldc.i4   0x10D93CB
0x5f19  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x5f1e  ldc.i4.s 0x32
0x5f20  ldstr    aSpapplicationa_94// "SPApplicationAuthenticationModule: Proo"...
0x5f25  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x5f2a  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenHandler Microsoft.SharePoint.IdentityModel.SPClaimsUtility::GetIdentityProofTokenHandler()
0x5f2f  stloc.s  0xA
0x5f31  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x5f36  stloc.s  0xB
0x5f38  ldloc.s  0xB
  ... truncated ...
```
