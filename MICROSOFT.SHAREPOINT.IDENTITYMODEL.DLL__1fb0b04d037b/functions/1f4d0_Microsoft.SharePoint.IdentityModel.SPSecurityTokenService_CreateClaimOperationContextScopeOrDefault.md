# Microsoft.SharePoint.IdentityModel.SPSecurityTokenService::CreateClaimOperationContextScopeOrDefault

- ea: `0x1f4d0`
- end: `0x1f5fd`
- name: `Microsoft.SharePoint.IdentityModel.SPSecurityTokenService::CreateClaimOperationContextScopeOrDefault`
- size: `301`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x1f380`
- `0x1f3c0`

## callees

- `0x1f4d0`

## string_xrefs

- `0x1f568`: `urn:schemas-microsoft-com:sharepoint:service`
- `0x1f4e5`: `Not creating SPClaimsOperationContext since there is one on the thread already. Uri: '{0}'.`
- `0x1f580`: `STS Call: Not creating SPClaimsOperationContext since AppliesTo point to Service Aplication. Value: '{0}'.`
- `0x1f5a7`: `STS Call: Creating Claims Operations Scope for Applies To Uri: '{0}'.`
- `0x1f5db`: `Couldn't create claims operation from claims identity. Exception: '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0x1f4d0  ldnull
0x1f4d1  stloc.0
0x1f4d2  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPClaimsOperationContext [Microsoft.SharePoint]Microsoft.SharePoint.SPClaimsOperationContext::get_Current()
0x1f4d7  brfalse.s loc_1F50E
0x1f4d9  ldc.i4   0x44738D
0x1f4de  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1f4e3  ldc.i4.s 0x32
0x1f4e5  ldstr    aNotCreatingSpc// "Not creating SPClaimsOperationContext s"...
0x1f4ea  ldc.i4.1
0x1f4eb  newarr   [mscorlib]System.Object
0x1f4f0  stloc.3
0x1f4f1  ldloc.3
0x1f4f2  ldc.i4.0
0x1f4f3  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPClaimsOperationContext [Microsoft.SharePoint]Microsoft.SharePoint.SPClaimsOperationContext::get_Current()
0x1f4f8  callvirt instance class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.SPClaimsOperationContext::get_Uri()
0x1f4fd  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSSanitizer::SanitizeAbsoluteUri(class [System]System.Uri)
0x1f502  stelem.ref
0x1f503  ldloc.3
0x1f504  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1f509  br       loc_1F5CC
0x1f50e  ldarg.1
0x1f50f  brtrue.s loc_1F52C
0x1f511  ldc.i4   0x44738E
0x1f516  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1f51b  ldc.i4.s 0x32
0x1f51d  ldstr    aStsCallNotCrea// "STS Call: Not creating SPClaimsOperatio"...
0x1f522  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1f527  br       loc_1F5CC
0x1f52c  ldnull
0x1f52d  ldarg.1
0x1f52e  callvirt instance class [System.ServiceModel]System.ServiceModel.EndpointAddress [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.WSTrustMessage::get_AppliesTo()
0x1f533  call     bool [System.ServiceModel]System.ServiceModel.EndpointAddress::op_Equality(class [System.ServiceModel]System.ServiceModel.EndpointAddress, class [System.ServiceModel]System.ServiceModel.EndpointAddress)
0x1f538  brtrue.s loc_1F54F
0x1f53a  ldnull
0x1f53b  ldarg.1
0x1f53c  callvirt instance class [System.ServiceModel]System.ServiceModel.EndpointAddress [Microsoft.IdentityModel]Microsoft.IdentityModel.Protocols.WSTrust.WSTrustMessage::get_AppliesTo()
0x1f541  callvirt instance class [System]System.Uri [System.ServiceModel]System.ServiceModel.EndpointAddress::get_Uri()
0x1f546  dup
0x1f547  stloc.1
0x1f548  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x1f54d  brfalse.s loc_1F567
0x1f54f  ldc.i4   0x44738F
0x1f554  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1f559  ldc.i4.s 0x32
0x1f55b  ldstr    aStsCallNotCrea_0// "STS Call: Not creating SPClaimsOperatio"...
0x1f560  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1f565  br.s     loc_1F5CC
0x1f567  ldloc.1
0x1f568  ldstr    aUrnSchemasMicr// "urn:schemas-microsoft-com:sharepoint:se"...
0x1f56d  callvirt instance bool [mscorlib]System.Object::Equals(object)
0x1f572  brfalse.s loc_1F59B
0x1f574  ldc.i4   0x447390
0x1f579  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1f57e  ldc.i4.s 0x32
0x1f580  ldstr    aStsCallNotCrea_1// "STS Call: Not creating SPClaimsOperatio"...
0x1f585  ldc.i4.1
0x1f586  newarr   [mscorlib]System.Object
0x1f58b  stloc.s  4
0x1f58d  ldloc.s  4
0x1f58f  ldc.i4.0
0x1f590  ldloc.1
0x1f591  stelem.ref
0x1f592  ldloc.s  4
0x1f594  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1f599  br.s     loc_1F5CC
0x1f59b  ldc.i4   0x447391
0x1f5a0  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1f5a5  ldc.i4.s 0x32
0x1f5a7  ldstr    aStsCallCreatin// "STS Call: Creating Claims Operations Sc"...
0x1f5ac  ldc.i4.1
0x1f5ad  newarr   [mscorlib]System.Object
0x1f5b2  stloc.s  5
0x1f5b4  ldloc.s  5
0x1f5b6  ldc.i4.0
0x1f5b7  ldloc.1
0x1f5b8  stelem.ref
0x1f5b9  ldloc.s  5
0x1f5bb  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1f5c0  ldloc.1
0x1f5c1  call     class [Microsoft.SharePoint]Microsoft.SharePoint.SPClaimsOperationContext [Microsoft.SharePoint]Microsoft.SharePoint.SPClaimsOperationContext::Create(class [System]System.Uri)
0x1f5c6  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPClaimsOperationContextScope::.ctor(class [Microsoft.SharePoint]Microsoft.SharePoint.SPClaimsOperationContext)
0x1f5cb  stloc.0
0x1f5cc  leave.s  loc_1F5FB
0x1f5ce  stloc.2
0x1f5cf  ldc.i4   0x447392
0x1f5d4  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_SecurityTokenService()
0x1f5d9  ldc.i4.s 0xA
0x1f5db  ldstr    aCouldnTCreateC// "Couldn't create claims operation from c"...
0x1f5e0  ldc.i4.1
0x1f5e1  newarr   [mscorlib]System.Object
0x1f5e6  stloc.s  6
0x1f5e8  ldloc.s  6
0x1f5ea  ldc.i4.0
0x1f5eb  ldloc.2
0x1f5ec  callvirt instance string [mscorlib]System.Object::ToString()
0x1f5f1  stelem.ref
0x1f5f2  ldloc.s  6
0x1f5f4  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1f5f9  leave.s  loc_1F5FB
0x1f5fb  ldloc.0
0x1f5fc  ret
```
