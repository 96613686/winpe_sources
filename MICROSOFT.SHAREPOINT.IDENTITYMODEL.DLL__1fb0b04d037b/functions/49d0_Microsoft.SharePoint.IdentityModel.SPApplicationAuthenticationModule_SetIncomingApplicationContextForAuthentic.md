# Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::SetIncomingApplicationContextForAuthenticatedWopiRequest

- ea: `0x49d0`
- end: `0x4c91`
- name: `Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::SetIncomingApplicationContextForAuthenticatedWopiRequest`
- size: `705`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x30a0`
- `0x49d0`
- `0x4ca0`
- `0x4d60`
- `0x14f10`
- `0x14f40`
- `0x28920`

## string_xrefs

- `0x49d8`: `wopiAccessToken`
- `0x49e6`: `authToken`
- `0x4a14`: `SPApplicationAuthenticationModule: Invalid access_token in query string. Exception: {0}`
- `0x4a39`: `Verifying access_token`
- `0x4a61`: `SPApplicationAuthenticationModule: access_token in query string has expired [ValidFrom:'{0}'], [ValidTo:'{1}']. Exception: `
- `0x4b03`: `SPApplicationAuthenticationModule: access_token in query string and token in Auth header are not issued for same user.`
- `0x4b5a`: `SPApplicationAuthenticationModule: access_token in query string doesn't have application context claim`
- `0x4bc1`: `SPApplicationAuthenticationModule: Auth token doesn't have appid claim`
- `0x4c17`: `SPApplicationAuthenticationModule: access_token in query string and token in Auth header are not issued for same app.`

## pseudocode

```c

```

## disassembly

```asm
0x49d0  ldarg.1
0x49d1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x49d6  brfalse.s loc_49E3
0x49d8  ldstr    aWopiaccesstoke// "wopiAccessToken"
0x49dd  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x49e2  throw
0x49e3  ldarg.2
0x49e4  brtrue.s loc_49F1
0x49e6  ldstr    aAuthtoken// "authToken"
0x49eb  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x49f0  throw
0x49f1  ldnull
0x49f2  stloc.0
0x49f3  ldarg.0
0x49f4  call     instance class Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::get_JsonWebSecurityTokenHandler()
0x49f9  ldarg.1
0x49fa  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityTokenHandler::ReadToken(string)
0x49ff  isinst   [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken
0x4a04  stloc.0
0x4a05  leave.s  loc_4A39
0x4a07  stloc.1
0x4a08  ldc.i4   0x6477D0
0x4a0d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x4a12  ldc.i4.s 0x14
0x4a14  ldstr    aSpapplicationa_56// "SPApplicationAuthenticationModule: Inva"...
0x4a19  ldc.i4.1
0x4a1a  newarr   [mscorlib]System.Object
0x4a1f  stloc.s  6
0x4a21  ldloc.s  6
0x4a23  ldc.i4.0
0x4a24  ldloc.1
0x4a25  callvirt instance string [mscorlib]System.Object::ToString()
0x4a2a  stelem.ref
0x4a2b  ldloc.s  6
0x4a2d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x4a32  ldloc.1
0x4a33  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPInvalidTokenSignatureOAuthException::.ctor(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenException)
0x4a38  throw
0x4a39  ldstr    aVerifyingAcces// "Verifying access_token"
0x4a3e  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string)
0x4a43  stloc.s  7
0x4a45  ldarg.0
0x4a46  call     instance class Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::get_JsonWebSecurityTokenHandler()
0x4a4b  ldloc.0
0x4a4c  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenHandler::ValidateToken(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken)
0x4a51  pop
0x4a52  leave.s  loc_4AB0
0x4a54  stloc.2
0x4a55  ldc.i4   0x6477D1
0x4a5a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x4a5f  ldc.i4.s 0x14
0x4a61  ldstr    aSpapplicationa_57// "SPApplicationAuthenticationModule: acce"...
0x4a66  ldc.i4.3
0x4a67  newarr   [mscorlib]System.Object
0x4a6c  stloc.s  8
0x4a6e  ldloc.s  8
0x4a70  ldc.i4.0
0x4a71  ldloc.0
0x4a72  callvirt instance valuetype [mscorlib]System.DateTime [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_ValidFrom()
0x4a77  box      [mscorlib]System.DateTime
0x4a7c  stelem.ref
0x4a7d  ldloc.s  8
0x4a7f  ldc.i4.1
0x4a80  ldloc.0
0x4a81  callvirt instance valuetype [mscorlib]System.DateTime [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_ValidTo()
0x4a86  box      [mscorlib]System.DateTime
0x4a8b  stelem.ref
0x4a8c  ldloc.s  8
0x4a8e  ldc.i4.2
0x4a8f  ldloc.2
0x4a90  callvirt instance string [mscorlib]System.Object::ToString()
0x4a95  stelem.ref
0x4a96  ldloc.s  8
0x4a98  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x4a9d  ldloc.0
0x4a9e  callvirt instance valuetype [mscorlib]System.DateTime [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_ValidFrom()
0x4aa3  ldloc.0
0x4aa4  callvirt instance valuetype [mscorlib]System.DateTime [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_ValidTo()
0x4aa9  ldloc.2
0x4aaa  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPExpiredTokenOAuthException::.ctor(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime, class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenExpiredException)
0x4aaf  throw
0x4ab0  leave.s  loc_4ABE
0x4ab2  ldloc.s  7
0x4ab4  brfalse.s loc_4ABD
0x4ab6  ldloc.s  7
0x4ab8  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4abd  endfinally
0x4abe  ldloc.0
0x4abf  call     bool Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::IsLoopbackToken(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken token)
0x4ac4  brfalse  loc_4C90
0x4ac9  ldloc.0
0x4aca  call     bool Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::RequiresAuthenticationToken(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken token)
0x4acf  brfalse  loc_4C90
0x4ad4  ldstr    aIsauthenticate// "IsAuthenticatedWopiRequest"
0x4ad9  ldstr    aTrue// "true"
0x4ade  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPThreadContext::Set(string, object)
0x4ae3  ldarg.0
0x4ae4  ldloc.0
0x4ae5  ldstr    aNameid// "nameid"
0x4aea  ldarg.2
0x4aeb  ldstr    aPuid// "puid"
0x4af0  call     instance bool Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::AreTokenClaimsMatching(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken wopiToken, string wopiClaimType, class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken authToken, string authClaimType)
0x4af5  brtrue.s loc_4B37
0x4af7  ldc.i4   0x651648
0x4afc  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x4b01  ldc.i4.s 0x14
0x4b03  ldstr    aSpapplicationa_58// "SPApplicationAuthenticationModule: acce"...
0x4b08  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x4b0d  ldstr    aInvalidRequest// "invalid_request"
0x4b12  ldc.i4   0x2DC6C1
0x4b17  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x4b1c  ldstr    aAuthenticatedw// "AuthenticatedWopiAppOrUserMismatch"
0x4b21  ldc.i4.0
0x4b22  newarr   [mscorlib]System.Object
0x4b27  call     string [Microsoft.SharePoint]Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo, string, object[])
0x4b2c  ldc.i4   0x191
0x4b31  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPOAuthException::.ctor(string, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPOAuthErrorCode, string, int32)
0x4b36  throw
0x4b37  ldloc.0
0x4b38  ldstr    aAppctx// "appctx"
0x4b3d  call     class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim Microsoft.SharePoint.IdentityModel.SPClaimsUtility::GetSingleClaim(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken token, string claimType)
0x4b42  stloc.3
0x4b43  ldloc.3
0x4b44  brfalse.s loc_4B4E
0x4b46  ldloc.3
0x4b47  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_Value()
0x4b4c  brtrue.s loc_4B8E
0x4b4e  ldc.i4   0x651649
0x4b53  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x4b58  ldc.i4.s 0xA
0x4b5a  ldstr    aSpapplicationa_59// "SPApplicationAuthenticationModule: acce"...
0x4b5f  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x4b64  ldstr    aInvalidRequest// "invalid_request"
0x4b69  ldc.i4   0x2DC6C1
0x4b6e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x4b73  ldstr    aAuthenticatedw// "AuthenticatedWopiAppOrUserMismatch"
0x4b78  ldc.i4.0
0x4b79  newarr   [mscorlib]System.Object
0x4b7e  call     string [Microsoft.SharePoint]Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo, string, object[])
0x4b83  ldc.i4   0x191
0x4b88  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPOAuthException::.ctor(string, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPOAuthErrorCode, string, int32)
0x4b8d  throw
0x4b8e  ldloc.3
0x4b8f  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_Value()
0x4b94  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WopiTokenContext [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPWOPIHost::ParseApplicationContext(string)
0x4b99  stloc.s  4
0x4b9b  ldarg.2
0x4b9c  ldstr    aAppid// "appid"
0x4ba1  call     class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim Microsoft.SharePoint.IdentityModel.SPClaimsUtility::GetSingleClaim(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken token, string claimType)
0x4ba6  stloc.s  5
0x4ba8  ldloc.s  5
0x4baa  brfalse.s loc_4BB5
0x4bac  ldloc.s  5
0x4bae  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_Value()
0x4bb3  brtrue.s loc_4BF5
0x4bb5  ldc.i4   0x65164A
0x4bba  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x4bbf  ldc.i4.s 0xA
0x4bc1  ldstr    aSpapplicationa_60// "SPApplicationAuthenticationModule: Auth"...
0x4bc6  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x4bcb  ldstr    aInvalidRequest// "invalid_request"
0x4bd0  ldc.i4   0x2DC6C1
0x4bd5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x4bda  ldstr    aAuthenticatedw// "AuthenticatedWopiAppOrUserMismatch"
0x4bdf  ldc.i4.0
0x4be0  newarr   [mscorlib]System.Object
0x4be5  call     string [Microsoft.SharePoint]Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo, string, object[])
0x4bea  ldc.i4   0x191
0x4bef  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPOAuthException::.ctor(string, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPOAuthErrorCode, string, int32)
0x4bf4  throw
0x4bf5  ldloc.s  4
0x4bf7  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WopiTokenContext::get_ApplicationId()
0x4bfc  ldloc.s  5
0x4bfe  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_Value()
0x4c03  ldc.i4.5
0x4c04  call     bool [mscorlib]System.String::Equals(string, string, valuetype [mscorlib]System.StringComparison)
0x4c09  brtrue.s loc_4C4B
0x4c0b  ldc.i4   0x6477D2
0x4c10  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x4c15  ldc.i4.s 0x14
0x4c17  ldstr    aSpapplicationa_61// "SPApplicationAuthenticationModule: acce"...
0x4c1c  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x4c21  ldstr    aInvalidRequest// "invalid_request"
0x4c26  ldc.i4   0x2DC6C1
0x4c2b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x4c30  ldstr    aAuthenticatedw// "AuthenticatedWopiAppOrUserMismatch"
0x4c35  ldc.i4.0
0x4c36  newarr   [mscorlib]System.Object
0x4c3b  call     string [Microsoft.SharePoint]Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo, string, object[])
0x4c40  ldc.i4   0x191
0x4c45  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPOAuthException::.ctor(string, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPOAuthErrorCode, string, int32)
0x4c4a  throw
0x4c4b  ldarg.0
0x4c4c  ldarg.2
0x4c4d  ldloc.s  4
0x4c4f  call     instance bool Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::DoesTokenContainAuthenticatedWopiRequiredScopes(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken authToken, class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WopiTokenContext wopiTokenContext)
0x4c54  brtrue.s loc_4C80
0x4c56  ldstr    aInvalidScope// "invalid_scope"
0x4c5b  ldc.i4   0x2DC6C1
0x4c60  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentUICulture()
0x4c65  ldstr    aAuthenticatedw_0// "AuthenticatedWopiMissingRequiredScope"
0x4c6a  ldc.i4.0
0x4c6b  newarr   [mscorlib]System.Object
0x4c70  call     string [Microsoft.SharePoint]Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo, string, object[])
0x4c75  ldc.i4   0x191
0x4c7a  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPOAuthException::.ctor(string, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPOAuthErrorCode, string, int32)
0x4c7f  throw
0x4c80  ldloc.3
0x4c81  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_Value()
0x4c86  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPIncomingApplicationContext::.ctor(string)
0x4c8b  call     T0x2B00000B
0x4c90  ret
```
