# Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::EnsureSharePointApplicationIdentityIfNeeded

- ea: `0x12850`
- end: `0x12960`
- name: `Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::EnsureSharePointApplicationIdentityIfNeeded`
- size: `272`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x118a0`

## callees

- `0x12850`
- `0x12fc0`

## string_xrefs

- `0x12875`: `SPIncomingIdentityHandler: No identities in the token, won't create sharepoint applciation identity.`
- `0x128a9`: `SPIncomingIdentityHandler: ServiceAssertedAppV1 Token type, so making Actor as Identity.`
- `0x128d5`: `SPIncomingIdentityHandler: This is not an app-only token, returning.`
- `0x1291a`: `SPIncomingIdentityHandler: Couldn't create an application identity, please see logs above.`
- `0x12944`: `SPIncomingIdentityHandler: Successfully created an application identity and set it main identity with actor:{0}.`

## pseudocode

```c

```

## disassembly

```asm
0x12850  ldarg.0
0x12851  ldind.ref
0x12852  brtrue.s loc_1285F
0x12854  ldstr    aResult_0// "result"
0x12859  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1285e  throw
0x1285f  ldc.i4.1
0x12860  ldarg.0
0x12861  ldind.ref
0x12862  callvirt instance int32 [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Count()
0x12867  beq.s    loc_12880
0x12869  ldc.i4   0x151380
0x1286e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x12873  ldc.i4.s 0x64
0x12875  ldstr    aSpincomingiden_4// "SPIncomingIdentityHandler: No identitie"...
0x1287a  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1287f  ret
0x12880  ldarg.0
0x12881  ldind.ref
0x12882  ldc.i4.0
0x12883  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Item(int32)
0x12888  stloc.0
0x12889  ldc.i4   0x29C3
0x1288e  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x12893  brfalse.s loc_128C1
0x12895  ldloc.0
0x12896  call     bool Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::IsServiceAssertedAppV1(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity claimsIdentity)
0x1289b  brfalse.s loc_128C1
0x1289d  ldc.i4   0x8DF150
0x128a2  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x128a7  ldc.i4.s 0x32
0x128a9  ldstr    aSpincomingiden_5// "SPIncomingIdentityHandler: ServiceAsser"...
0x128ae  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x128b3  ldarg.0
0x128b4  ldind.ref
0x128b5  ldc.i4.0
0x128b6  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Item(int32)
0x128bb  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Actor()
0x128c0  stloc.0
0x128c1  ldloc.0
0x128c2  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPApplicationOnlyIdentity::IsApplicationOnlyIdentity(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity)
0x128c7  brtrue.s loc_128E0
0x128c9  ldc.i4   0x151381
0x128ce  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x128d3  ldc.i4.s 0x64
0x128d5  ldstr    aSpincomingiden_6// "SPIncomingIdentityHandler: This is not "...
0x128da  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x128df  ret
0x128e0  ldnull
0x128e1  stloc.1
0x128e2  ldc.i4   0x2B36
0x128e7  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x128ec  brfalse.s loc_12904
0x128ee  ldloc.0
0x128ef  ldarg.0
0x128f0  ldind.ref
0x128f1  ldc.i4.0
0x128f2  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Item(int32)
0x128f7  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x128fc  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPApplicationOnlyIdentity::Create(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity, class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection)
0x12901  stloc.1
0x12902  br.s     loc_1290B
0x12904  ldloc.0
0x12905  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPApplicationOnlyIdentity::Create(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity)
0x1290a  stloc.1
0x1290b  ldloc.1
0x1290c  brtrue.s loc_12925
0x1290e  ldc.i4   0x151382
0x12913  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x12918  ldc.i4.s 0x64
0x1291a  ldstr    aSpincomingiden_7// "SPIncomingIdentityHandler: Couldn't cre"...
0x1291f  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x12924  ret
0x12925  ldarg.0
0x12926  ldc.i4.1
0x12927  newarr   [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity
0x1292c  stloc.2
0x1292d  ldloc.2
0x1292e  ldc.i4.0
0x1292f  ldloc.1
0x12930  stelem.ref
0x12931  ldloc.2
0x12932  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::.ctor(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity>)
0x12937  stind.ref
0x12938  ldc.i4   0x151383
0x1293d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x12942  ldc.i4.s 0x64
0x12944  ldstr    aSpincomingiden_8// "SPIncomingIdentityHandler: Successfully"...
0x12949  ldc.i4.1
0x1294a  newarr   [mscorlib]System.Object
0x1294f  stloc.3
0x12950  ldloc.3
0x12951  ldc.i4.0
0x12952  ldloc.0
0x12953  callvirt instance string [mscorlib]System.Security.Principal.IIdentity::get_Name()
0x12958  stelem.ref
0x12959  ldloc.3
0x1295a  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1295f  ret
```
