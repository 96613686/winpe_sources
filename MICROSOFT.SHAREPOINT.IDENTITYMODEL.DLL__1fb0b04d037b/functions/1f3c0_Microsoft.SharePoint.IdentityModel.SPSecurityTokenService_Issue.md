# Microsoft.SharePoint.IdentityModel.SPSecurityTokenService::Issue

- ea: `0x1f3c0`
- end: `0x1f4cd`
- name: `Microsoft.SharePoint.IdentityModel.SPSecurityTokenService::Issue`
- size: `269`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x19400`
- `0x1c260`
- `0x1c300`
- `0x1c4a0`
- `0x1f3c0`
- `0x1f4d0`

## string_xrefs

- `0x1f44b`: `http://schemas.microsoft.com/sharepoint/2014/06/signin/failure`
- `0x1f3f4`: `http://schemas.microsoft.com/idfx/requesttype/issue`
- `0x1f3c0`: `SPSecurityTokenService.Issue`
- `0x1f3d8`: `STS Call: Issuing new security token.`
- `0x1f411`: `Creating SPSecurityTokenRequestContext object for security token service Issue request.`
- `0x1f43d`: `STS Call: Successfully issued new security token.`
- `0x1f463`: `STS Call: Failed to issue new security token with sign-in exception. Exception: '{0}'.`
- `0x1f48f`: `STS Call: Failed to issue new security token. Exception: '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0x1f3c0  ldstr    aSpsecuritytoke_7// "SPSecurityTokenService.Issue"
0x1f3c5  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string)
0x1f3ca  stloc.s  4
0x1f3cc  ldc.i4   0x66327575
0x1f3d1  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1f3d6  ldc.i4.s 0x64
0x1f3d8  ldstr    aStsCallIssuing// "STS Call: Issuing new security token."
0x1f3dd  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1f3e2  ldnull
0x1f3e3  stloc.0
0x1f3e4  ldarg.0
0x1f3e5  ldarg.2
0x1f3e6  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.SPClaimsOperationContextScope Microsoft.SharePoint.IdentityModel.SPSecurityTokenService::CreateClaimOperationContextScopeOrDefault(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.RequestSecurityToken request)
0x1f3eb  stloc.1
0x1f3ec  ldarg.0
0x1f3ed  ldarga.s 1
0x1f3ef  call     instance void Microsoft.SharePoint.IdentityModel.SPSecurityTokenService::ValidateClaimsPrincipal(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal& principal)
0x1f3f4  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/idfx/reque"...
0x1f3f9  ldarg.2
0x1f3fa  call     void Microsoft.SharePoint.IdentityModel.SPSecurityTokenService::ValidateRequestType(string type, class [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.RequestSecurityToken request)
0x1f3ff  ldarg.1
0x1f400  call     void Microsoft.SharePoint.IdentityModel.SPSecurityTokenService::ValidateRequestArguments(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal principal)
0x1f405  ldc.i4   0x179A4DA
0x1f40a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1f40f  ldc.i4.s 0x32
0x1f411  ldstr    aCreatingSpsecu_6// "Creating SPSecurityTokenRequestContext "...
0x1f416  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1f41b  ldarg.0
0x1f41c  ldarg.1
0x1f41d  ldarg.2
0x1f41e  newobj   instance void Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::.ctor(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal principal, class [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.RequestSecurityToken request)
0x1f423  stfld    class Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext Microsoft.SharePoint.IdentityModel.SPSecurityTokenService::m_RequestInfo
0x1f428  ldarg.0
0x1f429  ldarg.1
0x1f42a  ldarg.2
0x1f42b  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.RequestSecurityTokenResponse [Microsoft.IdentityModel]Microsoft.IdentityModel.SecurityTokenService.SecurityTokenService::Issue(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal, class [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.RequestSecurityToken)
0x1f430  stloc.0
0x1f431  ldc.i4   0x15D650
0x1f436  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1f43b  ldc.i4.s 0x64
0x1f43d  ldstr    aStsCallSuccess_0// "STS Call: Successfully issued new secur"...
0x1f442  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1f447  leave.s  loc_1F4AF
0x1f449  stloc.2
0x1f44a  ldloc.2
0x1f44b  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/sharepoint"...
0x1f450  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceFailureUtilities::IsTokenIssuanceFailureExceptionInNameSpace(class [mscorlib]System.Exception, string)
0x1f455  brfalse.s loc_1F483
0x1f457  ldc.i4   0x80D659
0x1f45c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1f461  ldc.i4.s 0x32
0x1f463  ldstr    aStsCallFailedT// "STS Call: Failed to issue new security "...
0x1f468  ldc.i4.1
0x1f469  newarr   [mscorlib]System.Object
0x1f46e  stloc.s  5
0x1f470  ldloc.s  5
0x1f472  ldc.i4.0
0x1f473  ldloc.2
0x1f474  callvirt instance string [mscorlib]System.Object::ToString()
0x1f479  stelem.ref
0x1f47a  ldloc.s  5
0x1f47c  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1f481  br.s     loc_1F4AD
0x1f483  ldc.i4   0x666F3174
0x1f488  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1f48d  ldc.i4.s 0xF
0x1f48f  ldstr    aStsCallFailedT_0// "STS Call: Failed to issue new security "...
0x1f494  ldc.i4.1
0x1f495  newarr   [mscorlib]System.Object
0x1f49a  stloc.s  6
0x1f49c  ldloc.s  6
0x1f49e  ldc.i4.0
0x1f49f  ldloc.2
0x1f4a0  callvirt instance string [mscorlib]System.Object::ToString()
0x1f4a5  stelem.ref
0x1f4a6  ldloc.s  6
0x1f4a8  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1f4ad  rethrow
0x1f4af  leave.s  loc_1F4BB
0x1f4b1  ldloc.1
0x1f4b2  brfalse.s loc_1F4BA
0x1f4b4  ldloc.1
0x1f4b5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f4ba  endfinally
0x1f4bb  ldloc.0
0x1f4bc  stloc.3
0x1f4bd  leave.s  loc_1F4CB
0x1f4bf  ldloc.s  4
0x1f4c1  brfalse.s loc_1F4CA
0x1f4c3  ldloc.s  4
0x1f4c5  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f4ca  endfinally
0x1f4cb  ldloc.3
0x1f4cc  ret
```
