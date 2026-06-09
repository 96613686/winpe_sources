# Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::ValidateCrossTenantToken

- ea: `0x118e0`
- end: `0x11acd`
- name: `Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::ValidateCrossTenantToken`
- size: `493`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x118a0`

## callees

- `0x118e0`
- `0x12eb0`

## string_xrefs

- `0x11903`: `ValidateCrossTenantToken: No identities in the token`
- `0x11925`: `ValidateCrossTenantToken: Identity in the token is null`
- `0x11944`: `ValidateCrossTenantToken: Identity claim is null`
- `0x1196b`: `ValidateCrossTenantToken: This is cross tenant call. Validate issuer.`
- `0x1198f`: `Cross Tenant Token Issuer is empty.`
- `0x119d5`: `ValidateCrossTenantToken: Issuer is not SharePoint. Expected: '{0}', Actual: '{1}'`
- `0x119f7`: `Issuer of crosss tenant token is not SharePoint.`
- `0x11a36`: `ValidateCrossTenantToken: This is cross tenant call. Tid Claim should be present.`
- `0x11a6e`: `ValidateCrossTenantToken: This is cross tenant call. Idp Claim should be present.`
- `0x11aa6`: `ValidateCrossTenantToken: This is cross tenant call. AppId Claim should be present.`
- `0x11abc`: `ValidateCrossTenantToken: Set cross tenant call conext on thread context.`

## pseudocode

```c

```

## disassembly

```asm
0x118e0  ldarg.0
0x118e1  brtrue.s loc_118EE
0x118e3  ldstr    aResult_0// "result"
0x118e8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x118ed  throw
0x118ee  ldc.i4.1
0x118ef  ldarg.0
0x118f0  callvirt instance int32 [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Count()
0x118f5  beq.s    loc_1190E
0x118f7  ldc.i4   0x134A48B
0x118fc  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x11901  ldc.i4.s 0x32
0x11903  ldstr    aValidatecrosst// "ValidateCrossTenantToken: No identities"...
0x11908  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1190d  ret
0x1190e  ldarg.0
0x1190f  ldc.i4.0
0x11910  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Item(int32)
0x11915  stloc.0
0x11916  ldloc.0
0x11917  brtrue.s loc_11930
0x11919  ldc.i4   0x134A48C
0x1191e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x11923  ldc.i4.s 0x32
0x11925  ldstr    aValidatecrosst_0// "ValidateCrossTenantToken: Identity in t"...
0x1192a  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1192f  ret
0x11930  ldloc.0
0x11931  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x11936  brtrue.s loc_1194F
0x11938  ldc.i4   0x134A48D
0x1193d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x11942  ldc.i4.s 0x32
0x11944  ldstr    aValidatecrosst_1// "ValidateCrossTenantToken: Identity clai"...
0x11949  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1194e  ret
0x1194f  ldloc.0
0x11950  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x11955  call     bool Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::IsCrossTenantCall(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection claims)
0x1195a  brfalse  loc_11ACC
0x1195f  ldc.i4   0x134A48E
0x11964  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x11969  ldc.i4.s 0x32
0x1196b  ldstr    aValidatecrosst_2// "ValidateCrossTenantToken: This is cross"...
0x11970  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x11975  ldloc.0
0x11976  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x1197b  ldc.i4.0
0x1197c  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection::get_Item(int32)
0x11981  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Issuer()
0x11986  stloc.1
0x11987  ldloc.1
0x11988  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1198d  brfalse.s loc_1199A
0x1198f  ldstr    aCrossTenantTok// "Cross Tenant Token Issuer is empty."
0x11994  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPException::.ctor(string)
0x11999  throw
0x1199a  ldloc.1
0x1199b  ldc.i4.1
0x1199c  newarr   [mscorlib]System.Char
0x119a1  stloc.s  4
0x119a3  ldloc.s  4
0x119a5  ldc.i4.0
0x119a6  ldc.i4.s 0x40
0x119a8  stelem.i2
0x119a9  ldloc.s  4
0x119ab  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x119b0  ldc.i4.0
0x119b1  ldelem.ref
0x119b2  stloc.1
0x119b3  ldloc.1
0x119b4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x119b9  brtrue.s loc_119C9
0x119bb  ldloc.1
0x119bc  ldstr    a0000000300000f// "00000003-0000-0ff1-ce00-000000000000"
0x119c1  ldc.i4.3
0x119c2  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x119c7  brtrue.s loc_11A02
0x119c9  ldc.i4   0x134A48F
0x119ce  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x119d3  ldc.i4.s 0x32
0x119d5  ldstr    aValidatecrosst_3// "ValidateCrossTenantToken: Issuer is not"...
0x119da  ldc.i4.2
0x119db  newarr   [mscorlib]System.Object
0x119e0  stloc.s  5
0x119e2  ldloc.s  5
0x119e4  ldc.i4.0
0x119e5  ldstr    a0000000300000f// "00000003-0000-0ff1-ce00-000000000000"
0x119ea  stelem.ref
0x119eb  ldloc.s  5
0x119ed  ldc.i4.1
0x119ee  ldloc.1
0x119ef  stelem.ref
0x119f0  ldloc.s  5
0x119f2  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x119f7  ldstr    aIssuerOfCrosss// "Issuer of crosss tenant token is not Sh"...
0x119fc  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.SPException::.ctor(string)
0x11a01  throw
0x11a02  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPCrossTenantContext::.ctor()
0x11a07  stloc.2
0x11a08  ldloc.0
0x11a09  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x11a0e  ldstr    aTid// "tid"
0x11a13  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimCollectionExtensions::GetSingleClaim(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection, string)
0x11a18  stloc.3
0x11a19  ldloc.3
0x11a1a  brfalse.s loc_11A2A
0x11a1c  ldloc.2
0x11a1d  ldloc.3
0x11a1e  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x11a23  stfld    string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPCrossTenantContext::Tid
0x11a28  br.s     loc_11A40
0x11a2a  ldc.i4   0x134A490
0x11a2f  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x11a34  ldc.i4.s 0xA
0x11a36  ldstr    aValidatecrosst_4// "ValidateCrossTenantToken: This is cross"...
0x11a3b  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x11a40  ldloc.0
0x11a41  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x11a46  ldstr    aIdp// "idp"
0x11a4b  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimCollectionExtensions::GetSingleClaim(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection, string)
0x11a50  stloc.3
0x11a51  ldloc.3
0x11a52  brfalse.s loc_11A62
0x11a54  ldloc.2
0x11a55  ldloc.3
0x11a56  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x11a5b  stfld    string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPCrossTenantContext::Idp
0x11a60  br.s     loc_11A78
0x11a62  ldc.i4   0x134A491
0x11a67  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x11a6c  ldc.i4.s 0xA
0x11a6e  ldstr    aValidatecrosst_5// "ValidateCrossTenantToken: This is cross"...
0x11a73  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x11a78  ldloc.0
0x11a79  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x11a7e  ldstr    aAppid// "appid"
0x11a83  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimCollectionExtensions::GetSingleClaim(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection, string)
0x11a88  stloc.3
0x11a89  ldloc.3
0x11a8a  brfalse.s loc_11A9A
0x11a8c  ldloc.2
0x11a8d  ldloc.3
0x11a8e  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x11a93  stfld    string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPCrossTenantContext::AppId
0x11a98  br.s     loc_11AB0
0x11a9a  ldc.i4   0x134A492
0x11a9f  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x11aa4  ldc.i4.s 0xA
0x11aa6  ldstr    aValidatecrosst_6// "ValidateCrossTenantToken: This is cross"...
0x11aab  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x11ab0  ldc.i4   0x134A493
0x11ab5  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x11aba  ldc.i4.s 0x32
0x11abc  ldstr    aValidatecrosst_7// "ValidateCrossTenantToken: Set cross ten"...
0x11ac1  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x11ac6  ldloc.2
0x11ac7  call     T0x2B000008
0x11acc  ret
```
