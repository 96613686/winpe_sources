# Microsoft.SharePoint.IdentityModel.SPFederationAuthenticationModule::SetPrincipalAndWriteSessionTokenWithOptions

- ea: `0xbc40`
- end: `0xbe25`
- name: `Microsoft.SharePoint.IdentityModel.SPFederationAuthenticationModule::SetPrincipalAndWriteSessionTokenWithOptions`
- size: `485`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0xbc00`
- `0xbc10`

## callees

- `0xba40`
- `0xbc40`

## string_xrefs

- `0xbc75`: `securityToken`
- `0xbd75`: `SPFederationAuthenticationModule: Transforming generic xml token to token object.`
- `0xbc5c`: `SPFederationAuthenticationModule.SetPrincipalAndWriteSessionToken: The securityToken is null. Stack: '{0}'.`
- `0xbcbc`: `SPFederationAuthenticationModule.SetPrincipalAndWriteSessionToken: The sessionTokenHandler is null. Stack: '{0}'.`
- `0xbcd5`: `SecurityTokenHandlerMissing`
- `0xbd3a`: `SecurityTokenHandlerMissing`
- `0xbce5`: `SessionSecurityToken`
- `0xbd4a`: `SessionSecurityToken`
- `0xbd20`: `SPFederationAuthenticationModule.SetPrincipalAndWriteSessionToken: The SAM is null. Stack: '{0}'.`
- `0xbdbe`: `SPFederationAuthenticationModule: Building session security token.`

## pseudocode

```c

```

## disassembly

```asm
0xbc40  ldarg.1
0xbc41  brtrue.s loc_BC80
0xbc43  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xbc48  ldc.i4.s 0xA
0xbc4a  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::StackTraceString(class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel)
0xbc4f  stloc.0
0xbc50  ldc.i4   0x20F81C
0xbc55  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xbc5a  ldc.i4.s 0xA
0xbc5c  ldstr    aSpfederationau_12// "SPFederationAuthenticationModule.SetPri"...
0xbc61  ldc.i4.1
0xbc62  newarr   [mscorlib]System.Object
0xbc67  stloc.s  0xA
0xbc69  ldloc.s  0xA
0xbc6b  ldc.i4.0
0xbc6c  ldloc.0
0xbc6d  stelem.ref
0xbc6e  ldloc.s  0xA
0xbc70  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xbc75  ldstr    aSecuritytoken// "securityToken"
0xbc7a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xbc7f  throw
0xbc80  ldarg.0
0xbc81  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Configuration.ServiceConfiguration [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.HttpModuleBase::get_ServiceConfiguration()
0xbc86  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenHandlerCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Configuration.ServiceConfiguration::get_SecurityTokenHandlers()
0xbc8b  ldtoken  [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken
0xbc90  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0xbc95  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenHandler [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenHandlerCollection::get_Item(class [mscorlib]System.Type)
0xbc9a  isinst   [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityTokenHandler
0xbc9f  stloc.1
0xbca0  ldloc.1
0xbca1  brtrue.s loc_BCF8
0xbca3  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xbca8  ldc.i4.s 0xA
0xbcaa  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::StackTraceString(class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel)
0xbcaf  stloc.2
0xbcb0  ldc.i4   0x20F81D
0xbcb5  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xbcba  ldc.i4.s 0xA
0xbcbc  ldstr    aSpfederationau_13// "SPFederationAuthenticationModule.SetPri"...
0xbcc1  ldc.i4.1
0xbcc2  newarr   [mscorlib]System.Object
0xbcc7  stloc.s  0xB
0xbcc9  ldloc.s  0xB
0xbccb  ldc.i4.0
0xbccc  ldloc.2
0xbccd  stelem.ref
0xbcce  ldloc.s  0xB
0xbcd0  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xbcd5  ldstr    aSecuritytokenh// "SecurityTokenHandlerMissing"
0xbcda  ldc.i4.1
0xbcdb  newarr   [mscorlib]System.Object
0xbce0  stloc.s  0xC
0xbce2  ldloc.s  0xC
0xbce4  ldc.i4.0
0xbce5  ldstr    aSessionsecurit// "SessionSecurityToken"
0xbcea  stelem.ref
0xbceb  ldloc.s  0xC
0xbced  call     string [Microsoft.SharePoint]Microsoft.SharePoint.SPResource::GetString(string, object[])
0xbcf2  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenException::.ctor(string)
0xbcf7  throw
0xbcf8  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.SessionAuthenticationModule [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.FederatedAuthentication::get_SessionAuthenticationModule()
0xbcfd  isinst   Microsoft.SharePoint.IdentityModel.SPSessionAuthenticationModule
0xbd02  stloc.3
0xbd03  ldloc.3
0xbd04  brtrue.s loc_BD5D
0xbd06  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xbd0b  ldc.i4.s 0xA
0xbd0d  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::StackTraceString(class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel)
0xbd12  stloc.s  4
0xbd14  ldc.i4   0x20F81E
0xbd19  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xbd1e  ldc.i4.s 0xA
0xbd20  ldstr    aSpfederationau_14// "SPFederationAuthenticationModule.SetPri"...
0xbd25  ldc.i4.1
0xbd26  newarr   [mscorlib]System.Object
0xbd2b  stloc.s  0xD
0xbd2d  ldloc.s  0xD
0xbd2f  ldc.i4.0
0xbd30  ldloc.s  4
0xbd32  stelem.ref
0xbd33  ldloc.s  0xD
0xbd35  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xbd3a  ldstr    aSecuritytokenh// "SecurityTokenHandlerMissing"
0xbd3f  ldc.i4.1
0xbd40  newarr   [mscorlib]System.Object
0xbd45  stloc.s  0xE
0xbd47  ldloc.s  0xE
0xbd49  ldc.i4.0
0xbd4a  ldstr    aSessionsecurit// "SessionSecurityToken"
0xbd4f  stelem.ref
0xbd50  ldloc.s  0xE
0xbd52  call     string [Microsoft.SharePoint]Microsoft.SharePoint.SPResource::GetString(string, object[])
0xbd57  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenException::.ctor(string)
0xbd5c  throw
0xbd5d  ldarg.1
0xbd5e  isinst   [System.IdentityModel]System.IdentityModel.Tokens.GenericXmlSecurityToken
0xbd63  stloc.s  5
0xbd65  ldloc.s  5
0xbd67  brfalse.s loc_BD88
0xbd69  ldc.i4   0x1485042
0xbd6e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xbd73  ldc.i4.s 0x64
0xbd75  ldstr    aSpfederationau_9// "SPFederationAuthenticationModule: Trans"...
0xbd7a  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xbd7f  ldloc.s  5
0xbd81  call     class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken [Microsoft.SharePoint]Microsoft.SharePoint.SPSecurityContext::GetSecurityToken(class [System.IdentityModel]System.IdentityModel.Tokens.GenericXmlSecurityToken)
0xbd86  starg.s  1
0xbd88  ldc.i4.3
0xbd89  ldarg.2
0xbd8a  ceq
0xbd8c  stloc.s  6
0xbd8e  ldc.i4.1
0xbd8f  ldarg.2
0xbd90  bne.un.s loc_BDA3
0xbd92  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_Local()
0xbd97  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_UseSessionCookies()
0xbd9c  ldc.i4.0
0xbd9d  ceq
0xbd9f  stloc.s  6
0xbda1  br.s     loc_BDAA
0xbda3  ldc.i4.2
0xbda4  ldarg.2
0xbda5  bne.un.s loc_BDAA
0xbda7  ldc.i4.0
0xbda8  stloc.s  6
0xbdaa  ldarg.1
0xbdab  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal Microsoft.SharePoint.IdentityModel.SPFederationAuthenticationModule::AuthenticateUser(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken securityToken)
0xbdb0  stloc.s  7
0xbdb2  ldc.i4   0x1485043
0xbdb7  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xbdbc  ldc.i4.s 0x64
0xbdbe  ldstr    aSpfederationau_15// "SPFederationAuthenticationModule: Build"...
0xbdc3  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xbdc8  ldloc.s  7
0xbdca  ldnull
0xbdcb  ldarg.1
0xbdcc  callvirt instance valuetype [mscorlib]System.DateTime [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_ValidFrom()
0xbdd1  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0xbdd6  ldarg.1
0xbdd7  callvirt instance valuetype [mscorlib]System.DateTime [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_ValidTo()
0xbddc  newobj   instance void valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>::.ctor(var<u1>)
0xbde1  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken::.ctor(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal, string, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>, valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>)
0xbde6  stloc.s  8
0xbde8  ldloc.s  8
0xbdea  ldloc.s  6
0xbdec  callvirt instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken::set_IsPersistent(bool)
0xbdf1  ldloc.s  8
0xbdf3  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.SessionSecurityTokenCreatedEventArgs::.ctor(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken)
0xbdf8  stloc.s  9
0xbdfa  ldloc.s  9
0xbdfc  ldc.i4.0
0xbdfd  ldarg.2
0xbdfe  ceq
0xbe00  ldc.i4.0
0xbe01  ceq
0xbe03  callvirt instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.SessionSecurityTokenCreatedEventArgs::set_WriteSessionCookie(bool)
0xbe08  ldarg.0
0xbe09  ldloc.s  9
0xbe0b  callvirt instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.WSFederationAuthenticationModule::OnSessionSecurityTokenCreated(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.SessionSecurityTokenCreatedEventArgs)
0xbe10  ldloc.3
0xbe11  ldloc.s  9
0xbe13  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.SessionSecurityTokenCreatedEventArgs::get_SessionToken()
0xbe18  ldloc.s  9
0xbe1a  callvirt instance bool [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.SessionSecurityTokenCreatedEventArgs::get_WriteSessionCookie()
0xbe1f  callvirt instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.SessionAuthenticationModule::AuthenticateSessionSecurityToken(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken, bool)
0xbe24  ret
```
