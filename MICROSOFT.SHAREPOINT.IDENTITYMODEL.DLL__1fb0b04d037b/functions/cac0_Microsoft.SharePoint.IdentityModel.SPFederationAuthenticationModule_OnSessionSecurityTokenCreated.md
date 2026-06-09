# Microsoft.SharePoint.IdentityModel.SPFederationAuthenticationModule::OnSessionSecurityTokenCreated

- ea: `0xcac0`
- end: `0xcc2a`
- name: `Microsoft.SharePoint.IdentityModel.SPFederationAuthenticationModule::OnSessionSecurityTokenCreated`
- size: `362`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0xb690`
- `0xb740`
- `0xcac0`

## string_xrefs

- `0xcacf`: `SPFederationAuthenticationModule.OnSessionSecurityTokenCreated: Start`
- `0xcaf5`: `SPFederationAuthenticationModule.OnSessionSecurityTokenCreated: The eventArgs is null. Stack: '{0}'.`
- `0xcb16`: `SPFederationAuthenticationModule.OnSessionSecurityTokenCreated`
- `0xcb93`: `SPFederationAuthenticationModule.OnSessionSecurityTokenCreated: The eventArgs is invalid. Stack: '{0}'.`
- `0xcbd0`: `SPFederationAuthenticationModule.OnSessionSecurityTokenCreated: Session security token is locally issued.`
- `0xcbeb`: `SPFederationAuthenticationModule.OnSessionSecurityTokenCreated: Session security token is not locally issued so getting local version.`
- `0xcc1f`: `SPFederationAuthenticationModule.OnSessionSecurityTokenCreated: End`

## pseudocode

```c

```

## disassembly

```asm
0xcac0  ldc.i4   0x20F84F
0xcac5  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xcaca  ldc.i4   0xC8
0xcacf  ldstr    aSpfederationau_66// "SPFederationAuthenticationModule.OnSess"...
0xcad4  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xcad9  ldarg.1
0xcada  brtrue.s loc_CB16
0xcadc  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xcae1  ldc.i4.s 0xA
0xcae3  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::StackTraceString(class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel)
0xcae8  stloc.0
0xcae9  ldc.i4   0x20F850
0xcaee  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xcaf3  ldc.i4.s 0xA
0xcaf5  ldstr    aSpfederationau_67// "SPFederationAuthenticationModule.OnSess"...
0xcafa  ldc.i4.1
0xcafb  newarr   [mscorlib]System.Object
0xcb00  stloc.3
0xcb01  ldloc.3
0xcb02  ldc.i4.0
0xcb03  ldloc.0
0xcb04  stelem.ref
0xcb05  ldloc.3
0xcb06  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xcb0b  ldstr    aEventargs// "eventArgs"
0xcb10  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xcb15  throw
0xcb16  ldstr    aSpfederationau_68// "SPFederationAuthenticationModule.OnSess"...
0xcb1b  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string)
0xcb20  stloc.s  4
0xcb22  ldarg.1
0xcb23  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.SessionSecurityTokenCreatedEventArgs::get_SessionToken()
0xcb28  brfalse.s loc_CB7A
0xcb2a  ldarg.1
0xcb2b  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.SessionSecurityTokenCreatedEventArgs::get_SessionToken()
0xcb30  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken::get_ClaimsPrincipal()
0xcb35  brfalse.s loc_CB7A
0xcb37  ldarg.1
0xcb38  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.SessionSecurityTokenCreatedEventArgs::get_SessionToken()
0xcb3d  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken::get_ClaimsPrincipal()
0xcb42  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal::get_Identities()
0xcb47  brfalse.s loc_CB7A
0xcb49  ldc.i4.1
0xcb4a  ldarg.1
0xcb4b  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.SessionSecurityTokenCreatedEventArgs::get_SessionToken()
0xcb50  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken::get_ClaimsPrincipal()
0xcb55  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal::get_Identities()
0xcb5a  callvirt instance int32 [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Count()
0xcb5f  bne.un.s loc_CB7A
0xcb61  ldarg.1
0xcb62  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.SessionSecurityTokenCreatedEventArgs::get_SessionToken()
0xcb67  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken::get_ClaimsPrincipal()
0xcb6c  callvirt instance class [mscorlib]System.Security.Principal.IIdentity [mscorlib]System.Security.Principal.IPrincipal::get_Identity()
0xcb71  isinst   [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity
0xcb76  dup
0xcb77  stloc.1
0xcb78  brtrue.s loc_CBB8
0xcb7a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xcb7f  ldc.i4.s 0xA
0xcb81  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::StackTraceString(class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel)
0xcb86  stloc.2
0xcb87  ldc.i4   0x20F851
0xcb8c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xcb91  ldc.i4.s 0xA
0xcb93  ldstr    aSpfederationau_69// "SPFederationAuthenticationModule.OnSess"...
0xcb98  ldc.i4.1
0xcb99  newarr   [mscorlib]System.Object
0xcb9e  stloc.s  5
0xcba0  ldloc.s  5
0xcba2  ldc.i4.0
0xcba3  ldloc.2
0xcba4  stelem.ref
0xcba5  ldloc.s  5
0xcba7  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xcbac  ldnull
0xcbad  ldstr    aEventargs// "eventArgs"
0xcbb2  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0xcbb7  throw
0xcbb8  ldarg.0
0xcbb9  ldloc.1
0xcbba  call     instance bool Microsoft.SharePoint.IdentityModel.SPFederationAuthenticationModule::IsIdentityLocallyIssued(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity identity)
0xcbbf  brfalse.s loc_CBDC
0xcbc1  ldc.i4   0x20F852
0xcbc6  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xcbcb  ldc.i4   0xC8
0xcbd0  ldstr    aSpfederationau_70// "SPFederationAuthenticationModule.OnSess"...
0xcbd5  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xcbda  br.s     loc_CC02
0xcbdc  ldc.i4   0x20F853
0xcbe1  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xcbe6  ldc.i4   0xC8
0xcbeb  ldstr    aSpfederationau_71// "SPFederationAuthenticationModule.OnSess"...
0xcbf0  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xcbf5  ldarg.0
0xcbf6  ldloc.1
0xcbf7  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_BootstrapToken()
0xcbfc  ldarg.1
0xcbfd  call     instance void Microsoft.SharePoint.IdentityModel.SPFederationAuthenticationModule::ExchangeArgumentTrustedThirdPartySessionSecurityTokenForLocalToken(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken thirdPartyToken, class [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.SessionSecurityTokenCreatedEventArgs arguments)
0xcc02  leave.s  loc_CC10
0xcc04  ldloc.s  4
0xcc06  brfalse.s loc_CC0F
0xcc08  ldloc.s  4
0xcc0a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xcc0f  endfinally
0xcc10  ldc.i4   0x20F854
0xcc15  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xcc1a  ldc.i4   0xC8
0xcc1f  ldstr    aSpfederationau_72// "SPFederationAuthenticationModule.OnSess"...
0xcc24  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xcc29  ret
```
