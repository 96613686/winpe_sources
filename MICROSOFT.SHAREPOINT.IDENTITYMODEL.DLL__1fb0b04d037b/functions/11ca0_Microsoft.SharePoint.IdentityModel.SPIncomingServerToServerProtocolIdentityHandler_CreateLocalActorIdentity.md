# Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::CreateLocalActorIdentity

- ea: `0x11ca0`
- end: `0x11da5`
- name: `Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::CreateLocalActorIdentity`
- size: `261`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x3bb0`
- `0x4270`

## callees

- `0xeaf0`
- `0x11ca0`

## string_xrefs

- `0x11ca9`: `contextUri`
- `0x11cb7`: `incomingActorIdentity`
- `0x11cde`: `CreateLocalActorIdentity: Couldn't get actor's identity claim.`
- `0x11d19`: `CreateLocalActorIdentity: Couldn't create sharepoint identity caim for actor claim:[ClaimType:{0}, ClaimValue:{1}]`
- `0x11d88`: `CreateLocalActorIdentity: Created actor identity with name:{0}`

## pseudocode

```c

```

## disassembly

```asm
0x11ca0  ldnull
0x11ca1  ldarg.0
0x11ca2  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x11ca7  brfalse.s loc_11CB4
0x11ca9  ldstr    aContexturi// "contextUri"
0x11cae  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x11cb3  throw
0x11cb4  ldarg.1
0x11cb5  brtrue.s loc_11CC2
0x11cb7  ldstr    aIncomingactori// "incomingActorIdentity"
0x11cbc  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x11cc1  throw
0x11cc2  ldarg.0
0x11cc3  ldarg.1
0x11cc4  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x11cc9  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim Microsoft.SharePoint.IdentityModel.SPIdentityClaimMapperOperations::ResolveApplicationIdentityClaim(class [System]System.Uri contextUri, class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection inputClaims)
0x11cce  stloc.0
0x11ccf  ldloc.0
0x11cd0  brtrue.s loc_11D03
0x11cd2  ldc.i4   0x256400
0x11cd7  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x11cdc  ldc.i4.s 0x64
0x11cde  ldstr    aCreatelocalact// "CreateLocalActorIdentity: Couldn't get "...
0x11ce3  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x11ce8  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x11ced  ldstr    aGenericoauther// "GenericOAuthErrorOccured"
0x11cf2  ldc.i4.0
0x11cf3  newarr   [mscorlib]System.Object
0x11cf8  call     string [Microsoft.SharePoint]Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo, string, object[])
0x11cfd  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x11d02  throw
0x11d03  ldloc.0
0x11d04  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::CreateSharePointIdentityClaim(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim)
0x11d09  stloc.0
0x11d0a  ldloc.0
0x11d0b  brtrue.s loc_11D58
0x11d0d  ldc.i4   0x256401
0x11d12  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x11d17  ldc.i4.s 0xA
0x11d19  ldstr    aCreatelocalact_0// "CreateLocalActorIdentity: Couldn't crea"...
0x11d1e  ldc.i4.2
0x11d1f  newarr   [mscorlib]System.Object
0x11d24  stloc.2
0x11d25  ldloc.2
0x11d26  ldc.i4.0
0x11d27  ldloc.0
0x11d28  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_ClaimType()
0x11d2d  stelem.ref
0x11d2e  ldloc.2
0x11d2f  ldc.i4.1
0x11d30  ldloc.0
0x11d31  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x11d36  stelem.ref
0x11d37  ldloc.2
0x11d38  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x11d3d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_CurrentCulture()
0x11d42  ldstr    aGenericoauther// "GenericOAuthErrorOccured"
0x11d47  ldc.i4.0
0x11d48  newarr   [mscorlib]System.Object
0x11d4d  call     string [Microsoft.SharePoint]Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo, string, object[])
0x11d52  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x11d57  throw
0x11d58  ldarg.1
0x11d59  callvirt instance string [mscorlib]System.Security.Principal.IIdentity::get_AuthenticationType()
0x11d5e  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentity::.ctor(string)
0x11d63  stloc.1
0x11d64  ldloc.1
0x11d65  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x11d6a  ldloc.0
0x11d6b  callvirt instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection::Add(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim)
0x11d70  ldloc.1
0x11d71  ldloc.0
0x11d72  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_ClaimType()
0x11d77  callvirt instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::set_NameClaimType(string)
0x11d7c  ldc.i4   0x256402
0x11d81  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x11d86  ldc.i4.s 0x64
0x11d88  ldstr    aCreatelocalact_1// "CreateLocalActorIdentity: Created actor"...
0x11d8d  ldc.i4.1
0x11d8e  newarr   [mscorlib]System.Object
0x11d93  stloc.3
0x11d94  ldloc.3
0x11d95  ldc.i4.0
0x11d96  ldloc.1
0x11d97  callvirt instance string [mscorlib]System.Security.Principal.IIdentity::get_Name()
0x11d9c  stelem.ref
0x11d9d  ldloc.3
0x11d9e  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x11da3  ldloc.1
0x11da4  ret
```
