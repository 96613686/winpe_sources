# Microsoft.SharePoint.IdentityModel.SPSessionAuthenticationModule::OnSessionSecurityTokenReceived

- ea: `0x20170`
- end: `0x2034f`
- name: `Microsoft.SharePoint.IdentityModel.SPSessionAuthenticationModule::OnSessionSecurityTokenReceived`
- size: `479`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1be40`
- `0x20170`
- `0x283a0`

## string_xrefs

- `0x2018c`: `SPFam.OnSessionSecurityTokenReceived: The eventArgs is null. Stack: '{0}'.`
- `0x201bc`: `SPSam.OnSessionSecurityTokenReceived: Start`
- `0x201ec`: `SPSam.OnSessionSecurityTokenReceived: Token is anonymous session security token. Cancelling event.`
- `0x2026c`: `SPSam.OnSessionSecurityTokenReceived: Session token is invalid.`
- `0x20299`: `SPSam.OnSessionSecurityTokenReceived: Audience token conditions have failed. Cancelling event.`
- `0x202cc`: `Audience validation failed and WindowsModeIgnoreCache is set to true.  Marking cache entry as invalid.`
- `0x20303`: `AUTH_FORCE_WINDOWS_MODE_NOCACHE`
- `0x20314`: `SPSam.OnSessionSecurityTokenReceived::WifCodeCall`
- `0x20344`: `SPSam.OnSessionSecurityTokenReceived: End`

## pseudocode

```c

```

## disassembly

```asm
0x20170  ldarg.1
0x20171  brtrue.s loc_201AD
0x20173  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x20178  ldc.i4.s 0xA
0x2017a  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::StackTraceString(class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel)
0x2017f  stloc.0
0x20180  ldc.i4   0x20F85B
0x20185  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x2018a  ldc.i4.s 0xA
0x2018c  ldstr    aSpfamOnsession// "SPFam.OnSessionSecurityTokenReceived: T"...
0x20191  ldc.i4.1
0x20192  newarr   [mscorlib]System.Object
0x20197  stloc.3
0x20198  ldloc.3
0x20199  ldc.i4.0
0x2019a  ldloc.0
0x2019b  stelem.ref
0x2019c  ldloc.3
0x2019d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x201a2  ldstr    aEventargs// "eventArgs"
0x201a7  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x201ac  throw
0x201ad  ldc.i4   0x20F85C
0x201b2  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x201b7  ldc.i4   0xC8
0x201bc  ldstr    aSpsamOnsession_2// "SPSam.OnSessionSecurityTokenReceived: S"...
0x201c1  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x201c6  ldnull
0x201c7  stloc.1
0x201c8  ldarg.1
0x201c9  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.SessionSecurityTokenReceivedEventArgs::get_SessionToken()
0x201ce  brfalse.s loc_20202
0x201d0  ldarg.1
0x201d1  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.SessionSecurityTokenReceivedEventArgs::get_SessionToken()
0x201d6  isinst   Microsoft.SharePoint.IdentityModel.SPDummySessionSecurityToken
0x201db  brfalse.s loc_20202
0x201dd  ldc.i4   0x20F85D
0x201e2  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x201e7  ldc.i4   0xC8
0x201ec  ldstr    aSpsamOnsession_3// "SPSam.OnSessionSecurityTokenReceived: T"...
0x201f1  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x201f6  ldarg.1
0x201f7  ldc.i4.1
0x201f8  callvirt instance void [System]System.ComponentModel.CancelEventArgs::set_Cancel(bool)
0x201fd  br       loc_20335
0x20202  ldarg.1
0x20203  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.SessionSecurityTokenReceivedEventArgs::get_SessionToken()
0x20208  brfalse.s loc_20260
0x2020a  ldarg.1
0x2020b  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.SessionSecurityTokenReceivedEventArgs::get_SessionToken()
0x20210  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken::get_ClaimsPrincipal()
0x20215  brfalse.s loc_20260
0x20217  ldarg.1
0x20218  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.SessionSecurityTokenReceivedEventArgs::get_SessionToken()
0x2021d  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken::get_ClaimsPrincipal()
0x20222  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal::get_Identities()
0x20227  brfalse.s loc_20260
0x20229  ldc.i4.1
0x2022a  ldarg.1
0x2022b  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.SessionSecurityTokenReceivedEventArgs::get_SessionToken()
0x20230  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken::get_ClaimsPrincipal()
0x20235  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal::get_Identities()
0x2023a  callvirt instance int32 [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Count()
0x2023f  bne.un.s loc_20260
0x20241  ldarg.1
0x20242  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.SessionSecurityTokenReceivedEventArgs::get_SessionToken()
0x20247  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken::get_ClaimsPrincipal()
0x2024c  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal::get_Identities()
0x20251  ldc.i4.0
0x20252  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Item(int32)
0x20257  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_BootstrapToken()
0x2025c  dup
0x2025d  stloc.1
0x2025e  brtrue.s loc_20282
0x20260  ldc.i4   0x20F85E
0x20265  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x2026a  ldc.i4.s 0xA
0x2026c  ldstr    aSpsamOnsession_4// "SPSam.OnSessionSecurityTokenReceived: S"...
0x20271  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x20276  ldnull
0x20277  ldstr    aEventargs// "eventArgs"
0x2027c  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x20281  throw
0x20282  ldloc.1
0x20283  call     bool Microsoft.SharePoint.IdentityModel.SPSaml11SecurityTokenHandler::ValidateTokenAudienceConditions(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken token)
0x20288  brtrue   loc_20314
0x2028d  ldc.i4   0x20F85F
0x20292  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x20297  ldc.i4.s 0xA
0x20299  ldstr    aSpsamOnsession_5// "SPSam.OnSessionSecurityTokenReceived: A"...
0x2029e  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x202a3  ldarg.1
0x202a4  ldc.i4.1
0x202a5  callvirt instance void [System]System.ComponentModel.CancelEventArgs::set_Cancel(bool)
0x202aa  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_Local()
0x202af  stloc.2
0x202b0  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPAlternateUrl::get_ContextUri()
0x202b5  call     bool Microsoft.SharePoint.IdentityModel.SPClaimsUtility::IsClaimsWindowsAuthenticationOnly(class [System]System.Uri context)
0x202ba  brfalse.s loc_20335
0x202bc  ldloc.2
0x202bd  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_WindowsModeIgnoreCache()
0x202c2  brfalse.s loc_20335
0x202c4  ldc.i4.0
0x202c5  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x202ca  ldc.i4.s 0x32
0x202cc  ldstr    aAudienceValida_8// "Audience validation failed and WindowsM"...
0x202d1  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x202d6  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x202db  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x202e0  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_ServerVariables()
0x202e5  ldstr    aAuthForceWindo// "AUTH_FORCE_WINDOWS_MODE"
0x202ea  ldstr    aTrue_0// "TRUE"
0x202ef  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x202f4  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x202f9  callvirt instance class [System.Web]System.Web.HttpRequest [System.Web]System.Web.HttpContext::get_Request()
0x202fe  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpRequest::get_ServerVariables()
0x20303  ldstr    aAuthForceWindo_0// "AUTH_FORCE_WINDOWS_MODE_NOCACHE"
0x20308  ldstr    aTrue_0// "TRUE"
0x2030d  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::set_Item(string, string)
0x20312  br.s     loc_20335
0x20314  ldstr    aSpsamOnsession_6// "SPSam.OnSessionSecurityTokenReceived::W"...
0x20319  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string)
0x2031e  stloc.s  4
0x20320  ldarg.0
0x20321  ldarg.1
0x20322  call     instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.SessionAuthenticationModule::OnSessionSecurityTokenReceived(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.SessionSecurityTokenReceivedEventArgs)
0x20327  leave.s  loc_20335
0x20329  ldloc.s  4
0x2032b  brfalse.s loc_20334
0x2032d  ldloc.s  4
0x2032f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20334  endfinally
0x20335  ldc.i4   0x20F860
0x2033a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x2033f  ldc.i4   0xC8
0x20344  ldstr    aSpsamOnsession_7// "SPSam.OnSessionSecurityTokenReceived: E"...
0x20349  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x2034e  ret
```
