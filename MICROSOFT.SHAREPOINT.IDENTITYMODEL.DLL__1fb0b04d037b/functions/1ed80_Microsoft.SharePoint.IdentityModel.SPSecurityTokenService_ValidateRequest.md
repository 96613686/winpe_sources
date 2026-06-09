# Microsoft.SharePoint.IdentityModel.SPSecurityTokenService::ValidateRequest

- ea: `0x1ed80`
- end: `0x1edea`
- name: `Microsoft.SharePoint.IdentityModel.SPSecurityTokenService::ValidateRequest`
- size: `106`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x1ed80`

## string_xrefs

- `0x1ed80`: `SPSecurityTokenService.ValidateRequest`
- `0x1ed9a`: `STS Call: Validating request to security token.`
- `0x1edac`: `http://schemas.microsoft.com/idfx/requesttype/issue`
- `0x1edcc`: `STS Call: Success validating request to security token.`

## pseudocode

```c

```

## disassembly

```asm
0x1ed80  ldstr    aSpsecuritytoke_4// "SPSecurityTokenService.ValidateRequest"
0x1ed85  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string)
0x1ed8a  stloc.1
0x1ed8b  ldc.i4   0x66327574
0x1ed90  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1ed95  ldc.i4   0xC8
0x1ed9a  ldstr    aStsCallValidat// "STS Call: Validating request to securit"...
0x1ed9f  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1eda4  ldarg.1
0x1eda5  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.WSTrustMessage::get_RequestType()
0x1edaa  stloc.0
0x1edab  ldarg.1
0x1edac  ldstr    aHttpSchemasMic_0// "http://schemas.microsoft.com/idfx/reque"...
0x1edb1  callvirt instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.WSTrustMessage::set_RequestType(string)
0x1edb6  ldarg.0
0x1edb7  ldarg.1
0x1edb8  call     instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.SecurityTokenService.SecurityTokenService::ValidateRequest(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.RequestSecurityToken)
0x1edbd  ldc.i4   0x15D64B
0x1edc2  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1edc7  ldc.i4   0xC8
0x1edcc  ldstr    aStsCallSuccess// "STS Call: Success validating request to"...
0x1edd1  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1edd6  ldarg.1
0x1edd7  ldloc.0
0x1edd8  callvirt instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.WSTrustMessage::set_RequestType(string)
0x1eddd  leave.s  loc_1EDE9
0x1eddf  ldloc.1
0x1ede0  brfalse.s loc_1EDE8
0x1ede2  ldloc.1
0x1ede3  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1ede8  endfinally
0x1ede9  ret
```
