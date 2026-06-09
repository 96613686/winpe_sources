# Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::ApplyClaimsMapping

- ea: `0x11db0`
- end: `0x122d2`
- name: `Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::ApplyClaimsMapping`
- size: `1314`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x118a0`

## callees

- `0x11db0`
- `0x122e0`
- `0x123b0`
- `0x123f0`
- `0x12440`
- `0x12470`
- `0x12d10`

## string_xrefs

- `0x120c8`: `ApplyClaimsMapping: Evo STS token feature is enabled.`
- `0x120e2`: `ApplyClaimsMapping: Evo AppOnly token feature is enabled.`
- `0x12280`: `ApplyClaimsMapping: Current Identity already have NameId Claim type: {0}.`

## pseudocode

```c

```

## disassembly

```asm
0x11db0  ldarg.0
0x11db1  ldind.ref
0x11db2  brtrue.s loc_11DBF
0x11db4  ldstr    aCollection// "collection"
0x11db9  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x11dbe  throw
0x11dbf  ldarg.0
0x11dc0  ldind.ref
0x11dc1  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity> [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::GetEnumerator()
0x11dc6  stloc.s  0xC
0x11dc8  br       loc_122B7
0x11dcd  ldloc.s  0xC
0x11dcf  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity>::get_Current()
0x11dd4  castclass [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentity
0x11dd9  stloc.0
0x11dda  ldloc.0
0x11ddb  stloc.1
0x11ddc  br       loc_122B1
0x11de1  ldnull
0x11de2  stloc.2
0x11de3  ldc.i4.0
0x11de4  stloc.3
0x11de5  br       loc_1202F
0x11dea  ldloc.1
0x11deb  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x11df0  ldloc.3
0x11df1  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection::get_Item(int32)
0x11df6  stloc.s  4
0x11df8  ldloc.s  4
0x11dfa  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_ClaimType()
0x11dff  ldstr    aNameid// "nameid"
0x11e04  call     bool [mscorlib]System.String::op_Equality(string, string)
0x11e09  brtrue.s loc_11E21
0x11e0b  ldloc.s  4
0x11e0d  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_ClaimType()
0x11e12  ldstr    aPuid// "puid"
0x11e17  call     bool [mscorlib]System.String::op_Equality(string, string)
0x11e1c  brfalse  loc_11F5F
0x11e21  ldc.i4   0x29C2
0x11e26  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x11e2b  brfalse  loc_11EE5
0x11e30  ldc.i4   0x100D402
0x11e35  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x11e3a  ldc.i4.s 0x32
0x11e3c  ldstr    aApplyclaimsmap// "ApplyClaimsMapping: Claim Type {0} Clai"...
0x11e41  ldc.i4.2
0x11e42  newarr   [mscorlib]System.Object
0x11e47  stloc.s  0xD
0x11e49  ldloc.s  0xD
0x11e4b  ldc.i4.0
0x11e4c  ldloc.s  4
0x11e4e  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_ClaimType()
0x11e53  stelem.ref
0x11e54  ldloc.s  0xD
0x11e56  ldc.i4.1
0x11e57  ldloc.s  4
0x11e59  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x11e5e  stelem.ref
0x11e5f  ldloc.s  0xD
0x11e61  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x11e66  ldloc.0
0x11e67  ldloc.1
0x11e68  bne.un.s loc_11ECA
0x11e6a  ldloc.1
0x11e6b  call     bool Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::ShouldAddLiveDotComSuffice(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity currentIdentity)
0x11e70  brfalse.s loc_11ECA
0x11e72  ldloc.s  4
0x11e74  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_ClaimType()
0x11e79  ldstr    aNameid// "nameid"
0x11e7e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x11e83  brfalse.s loc_11E93
0x11e85  ldloc.s  4
0x11e87  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x11e8c  call     bool Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::IsSidFormat(string value)
0x11e91  brtrue.s loc_11ECA
0x11e93  ldloc.1
0x11e94  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x11e99  ldloc.3
0x11e9a  ldloc.s  4
0x11e9c  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPServerToServerProtocolConstants::get_InternalNameIdClaimType()
0x11ea1  ldsfld   class [mscorlib]System.Func`2<string, string> Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::CS$<>9__CachedAnonymousMethodDelegate2
0x11ea6  brtrue.s loc_11EB9
0x11ea8  ldnull
0x11ea9  ldftn    string Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::<ApplyClaimsMapping>b__0(string value)
0x11eaf  newobj   instance void class [mscorlib]System.Func`2<string, string>::.ctor(object, native int)
0x11eb4  stsfld   class [mscorlib]System.Func`2<string, string> Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::CS$<>9__CachedAnonymousMethodDelegate2
0x11eb9  ldsfld   class [mscorlib]System.Func`2<string, string> Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::CS$<>9__CachedAnonymousMethodDelegate2
0x11ebe  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::ApplyClaimTransform(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim claim, string newClaimType, [opt] class [mscorlib]System.Func`2<string, string> valueTransform)
0x11ec3  callvirt instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection::set_Item(int32, class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim)
0x11ec8  br.s     loc_11F41
0x11eca  ldloc.1
0x11ecb  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x11ed0  ldloc.3
0x11ed1  ldloc.s  4
0x11ed3  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPServerToServerProtocolConstants::get_InternalNameIdClaimType()
0x11ed8  ldnull
0x11ed9  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::ApplyClaimTransform(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim claim, string newClaimType, [opt] class [mscorlib]System.Func`2<string, string> valueTransform)
0x11ede  callvirt instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection::set_Item(int32, class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim)
0x11ee3  br.s     loc_11F41
0x11ee5  ldloc.0
0x11ee6  ldloc.1
0x11ee7  bne.un.s loc_11F28
0x11ee9  ldloc.1
0x11eea  call     bool Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::ShouldAddLiveDotComSuffice(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity currentIdentity)
0x11eef  brfalse.s loc_11F28
0x11ef1  ldloc.1
0x11ef2  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x11ef7  ldloc.3
0x11ef8  ldloc.s  4
0x11efa  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPServerToServerProtocolConstants::get_InternalNameIdClaimType()
0x11eff  ldsfld   class [mscorlib]System.Func`2<string, string> Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::CS$<>9__CachedAnonymousMethodDelegate3
0x11f04  brtrue.s loc_11F17
0x11f06  ldnull
0x11f07  ldftn    string Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::<ApplyClaimsMapping>b__1(string value)
0x11f0d  newobj   instance void class [mscorlib]System.Func`2<string, string>::.ctor(object, native int)
0x11f12  stsfld   class [mscorlib]System.Func`2<string, string> Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::CS$<>9__CachedAnonymousMethodDelegate3
0x11f17  ldsfld   class [mscorlib]System.Func`2<string, string> Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::CS$<>9__CachedAnonymousMethodDelegate3
0x11f1c  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::ApplyClaimTransform(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim claim, string newClaimType, [opt] class [mscorlib]System.Func`2<string, string> valueTransform)
0x11f21  callvirt instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection::set_Item(int32, class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim)
0x11f26  br.s     loc_11F41
0x11f28  ldloc.1
0x11f29  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x11f2e  ldloc.3
0x11f2f  ldloc.s  4
0x11f31  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPServerToServerProtocolConstants::get_InternalNameIdClaimType()
0x11f36  ldnull
0x11f37  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::ApplyClaimTransform(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim claim, string newClaimType, [opt] class [mscorlib]System.Func`2<string, string> valueTransform)
0x11f3c  callvirt instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection::set_Item(int32, class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim)
0x11f41  ldloc.s  4
0x11f43  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_ClaimType()
0x11f48  ldstr    aPuid// "puid"
0x11f4d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x11f52  brfalse  loc_1202B
0x11f57  ldloc.s  4
0x11f59  stloc.2
0x11f5a  br       loc_1202B
0x11f5f  ldloc.s  4
0x11f61  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_ClaimType()
0x11f66  ldstr    aNii// "nii"
0x11f6b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x11f70  brtrue.s loc_11F85
0x11f72  ldloc.s  4
0x11f74  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_ClaimType()
0x11f79  ldstr    aIdentityprovid_0// "identityprovider"
0x11f7e  call     bool [mscorlib]System.String::op_Equality(string, string)
0x11f83  brfalse.s loc_11FA3
0x11f85  ldloc.1
0x11f86  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x11f8b  ldloc.3
0x11f8c  ldloc.s  4
0x11f8e  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPServerToServerProtocolConstants::get_InternalNameIdentifierIssuerClaimType()
0x11f93  ldnull
0x11f94  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::ApplyClaimTransform(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim claim, string newClaimType, [opt] class [mscorlib]System.Func`2<string, string> valueTransform)
0x11f99  callvirt instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection::set_Item(int32, class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim)
0x11f9e  br       loc_1202B
0x11fa3  ldloc.s  4
0x11fa5  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_ClaimType()
0x11faa  ldstr    aUpn// "upn"
0x11faf  call     bool [mscorlib]System.String::op_Equality(string, string)
0x11fb4  brfalse.s loc_11FD1
0x11fb6  ldloc.1
0x11fb7  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x11fbc  ldloc.3
0x11fbd  ldloc.s  4
0x11fbf  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPServerToServerProtocolConstants::get_InternalUserPrincipalNameClaimType()
0x11fc4  ldnull
0x11fc5  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::ApplyClaimTransform(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim claim, string newClaimType, [opt] class [mscorlib]System.Func`2<string, string> valueTransform)
0x11fca  callvirt instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection::set_Item(int32, class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim)
0x11fcf  br.s     loc_1202B
0x11fd1  ldloc.s  4
0x11fd3  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_ClaimType()
0x11fd8  ldstr    aSmtp// "smtp"
0x11fdd  call     bool [mscorlib]System.String::op_Equality(string, string)
0x11fe2  brfalse.s loc_11FFF
0x11fe4  ldloc.1
0x11fe5  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x11fea  ldloc.3
0x11feb  ldloc.s  4
0x11fed  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPServerToServerProtocolConstants::get_InternalSMTPClaimType()
0x11ff2  ldnull
0x11ff3  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::ApplyClaimTransform(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim claim, string newClaimType, [opt] class [mscorlib]System.Func`2<string, string> valueTransform)
0x11ff8  callvirt instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection::set_Item(int32, class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim)
0x11ffd  br.s     loc_1202B
0x11fff  ldloc.s  4
0x12001  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_ClaimType()
0x12006  ldstr    aSip// "sip"
0x1200b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x12010  brfalse.s loc_1202B
0x12012  ldloc.1
0x12013  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x12018  ldloc.3
0x12019  ldloc.s  4
0x1201b  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPServerToServerProtocolConstants::get_InternalSIPClaimType()
0x12020  ldnull
0x12021  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::ApplyClaimTransform(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim claim, string newClaimType, [opt] class [mscorlib]System.Func`2<string, string> valueTransform)
0x12026  callvirt instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection::set_Item(int32, class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim)
0x1202b  ldloc.3
0x1202c  ldc.i4.1
0x1202d  add
0x1202e  stloc.3
0x1202f  ldloc.3
0x12030  ldloc.1
0x12031  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x12036  callvirt instance int32 [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection::get_Count()
0x1203b  blt      loc_11DEA
0x12040  ldloc.2
0x12041  brfalse.s loc_12093
0x12043  ldloc.1
0x12044  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x12049  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPServerToServerProtocolConstants::get_InternalNameIdentifierIssuerClaimType()
0x1204e  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimCollectionExtensions::GetSingleClaim(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection, string)
0x12053  brtrue.s loc_12093
0x12055  call     class [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPAuthenticationPipelineClaimMapping Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::GetFormsMembershipIdentityProviderMapping()
0x1205a  stloc.s  5
0x1205c  ldnull
0x1205d  ldloc.s  5
0x1205f  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x12064  brfalse.s loc_12093
0x12066  ldloc.1
0x12067  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x1206c  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPServerToServerProtocolConstants::get_InternalNameIdentifierIssuerClaimType()
0x12071  ldloc.s  5
0x12073  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPAuthenticationPipelineClaimMapping::get_ExternalClaimValue()
0x12078  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimValueTypes::get_String()
0x1207d  ldloc.2
0x1207e  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Issuer()
0x12083  ldloc.2
0x12084  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_OriginalIssuer()
0x12089  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::.ctor(string, string, string, string, string)
0x1208e  callvirt instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection::Add(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim)
0x12093  ldc.i4   0x2890
0x12098  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x1209d  stloc.s  6
0x1209f  ldc.i4   0x2912
0x120a4  ldnull
0x120a5  ldnull
0x120a6  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.DarkDeploymentUtility::IsFeatureEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId, class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext, class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb)
0x120ab  stloc.s  7
0x120ad  ldloc.s  6
0x120af  brtrue.s loc_120B8
0x120b1  ldloc.s  7
0x120b3  brfalse  loc_1229F
0x120b8  ldloc.s  6
0x120ba  brfalse.s loc_120D2
0x120bc  ldc.i4   0x723391
0x120c1  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x120c6  ldc.i4.s 0x64
0x120c8  ldstr    aApplyclaimsmap_0// "ApplyClaimsMapping: Evo STS token featu"...
0x120cd  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x120d2  ldloc.s  7
0x120d4  brfalse.s loc_120EC
0x120d6  ldc.i4   0x723392
0x120db  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x120e0  ldc.i4.s 0x64
0x120e2  ldstr    aApplyclaimsmap_1// "ApplyClaimsMapping: Evo AppOnly token f"...
0x120e7  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x120ec  ldloc.1
0x120ed  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x120f2  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPServerToServerProtocolConstants::get_InternalNameIdClaimType()
0x120f7  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimCollectionExtensions::GetSingleClaim(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection, string)
0x120fc  stloc.s  8
0x120fe  ldloc.s  8
0x12100  brtrue   loc_12274
0x12105  ldloc.1
0x12106  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x1210b  ldstr    aTid// "tid"
0x12110  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimCollectionExtensions::GetSingleClaim(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection, string)
0x12115  stloc.s  9
0x12117  ldnull
0x12118  stloc.s  0xA
0x1211a  ldc.i4   0x2B3C
0x1211f  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x12124  brfalse.s loc_12186
0x12126  ldloc.1
0x12127  call     bool Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::IsClientAppAsIdentityAllowed(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity identity)
0x1212c  brfalse.s loc_12140
0x1212e  ldloc.1
0x1212f  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x12134  ldstr    aClientappid// "clientappid"
0x12139  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimCollectionExtensions::GetSingleClaim(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection, string)
0x1213e  stloc.s  0xA
0x12140  ldloc.s  0xA
0x12142  brtrue.s loc_1216E
0x12144  ldc.i4   0x10638CE
0x12149  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x1214e  ldc.i4.s 0x32
0x12150  ldstr    aApplyclaimsmap_2// "ApplyClaimsMapping: ClientAppId claim n"...
0x12155  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1215a  ldloc.1
0x1215b  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x12160  ldstr    aAppid// "appid"
0x12165  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimCollectionExtensions::GetSingleClaim(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection, string)
0x1216a  stloc.s  0xA
0x1216c  br.s     loc_12198
0x1216e  ldc.i4   0x10638CF
0x12173  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x12178  ldc.i4.s 0x32
0x1217a  ldstr    aApplyclaimsmap_3// "ApplyClaimsMapping: ClientAppId claim f"...
0x1217f  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x12184  br.s     loc_12198
  ... truncated ...
```
