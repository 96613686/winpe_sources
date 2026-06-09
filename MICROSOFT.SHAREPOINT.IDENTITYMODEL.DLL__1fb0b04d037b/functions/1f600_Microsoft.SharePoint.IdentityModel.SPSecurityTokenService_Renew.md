# Microsoft.SharePoint.IdentityModel.SPSecurityTokenService::Renew

- ea: `0x1f600`
- end: `0x1f6f6`
- name: `Microsoft.SharePoint.IdentityModel.SPSecurityTokenService::Renew`
- size: `246`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callees

- `0x19400`
- `0x1c260`
- `0x1c300`
- `0x1c4a0`
- `0x1f600`

## string_xrefs

- `0x1f682`: `http://schemas.microsoft.com/sharepoint/2014/06/signin/failure`
- `0x1f600`: `SPSecurityTokenService.Renew`
- `0x1f617`: `STS Call: Renewing security token.`
- `0x1f62b`: `http://schemas.microsoft.com/idfx/requesttype/renew`
- `0x1f648`: `Creating SPSecurityTokenRequestContext object for security token service Renew request.`
- `0x1f674`: `STS Call: Successfully renewed security token.`
- `0x1f69a`: `STS Call: Failed to renew security token with sign-in exception. Exception: '{0}'.`
- `0x1f6c6`: `STS Call: Failed to renew security token. Exception: '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0x1f600  ldstr    aSpsecuritytoke_8// "SPSecurityTokenService.Renew"
0x1f605  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string)
0x1f60a  stloc.3
0x1f60b  ldc.i4   0x66327576
0x1f610  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1f615  ldc.i4.s 0x64
0x1f617  ldstr    aStsCallRenewin// "STS Call: Renewing security token."
0x1f61c  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1f621  ldnull
0x1f622  stloc.0
0x1f623  ldarg.0
0x1f624  ldarga.s 1
0x1f626  call     instance void Microsoft.SharePoint.IdentityModel.SPSecurityTokenService::ValidateClaimsPrincipal(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal& principal)
0x1f62b  ldstr    aHttpSchemasMic_1// "http://schemas.microsoft.com/idfx/reque"...
0x1f630  ldarg.2
0x1f631  call     void Microsoft.SharePoint.IdentityModel.SPSecurityTokenService::ValidateRequestType(string type, class [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.RequestSecurityToken request)
0x1f636  ldarg.1
0x1f637  call     void Microsoft.SharePoint.IdentityModel.SPSecurityTokenService::ValidateRequestArguments(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal principal)
0x1f63c  ldc.i4   0x179A4DB
0x1f641  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1f646  ldc.i4.s 0x32
0x1f648  ldstr    aCreatingSpsecu_7// "Creating SPSecurityTokenRequestContext "...
0x1f64d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1f652  ldarg.0
0x1f653  ldarg.1
0x1f654  ldarg.2
0x1f655  newobj   instance void Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext::.ctor(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal principal, class [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.RequestSecurityToken request)
0x1f65a  stfld    class Microsoft.SharePoint.IdentityModel.SPSecurityTokenRequestContext Microsoft.SharePoint.IdentityModel.SPSecurityTokenService::m_RequestInfo
0x1f65f  ldarg.0
0x1f660  ldarg.1
0x1f661  ldarg.2
0x1f662  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.RequestSecurityTokenResponse [Microsoft.IdentityModel]Microsoft.IdentityModel.SecurityTokenService.SecurityTokenService::Issue(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsPrincipal, class [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.RequestSecurityToken)
0x1f667  stloc.0
0x1f668  ldc.i4   0x15D651
0x1f66d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1f672  ldc.i4.s 0x64
0x1f674  ldstr    aStsCallSuccess_1// "STS Call: Successfully renewed security"...
0x1f679  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1f67e  leave.s  loc_1F6E6
0x1f680  stloc.1
0x1f681  ldloc.1
0x1f682  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/sharepoint"...
0x1f687  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceFailureUtilities::IsTokenIssuanceFailureExceptionInNameSpace(class [mscorlib]System.Exception, string)
0x1f68c  brfalse.s loc_1F6BA
0x1f68e  ldc.i4   0x80D65A
0x1f693  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1f698  ldc.i4.s 0x32
0x1f69a  ldstr    aStsCallFailedT_1// "STS Call: Failed to renew security toke"...
0x1f69f  ldc.i4.1
0x1f6a0  newarr   [mscorlib]System.Object
0x1f6a5  stloc.s  4
0x1f6a7  ldloc.s  4
0x1f6a9  ldc.i4.0
0x1f6aa  ldloc.1
0x1f6ab  callvirt instance string [mscorlib]System.Object::ToString()
0x1f6b0  stelem.ref
0x1f6b1  ldloc.s  4
0x1f6b3  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1f6b8  br.s     loc_1F6E4
0x1f6ba  ldc.i4   0x666F3175
0x1f6bf  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1f6c4  ldc.i4.s 0xF
0x1f6c6  ldstr    aStsCallFailedT_2// "STS Call: Failed to renew security toke"...
0x1f6cb  ldc.i4.1
0x1f6cc  newarr   [mscorlib]System.Object
0x1f6d1  stloc.s  5
0x1f6d3  ldloc.s  5
0x1f6d5  ldc.i4.0
0x1f6d6  ldloc.1
0x1f6d7  callvirt instance string [mscorlib]System.Object::ToString()
0x1f6dc  stelem.ref
0x1f6dd  ldloc.s  5
0x1f6df  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1f6e4  rethrow
0x1f6e6  ldloc.0
0x1f6e7  stloc.2
0x1f6e8  leave.s  loc_1F6F4
0x1f6ea  ldloc.3
0x1f6eb  brfalse.s loc_1F6F3
0x1f6ed  ldloc.3
0x1f6ee  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1f6f3  endfinally
0x1f6f4  ldloc.2
0x1f6f5  ret
```
