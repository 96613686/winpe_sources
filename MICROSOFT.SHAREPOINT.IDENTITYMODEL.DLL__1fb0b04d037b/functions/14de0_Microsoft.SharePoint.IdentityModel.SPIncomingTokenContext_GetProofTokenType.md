# Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::GetProofTokenType

- ea: `0x14de0`
- end: `0x14f0b`
- name: `Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::GetProofTokenType`
- size: `299`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140a0`

## callees

- `0x14de0`

## string_xrefs

- `0x14de3`: `claimsIdentity`
- `0x14e10`: `SPIncomingServerToServerProtocolIdentityHandler identity doesn't have ProofTokenType claim`
- `0x14e51`: `SPIncomingServerToServerProtocolIdentityHandler Token type found. {0}`
- `0x14e8e`: `SPIncomingServerToServerProtocolIdentityHandler Token type not an integer. Value: '{0}'.`
- `0x14ebc`: `SPIncomingServerToServerProtocolIdentityHandler: Token type found. Value: '{0}'.`
- `0x14ee9`: `SPIncomingServerToServerProtocolIdentityHandler: Token type unknwon. Value: '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0x14de0  ldarg.0
0x14de1  brtrue.s loc_14DEE
0x14de3  ldstr    aClaimsidentity// "claimsIdentity"
0x14de8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x14ded  throw
0x14dee  ldarg.0
0x14def  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x14df4  ldsfld   string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPServerToServerProtocolConstants::ProofTokenTypeClaimType
0x14df9  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimCollectionExtensions::GetSingleClaim(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection, string)
0x14dfe  stloc.0
0x14dff  ldc.i4.0
0x14e00  stloc.1
0x14e01  ldloc.0
0x14e02  brtrue.s loc_14E1F
0x14e04  ldc.i4   0x164F39C
0x14e09  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x14e0e  ldc.i4.s 0xA
0x14e10  ldstr    aSpincomingserv_0// "SPIncomingServerToServerProtocolIdentit"...
0x14e15  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x14e1a  br       loc_14F09
0x14e1f  ldc.i4.0
0x14e20  stloc.2
0x14e21  ldsfld   valuetype [mscorlib]System.Guid Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::FixMisleadingLogKillSwitch
0x14e26  ldstr    a10112017// "10/11/2017"
0x14e2b  ldstr    aFixMisleadingL// "Fix misleading log message."
0x14e30  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid, string, string)
0x14e35  brfalse.s loc_14E73
0x14e37  ldloc.0
0x14e38  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x14e3d  ldloca.s 2
0x14e3f  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0x14e44  pop
0x14e45  ldc.i4   0x164F39D
0x14e4a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x14e4f  ldc.i4.s 0xA
0x14e51  ldstr    aSpincomingserv_1// "SPIncomingServerToServerProtocolIdentit"...
0x14e56  ldc.i4.1
0x14e57  newarr   [mscorlib]System.Object
0x14e5c  stloc.3
0x14e5d  ldloc.3
0x14e5e  ldc.i4.0
0x14e5f  ldloc.2
0x14e60  box      [mscorlib]System.Int32
0x14e65  stelem.ref
0x14e66  ldloc.3
0x14e67  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x14e6c  ldloc.2
0x14e6d  stloc.1
0x14e6e  br       loc_14F09
0x14e73  ldloc.0
0x14e74  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x14e79  ldloca.s 2
0x14e7b  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0x14e80  brtrue.s loc_14EAE
0x14e82  ldc.i4   0x17E3611
0x14e87  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x14e8c  ldc.i4.s 0xA
0x14e8e  ldstr    aSpincomingserv_2// "SPIncomingServerToServerProtocolIdentit"...
0x14e93  ldc.i4.1
0x14e94  newarr   [mscorlib]System.Object
0x14e99  stloc.s  4
0x14e9b  ldloc.s  4
0x14e9d  ldc.i4.0
0x14e9e  ldloc.0
0x14e9f  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x14ea4  stelem.ref
0x14ea5  ldloc.s  4
0x14ea7  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x14eac  br.s     loc_14F09
0x14eae  ldloc.2
0x14eaf  stloc.1
0x14eb0  ldc.i4   0x17E3612
0x14eb5  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x14eba  ldc.i4.s 0x32
0x14ebc  ldstr    aSpincomingserv_3// "SPIncomingServerToServerProtocolIdentit"...
0x14ec1  ldc.i4.1
0x14ec2  newarr   [mscorlib]System.Object
0x14ec7  stloc.s  5
0x14ec9  ldloc.s  5
0x14ecb  ldc.i4.0
0x14ecc  ldloc.1
0x14ecd  box      [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPOAuthProofTokenTypes
0x14ed2  stelem.ref
0x14ed3  ldloc.s  5
0x14ed5  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x14eda  leave.s  loc_14F09
0x14edc  pop
0x14edd  ldc.i4   0x17E3613
0x14ee2  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x14ee7  ldc.i4.s 0xA
0x14ee9  ldstr    aSpincomingserv_4// "SPIncomingServerToServerProtocolIdentit"...
0x14eee  ldc.i4.1
0x14eef  newarr   [mscorlib]System.Object
0x14ef4  stloc.s  6
0x14ef6  ldloc.s  6
0x14ef8  ldc.i4.0
0x14ef9  ldloc.2
0x14efa  box      [mscorlib]System.Int32
0x14eff  stelem.ref
0x14f00  ldloc.s  6
0x14f02  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x14f07  leave.s  loc_14F09
0x14f09  ldloc.1
0x14f0a  ret
```
