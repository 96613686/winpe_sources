# Microsoft.SharePoint.IdentityModel.SPSessionAuthenticationModule::AuthenticateSessionSecurityToken

- ea: `0x20470`
- end: `0x2053b`
- name: `Microsoft.SharePoint.IdentityModel.SPSessionAuthenticationModule::AuthenticateSessionSecurityToken`
- size: `203`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x20470`

## string_xrefs

- `0x2047f`: `SPSam.AuthenticateSessionSecurityToken: Start`
- `0x20489`: `SPSam.AuthenticateSessionSecurityToken::WifCodeCall`
- `0x204be`: `SPSam.AuthenticateSessionSecurityToken: Session Authentication cookie expired.`
- `0x20503`: `SPSam.AuthenticateSessionSecurityToken: Error while handling FederatedSessionExpiredException. Exception: '{0}'. Stack: '{1}'.`
- `0x20530`: `SPSam.AuthenticateSessionSecurityToken: End`

## pseudocode

```c

```

## disassembly

```asm
0x20470  ldc.i4   0x20F883
0x20475  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x2047a  ldc.i4   0xC8
0x2047f  ldstr    aSpsamAuthentic// "SPSam.AuthenticateSessionSecurityToken:"...
0x20484  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x20489  ldstr    aSpsamAuthentic_0// "SPSam.AuthenticateSessionSecurityToken:"...
0x2048e  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string)
0x20493  stloc.2
0x20494  ldarg.0
0x20495  ldarg.1
0x20496  ldarg.2
0x20497  call     instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.SessionAuthenticationModule::AuthenticateSessionSecurityToken(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken, bool)
0x2049c  leave.s  loc_204A8
0x2049e  ldloc.2
0x2049f  brfalse.s loc_204A7
0x204a1  ldloc.2
0x204a2  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x204a7  endfinally
0x204a8  leave.s  loc_20521
0x204aa  pop
0x204ab  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x204b0  brfalse.s loc_2051F
0x204b2  ldc.i4   0x66327577
0x204b7  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x204bc  ldc.i4.s 0x64
0x204be  ldstr    aSpsamAuthentic_1// "SPSam.AuthenticateSessionSecurityToken:"...
0x204c3  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x204c8  call     class [System.Web]System.Web.HttpContext [System.Web]System.Web.HttpContext::get_Current()
0x204cd  callvirt instance class [System.Web]System.Web.HttpResponse [System.Web]System.Web.HttpContext::get_Response()
0x204d2  callvirt instance class [System]System.Collections.Specialized.NameValueCollection [System.Web]System.Web.HttpResponse::get_Headers()
0x204d7  ldstr    aSpsessionauthe// "SPSessionAuthentication"
0x204dc  ldstr    aCookieExpired// "cookie-expired"
0x204e1  callvirt instance void [System]System.Collections.Specialized.NameValueCollection::Add(string, string)
0x204e6  leave.s  loc_2051F
0x204e8  stloc.0
0x204e9  ldloc.0
0x204ea  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x204ef  ldc.i4.s 0x14
0x204f1  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPUtility::ExceptionTraceString(class [mscorlib]System.Exception, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel)
0x204f6  stloc.1
0x204f7  ldc.i4   0x65653134
0x204fc  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x20501  ldc.i4.s 0x14
0x20503  ldstr    aSpsamAuthentic_2// "SPSam.AuthenticateSessionSecurityToken:"...
0x20508  ldc.i4.2
0x20509  newarr   [mscorlib]System.Object
0x2050e  stloc.3
0x2050f  ldloc.3
0x20510  ldc.i4.0
0x20511  ldloc.0
0x20512  stelem.ref
0x20513  ldloc.3
0x20514  ldc.i4.1
0x20515  ldloc.1
0x20516  stelem.ref
0x20517  ldloc.3
0x20518  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x2051d  leave.s  loc_2051F
0x2051f  leave.s  loc_20521
0x20521  ldc.i4   0x20F884
0x20526  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x2052b  ldc.i4   0xC8
0x20530  ldstr    aSpsamAuthentic_3// "SPSam.AuthenticateSessionSecurityToken:"...
0x20535  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x2053a  ret
```
