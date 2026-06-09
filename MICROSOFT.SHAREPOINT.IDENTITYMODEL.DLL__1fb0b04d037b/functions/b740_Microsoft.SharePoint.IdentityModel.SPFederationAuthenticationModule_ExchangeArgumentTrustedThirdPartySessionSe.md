# Microsoft.SharePoint.IdentityModel.SPFederationAuthenticationModule::ExchangeArgumentTrustedThirdPartySessionSecurityTokenForLocalToken

- ea: `0xb740`
- end: `0xba38`
- name: `Microsoft.SharePoint.IdentityModel.SPFederationAuthenticationModule::ExchangeArgumentTrustedThirdPartySessionSecurityTokenForLocalToken`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xcac0`

## callees

- `0xb740`

## string_xrefs

- `0xb75c`: `SPFederationAuthenticationModule: The thirdPartyToken is null. Stack: '{0}'.`
- `0xb775`: `thirdPartyToken`
- `0xb7cc`: `Claims Saml Sign-In: Received trusted third party token. Attempting to get equivalent local token.`
- `0xb822`: `Claims Saml Sign-In: Received saml is invalid. Could not find identity claim. Failed to get local token. Redirecting to error page.`
- `0xb8ec`: `Claims Saml Sign-In: Could not get local token for trusted third party token. FaultException: '{0}'. Stack: '{1}'.`
- `0xb92e`: `Claims Saml Sign-In: Could not get local token for trusted third party token. Exception: '{0}'. Stack: '{1}'.`
- `0xb962`: `Claims Saml Sign-In: Could not get local token from trusted third party token.`
- `0xb984`: `Claims Saml Sign-In: Could not get generic token from token. TokenType: '{0}'.`
- `0xb9bf`: `Claims Saml Sign-In: Could not get token from generic token.`
- `0xb9d6`: `Claims Saml Sign-In: Signing in user from third party trusted token.`

## pseudocode

```c

```

## disassembly

```asm
0xb740  ldarg.1
0xb741  brtrue.s loc_B780
0xb743  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xb748  ldc.i4.s 0xA
0xb74a  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::StackTraceString(class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel)
0xb74f  stloc.0
0xb750  ldc.i4   0x20F817
0xb755  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xb75a  ldc.i4.s 0xA
0xb75c  ldstr    aSpfederationau_1// "SPFederationAuthenticationModule: The t"...
0xb761  ldc.i4.1
0xb762  newarr   [mscorlib]System.Object
0xb767  stloc.s  0xF
0xb769  ldloc.s  0xF
0xb76b  ldc.i4.0
0xb76c  ldloc.0
0xb76d  stelem.ref
0xb76e  ldloc.s  0xF
0xb770  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xb775  ldstr    aThirdpartytoke// "thirdPartyToken"
0xb77a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xb77f  throw
0xb780  ldarg.2
0xb781  brtrue.s loc_B7C0
0xb783  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xb788  ldc.i4.s 0xA
0xb78a  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::StackTraceString(class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel)
0xb78f  stloc.1
0xb790  ldc.i4   0x20F818
0xb795  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xb79a  ldc.i4.s 0xA
0xb79c  ldstr    aSpfederationau_2// "SPFederationAuthenticationModule: The a"...
0xb7a1  ldc.i4.1
0xb7a2  newarr   [mscorlib]System.Object
0xb7a7  stloc.s  0x10
0xb7a9  ldloc.s  0x10
0xb7ab  ldc.i4.0
0xb7ac  ldloc.1
0xb7ad  stelem.ref
0xb7ae  ldloc.s  0x10
0xb7b0  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xb7b5  ldstr    aArguments// "arguments"
0xb7ba  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xb7bf  throw
0xb7c0  ldc.i4   0x15D5D5
0xb7c5  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xb7ca  ldc.i4.s 0x64
0xb7cc  ldstr    aClaimsSamlSign_0// "Claims Saml Sign-In: Received trusted t"...
0xb7d1  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xb7d6  ldnull
0xb7d7  stloc.2
0xb7d8  ldnull
0xb7d9  stloc.3
0xb7da  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimProviderManager::GetWebApplicationUriForHttpContext()
0xb7df  stloc.3
0xb7e0  ldloc.3
0xb7e1  ldarg.1
0xb7e2  call     class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken [Microsoft.SharePoint]Microsoft.SharePoint.SPSecurityContext::SecurityTokenForOnBehalfOfContext(class [System]System.Uri, class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken)
0xb7e7  stloc.2
0xb7e8  leave    loc_B950
0xb7ed  stloc.s  4
0xb7ef  ldloc.s  4
0xb7f1  callvirt instance class [System.ServiceModel]System.ServiceModel.FaultCode [System.ServiceModel]System.ServiceModel.FaultException::get_Code()
0xb7f6  brfalse  loc_B8D0
0xb7fb  ldstr    aTrustedmissing// "TrustedMissingIdentityClaim"
0xb800  ldloc.s  4
0xb802  callvirt instance class [System.ServiceModel]System.ServiceModel.FaultCode [System.ServiceModel]System.ServiceModel.FaultException::get_Code()
0xb807  callvirt instance string [System.ServiceModel]System.ServiceModel.FaultCode::get_Name()
0xb80c  call     bool [mscorlib]System.String::op_Equality(string, string)
0xb811  brfalse  loc_B8D0
0xb816  ldc.i4   0x15D5D6
0xb81b  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xb820  ldc.i4.s 0x64
0xb822  ldstr    aClaimsSamlSign_1// "Claims Saml Sign-In: Received saml is i"...
0xb827  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xb82c  ldarg.0
0xb82d  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0xb832  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0xb837  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.WSFederationAuthenticationModule::GetReturnUrlFromResponse(class [System.Web]System.Web.HttpRequest)
0xb83c  stloc.s  5
0xb83e  ldloc.s  5
0xb840  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xb845  brfalse.s loc_B851
0xb847  ldloc.3
0xb848  callvirt instance string [mscorlib]System.Object::ToString()
0xb84d  stloc.s  5
0xb84f  br.s     loc_B873
0xb851  ldloc.s  5
0xb853  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::IsAbsoluteUrl(string)
0xb858  brtrue.s loc_B873
0xb85a  ldloc.3
0xb85b  ldloc.s  5
0xb85d  ldc.i4.0
0xb85e  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0xb863  newobj   instance void [System]System.Uri::.ctor(class [System]System.Uri, class [System]System.Uri)
0xb868  stloc.s  6
0xb86a  ldloc.s  6
0xb86c  callvirt instance string [mscorlib]System.Object::ToString()
0xb871  stloc.s  5
0xb873  ldstr    aLoginDefaultAs// "/_login/default.aspx?errorCode=TrustedM"...
0xb878  ldloc.s  5
0xb87a  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPHttpUtility::UrlKeyValueEncode(string)
0xb87f  call     string [mscorlib]System.String::Concat(string, string)
0xb884  ldc.i4.2
0xb885  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0xb88a  stloc.s  7
0xb88c  ldc.i4   0x20F819
0xb891  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xb896  ldc.i4.s 0x64
0xb898  ldstr    aClaimsSamlSign_2// "Claims Saml Sign-In: Redirecting to err"...
0xb89d  ldc.i4.1
0xb89e  newarr   [mscorlib]System.Object
0xb8a3  stloc.s  0x11
0xb8a5  ldloc.s  0x11
0xb8a7  ldc.i4.0
0xb8a8  ldloc.s  7
0xb8aa  callvirt instance string [mscorlib]System.Object::ToString()
0xb8af  stelem.ref
0xb8b0  ldloc.s  0x11
0xb8b2  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xb8b7  ldloc.s  7
0xb8b9  callvirt instance string [mscorlib]System.Object::ToString()
0xb8be  ldc.i4   0x85
0xb8c3  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0xb8c8  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::Redirect(string, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPRedirectFlags, class [System.Web]System.Web.HttpContext)
0xb8cd  pop
0xb8ce  br.s     loc_B90E
0xb8d0  ldloc.s  4
0xb8d2  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xb8d7  ldc.i4.s 0xA
0xb8d9  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::ExceptionTraceString(class [mscorlib]System.Exception, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel)
0xb8de  stloc.s  8
0xb8e0  ldc.i4   0x15D5D7
0xb8e5  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xb8ea  ldc.i4.s 0xA
0xb8ec  ldstr    aClaimsSamlSign_3// "Claims Saml Sign-In: Could not get loca"...
0xb8f1  ldc.i4.2
0xb8f2  newarr   [mscorlib]System.Object
0xb8f7  stloc.s  0x12
0xb8f9  ldloc.s  0x12
0xb8fb  ldc.i4.0
0xb8fc  ldloc.s  4
0xb8fe  stelem.ref
0xb8ff  ldloc.s  0x12
0xb901  ldc.i4.1
0xb902  ldloc.s  8
0xb904  stelem.ref
0xb905  ldloc.s  0x12
0xb907  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xb90c  rethrow
0xb90e  leave.s  loc_B950
0xb910  stloc.s  9
0xb912  ldloc.s  9
0xb914  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xb919  ldc.i4.s 0xA
0xb91b  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::ExceptionTraceString(class [mscorlib]System.Exception, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel)
0xb920  stloc.s  0xA
0xb922  ldc.i4   0x15D5D8
0xb927  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xb92c  ldc.i4.s 0xA
0xb92e  ldstr    aClaimsSamlSign_4// "Claims Saml Sign-In: Could not get loca"...
0xb933  ldc.i4.2
0xb934  newarr   [mscorlib]System.Object
0xb939  stloc.s  0x13
0xb93b  ldloc.s  0x13
0xb93d  ldc.i4.0
0xb93e  ldloc.s  9
0xb940  stelem.ref
0xb941  ldloc.s  0x13
0xb943  ldc.i4.1
0xb944  ldloc.s  0xA
0xb946  stelem.ref
0xb947  ldloc.s  0x13
0xb949  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xb94e  rethrow
0xb950  ldnull
0xb951  stloc.s  0xB
0xb953  ldloc.2
0xb954  brtrue.s loc_B96D
0xb956  ldc.i4   0x15D5D9
0xb95b  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xb960  ldc.i4.s 0xA
0xb962  ldstr    aClaimsSamlSign_5// "Claims Saml Sign-In: Could not get loca"...
0xb967  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xb96c  ret
0xb96d  ldloc.2
0xb96e  isinst   [System.IdentityModel]System.IdentityModel.Tokens.GenericXmlSecurityToken
0xb973  dup
0xb974  stloc.s  0xB
0xb976  brtrue.s loc_B9A8
0xb978  ldc.i4   0x15D5DA
0xb97d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xb982  ldc.i4.s 0xA
0xb984  ldstr    aClaimsSamlSign_6// "Claims Saml Sign-In: Could not get gene"...
0xb989  ldc.i4.1
0xb98a  newarr   [mscorlib]System.Object
0xb98f  stloc.s  0x14
0xb991  ldloc.s  0x14
0xb993  ldc.i4.0
0xb994  ldloc.2
0xb995  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0xb99a  callvirt instance string [mscorlib]System.Reflection.MemberInfo::get_Name()
0xb99f  stelem.ref
0xb9a0  ldloc.s  0x14
0xb9a2  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xb9a7  ret
0xb9a8  ldloc.s  0xB
0xb9aa  call     class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken [Microsoft.SharePoint]Microsoft.SharePoint.SPSecurityContext::GetSecurityToken(class [System.IdentityModel]System.IdentityModel.Tokens.GenericXmlSecurityToken)
0xb9af  dup
0xb9b0  stloc.2
0xb9b1  brtrue.s loc_B9CA
0xb9b3  ldc.i4   0x15D5DB
0xb9b8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xb9bd  ldc.i4.s 0xA
0xb9bf  ldstr    aClaimsSamlSign_7// "Claims Saml Sign-In: Could not get toke"...
0xb9c4  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xb9c9  ret
0xb9ca  ldc.i4   0x15D5DC
0xb9cf  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xb9d4  ldc.i4.s 0x64
0xb9d6  ldstr    aClaimsSamlSign_8// "Claims Saml Sign-In: Signing in user fr"...
0xb9db  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xb9e0  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Configuration.ServiceConfiguration [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.FederatedAuthentication::get_ServiceConfiguration()
0xb9e5  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenHandlerCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Configuration.ServiceConfiguration::get_SecurityTokenHandlers()
0xb9ea  ldloc.2
0xb9eb  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenHandlerCollection::ValidateToken(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken)
0xb9f0  stloc.s  0xC
0xb9f2  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_Local()
0xb9f7  stloc.s  0xD
0xb9f9  ldloc.s  0xC
0xb9fb  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsPrincipal::.ctor(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection)
0xba00  ldnull
0xba01  ldloc.2
0xba02  callvirt instance valuetype [mscorlib]System.DateTime [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_ValidFrom()
0xba07  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0xba0c  ldloc.2
0xba0d  callvirt instance valuetype [mscorlib]System.DateTime [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_ValidTo()
0xba12  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0xba17  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken::.ctor(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal, string, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>)
0xba1c  stloc.s  0xE
0xba1e  ldloc.s  0xE
0xba20  ldloc.s  0xD
0xba22  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_UseSessionCookies()
0xba27  ldc.i4.0
0xba28  ceq
0xba2a  callvirt instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken::set_IsPersistent(bool)
0xba2f  ldarg.2
0xba30  ldloc.s  0xE
0xba32  callvirt instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.SessionSecurityTokenCreatedEventArgs::set_SessionToken(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken)
0xba37  ret
```
