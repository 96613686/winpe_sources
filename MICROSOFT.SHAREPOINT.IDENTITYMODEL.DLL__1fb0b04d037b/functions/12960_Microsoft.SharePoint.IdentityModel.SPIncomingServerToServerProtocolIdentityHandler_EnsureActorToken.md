# Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::EnsureActorToken

- ea: `0x12960`
- end: `0x12a57`
- name: `Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::EnsureActorToken`
- size: `247`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x118a0`

## callees

- `0x12960`
- `0x12a60`
- `0x12a80`
- `0x12fc0`

## string_xrefs

- `0x12964`: `token`
- `0x12984`: `SPIncomingIdentityHandler: No identities in the token, no actor validation required.`
- `0x129e2`: `SPIncomingIdentityHandler: No actor claim in the token, no actor generation required.`

## pseudocode

```c

```

## disassembly

```asm
0x12960  ldarg.0
0x12961  ldind.ref
0x12962  brtrue.s loc_1296F
0x12964  ldstr    aToken// "token"
0x12969  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1296e  throw
0x1296f  ldarg.0
0x12970  ldind.ref
0x12971  callvirt instance int32 [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Count()
0x12976  brtrue.s loc_1298F
0x12978  ldc.i4   0x151384
0x1297d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x12982  ldc.i4.s 0x64
0x12984  ldstr    aSpincomingiden_9// "SPIncomingIdentityHandler: No identitie"...
0x12989  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1298e  ret
0x1298f  ldarg.0
0x12990  ldind.ref
0x12991  ldc.i4.0
0x12992  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Item(int32)
0x12997  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Actor()
0x1299c  stloc.0
0x1299d  ldc.i4   0x29C3
0x129a2  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x129a7  brfalse.s loc_129BC
0x129a9  ldloc.0
0x129aa  brfalse.s loc_129C0
0x129ac  ldarg.0
0x129ad  ldind.ref
0x129ae  ldc.i4.0
0x129af  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Item(int32)
0x129b4  call     bool Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::IsServiceAssertedAppV1(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity claimsIdentity)
0x129b9  brtrue.s loc_129C0
0x129bb  ret
0x129bc  ldloc.0
0x129bd  brfalse.s loc_129C0
0x129bf  ret
0x129c0  ldarg.0
0x129c1  ldind.ref
0x129c2  ldc.i4.0
0x129c3  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Item(int32)
0x129c8  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x129cd  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::GetActorClaim(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection claims)
0x129d2  stloc.1
0x129d3  ldloc.1
0x129d4  brtrue.s loc_129ED
0x129d6  ldc.i4   0x151385
0x129db  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x129e0  ldc.i4.s 0x64
0x129e2  ldstr    aSpincomingiden_10// "SPIncomingIdentityHandler: No actor cla"...
0x129e7  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x129ec  ret
0x129ed  ldloc.1
0x129ee  ldarg.0
0x129ef  ldind.ref
0x129f0  ldc.i4.0
0x129f1  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Item(int32)
0x129f6  callvirt instance string [mscorlib]System.Security.Principal.IIdentity::get_AuthenticationType()
0x129fb  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPApplicationOnlyIdentity::CreateIdentity(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim, string)
0x12a00  stloc.2
0x12a01  ldloc.2
0x12a02  brtrue.s loc_12A05
0x12a04  ret
0x12a05  ldarg.0
0x12a06  ldind.ref
0x12a07  ldc.i4.0
0x12a08  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Item(int32)
0x12a0d  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x12a12  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::GetAppIdAccredationClaim(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection claimCollection)
0x12a17  stloc.3
0x12a18  ldloc.3
0x12a19  brfalse.s loc_12A48
0x12a1b  ldloc.2
0x12a1c  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x12a21  ldloc.3
0x12a22  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_ClaimType()
0x12a27  ldloc.3
0x12a28  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x12a2d  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimValueTypes::get_String()
0x12a32  ldloc.1
0x12a33  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Issuer()
0x12a38  ldloc.1
0x12a39  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_OriginalIssuer()
0x12a3e  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::.ctor(string, string, string, string, string)
0x12a43  callvirt instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection::Add(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim)
0x12a48  ldarg.0
0x12a49  ldind.ref
0x12a4a  ldc.i4.0
0x12a4b  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Item(int32)
0x12a50  ldloc.2
0x12a51  callvirt instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::set_Actor(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity)
0x12a56  ret
```
