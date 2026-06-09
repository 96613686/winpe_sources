# Microsoft.SharePoint.IdentityModel.SPFederationAuthenticationModule::GetPrincipalFromToken

- ea: `0xbac0`
- end: `0xbbff`
- name: `Microsoft.SharePoint.IdentityModel.SPFederationAuthenticationModule::GetPrincipalFromToken`
- size: `319`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0xba40`
- `0x241d0`

## callees

- `0xbac0`

## string_xrefs

- `0xbaf5`: `securityToken`
- `0xbadc`: `SPFederationAuthenticationModule: The securityToken is null. Stack: '{0}'.`
- `0xbb2e`: `SPFederationAuthenticationModule: The securityToken is not a bearer token. Stack: '{0}'.`
- `0xbb47`: `Bearer token required.`
- `0xbb5e`: `SPFederationAuthenticationModule: Getting principal from token.`
- `0xbb80`: `SPFederationAuthenticationModule: Transforming generic xml token to token object.`
- `0xbbaf`: `SPFederationAuthenticationModule: Could not get securityToken as GenericXmlSecurityToken. Stack: '{0}'.`
- `0xbbdc`: `SPFederationAuthenticationModule: Validating token.`

## pseudocode

```c

```

## disassembly

```asm
0xbac0  ldarg.0
0xbac1  brtrue.s loc_BB00
0xbac3  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xbac8  ldc.i4.s 0xA
0xbaca  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::StackTraceString(class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel)
0xbacf  stloc.0
0xbad0  ldc.i4   0x20F81A
0xbad5  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xbada  ldc.i4.s 0xA
0xbadc  ldstr    aSpfederationau_6// "SPFederationAuthenticationModule: The s"...
0xbae1  ldc.i4.1
0xbae2  newarr   [mscorlib]System.Object
0xbae7  stloc.s  7
0xbae9  ldloc.s  7
0xbaeb  ldc.i4.0
0xbaec  ldloc.0
0xbaed  stelem.ref
0xbaee  ldloc.s  7
0xbaf0  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xbaf5  ldstr    aSecuritytoken// "securityToken"
0xbafa  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xbaff  throw
0xbb00  ldarg.0
0xbb01  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.IdentityModel]System.IdentityModel.Tokens.SecurityKey> [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_SecurityKeys()
0xbb06  brfalse.s loc_BB52
0xbb08  ldarg.0
0xbb09  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.IdentityModel]System.IdentityModel.Tokens.SecurityKey> [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_SecurityKeys()
0xbb0e  callvirt instance int32 class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [System.IdentityModel]System.IdentityModel.Tokens.SecurityKey>::get_Count()
0xbb13  brfalse.s loc_BB52
0xbb15  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xbb1a  ldc.i4.s 0xA
0xbb1c  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::StackTraceString(class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel)
0xbb21  stloc.1
0xbb22  ldc.i4   0x20F81B
0xbb27  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xbb2c  ldc.i4.s 0xA
0xbb2e  ldstr    aSpfederationau_7// "SPFederationAuthenticationModule: The s"...
0xbb33  ldc.i4.1
0xbb34  newarr   [mscorlib]System.Object
0xbb39  stloc.s  8
0xbb3b  ldloc.s  8
0xbb3d  ldc.i4.0
0xbb3e  ldloc.1
0xbb3f  stelem.ref
0xbb40  ldloc.s  8
0xbb42  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xbb47  ldstr    aBearerTokenReq// "Bearer token required."
0xbb4c  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenException::.ctor(string)
0xbb51  throw
0xbb52  ldc.i4   0x1485023
0xbb57  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xbb5c  ldc.i4.s 0x64
0xbb5e  ldstr    aSpfederationau_8// "SPFederationAuthenticationModule: Getti"...
0xbb63  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xbb68  ldnull
0xbb69  stloc.2
0xbb6a  ldarg.0
0xbb6b  isinst   [System.IdentityModel]System.IdentityModel.Tokens.GenericXmlSecurityToken
0xbb70  stloc.3
0xbb71  ldloc.3
0xbb72  brfalse.s loc_BB92
0xbb74  ldc.i4   0x1485040
0xbb79  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xbb7e  ldc.i4.s 0x64
0xbb80  ldstr    aSpfederationau_9// "SPFederationAuthenticationModule: Trans"...
0xbb85  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xbb8a  ldloc.3
0xbb8b  call     class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken [Microsoft.SharePoint]Microsoft.SharePoint.SPSecurityContext::GetSecurityToken(class [System.IdentityModel]System.IdentityModel.Tokens.GenericXmlSecurityToken)
0xbb90  starg.s  0
0xbb92  ldarg.0
0xbb93  brtrue.s loc_BBC9
0xbb95  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xbb9a  ldc.i4.s 0xA
0xbb9c  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::StackTraceString(class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel)
0xbba1  stloc.s  4
0xbba3  ldc.i4   0x5E3408
0xbba8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xbbad  ldc.i4.s 0xA
0xbbaf  ldstr    aSpfederationau_10// "SPFederationAuthenticationModule: Could"...
0xbbb4  ldc.i4.1
0xbbb5  newarr   [mscorlib]System.Object
0xbbba  stloc.s  9
0xbbbc  ldloc.s  9
0xbbbe  ldc.i4.0
0xbbbf  ldloc.s  4
0xbbc1  stelem.ref
0xbbc2  ldloc.s  9
0xbbc4  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xbbc9  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Configuration.ServiceConfiguration [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.FederatedAuthentication::get_ServiceConfiguration()
0xbbce  stloc.s  5
0xbbd0  ldc.i4   0x1485041
0xbbd5  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xbbda  ldc.i4.s 0x64
0xbbdc  ldstr    aSpfederationau_11// "SPFederationAuthenticationModule: Valid"...
0xbbe1  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xbbe6  ldloc.s  5
0xbbe8  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenHandlerCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Configuration.ServiceConfiguration::get_SecurityTokenHandlers()
0xbbed  ldarg.0
0xbbee  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenHandlerCollection::ValidateToken(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken)
0xbbf3  stloc.s  6
0xbbf5  ldloc.s  6
0xbbf7  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsPrincipal::.ctor(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection)
0xbbfc  stloc.2
0xbbfd  ldloc.2
0xbbfe  ret
```
