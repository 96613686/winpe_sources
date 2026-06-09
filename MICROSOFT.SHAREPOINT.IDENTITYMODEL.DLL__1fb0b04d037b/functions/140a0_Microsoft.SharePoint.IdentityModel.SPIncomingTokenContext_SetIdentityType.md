# Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::SetIdentityType

- ea: `0x140a0`
- end: `0x14232`
- name: `Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::SetIdentityType`
- size: `402`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x13e90`

## callees

- `0x13030`
- `0x13070`
- `0x13570`
- `0x135a0`
- `0x140a0`
- `0x14da0`
- `0x14de0`

## string_xrefs

- `0x1418b`: `Setting the identity type to UserAndApplication because this is a noauth/preauth request and token.`
- `0x141b7`: `This is proof token scenario, so setting up identity type based on proof token type.`
- `0x141d8`: `This is AppOnly proof token scenario, so setting up identioty typoe as AppOnly.`
- `0x141fa`: `This is AppPlusUser proof token scenrio, so setting up identioty typoe as UserAndApplication.`
- `0x14218`: `This is UserOnly proof token scenrio, so setting up identioty typoe as UserOnly.`

## pseudocode

```c

```

## disassembly

```asm
0x140a0  ldarg.0
0x140a1  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::get_Identity()
0x140a6  callvirt instance int32 [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Count()
0x140ab  brfalse.s loc_140C9
0x140ad  ldarg.0
0x140ae  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::get_Identity()
0x140b3  callvirt instance int32 [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Count()
0x140b8  ldc.i4.1
0x140b9  bgt.s    loc_140C9
0x140bb  ldarg.0
0x140bc  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::get_Identity()
0x140c1  ldc.i4.0
0x140c2  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Item(int32)
0x140c7  brtrue.s loc_140D1
0x140c9  ldarg.0
0x140ca  ldc.i4.0
0x140cb  call     instance void Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::set_IdentityType(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPIncomingOAuthIdentityType value)
0x140d0  ret
0x140d1  ldarg.0
0x140d2  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::get_Identity()
0x140d7  ldc.i4.0
0x140d8  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Item(int32)
0x140dd  stloc.0
0x140de  ldc.i4.0
0x140df  stloc.1
0x140e0  ldloc.0
0x140e1  brfalse.s loc_140EA
0x140e3  ldloc.0
0x140e4  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPApplicationOnlyIdentity::IsSharePointApplicationIdentity(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity)
0x140e9  stloc.1
0x140ea  ldloc.0
0x140eb  brfalse.s loc_14105
0x140ed  ldloc.0
0x140ee  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Actor()
0x140f3  brfalse.s loc_14105
0x140f5  ldloc.0
0x140f6  call     bool Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::IsAnonymousIdentity(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity claimsIdentity)
0x140fb  brfalse.s loc_14105
0x140fd  ldarg.0
0x140fe  ldc.i4.5
0x140ff  call     instance void Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::set_IdentityType(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPIncomingOAuthIdentityType value)
0x14104  ret
0x14105  ldloc.0
0x14106  brfalse.s loc_14118
0x14108  ldloc.0
0x14109  call     bool Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::IsAnonymousIdentity(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity claimsIdentity)
0x1410e  brfalse.s loc_14118
0x14110  ldarg.0
0x14111  ldc.i4.4
0x14112  call     instance void Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::set_IdentityType(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPIncomingOAuthIdentityType value)
0x14117  ret
0x14118  ldloc.0
0x14119  brfalse.s loc_14143
0x1411b  ldloc.0
0x1411c  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Actor()
0x14121  brfalse.s loc_14143
0x14123  ldloc.1
0x14124  brtrue.s loc_14143
0x14126  ldc.i4   0x2803
0x1412b  ldc.i4.3
0x1412c  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPConfigUtility::IsCodeEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPConfigUtility/FlightEnvironment)
0x14131  brfalse.s loc_1413B
0x14133  ldloc.0
0x14134  call     bool Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::HasUserImpersonationScope(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity claimsIdentity)
0x14139  brtrue.s loc_14143
0x1413b  ldarg.0
0x1413c  ldc.i4.3
0x1413d  call     instance void Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::set_IdentityType(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPIncomingOAuthIdentityType value)
0x14142  ret
0x14143  ldloc.0
0x14144  brfalse.s loc_14166
0x14146  ldloc.0
0x14147  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Actor()
0x1414c  brfalse.s loc_14166
0x1414e  ldloc.0
0x1414f  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Actor()
0x14154  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPApplicationOnlyIdentity::IsApplicationOnlyIdentity(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity)
0x14159  brfalse.s loc_14166
0x1415b  ldloc.1
0x1415c  brfalse.s loc_14166
0x1415e  ldarg.0
0x1415f  ldc.i4.2
0x14160  call     instance void Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::set_IdentityType(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPIncomingOAuthIdentityType value)
0x14165  ret
0x14166  ldc.i4   0x374E
0x1416b  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x14170  stloc.2
0x14171  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPWOPIHost::get_IsPreAuthWopiFeatureEnabled()
0x14176  brfalse.s loc_1419D
0x14178  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPWOPIHost::get_IsPreAuthWopiRequest()
0x1417d  brfalse.s loc_1419D
0x1417f  ldc.i4   0x1001844
0x14184  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x14189  ldc.i4.s 0x32
0x1418b  ldstr    aSettingTheIden// "Setting the identity type to UserAndApp"...
0x14190  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x14195  ldarg.0
0x14196  ldc.i4.3
0x14197  call     instance void Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::set_IdentityType(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPIncomingOAuthIdentityType value)
0x1419c  ret
0x1419d  ldloc.2
0x1419e  brfalse  loc_1422A
0x141a3  ldloc.0
0x141a4  call     bool Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::IsProofToken(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity claimsIdentity)
0x141a9  brfalse.s loc_1422A
0x141ab  ldc.i4   0x164F397
0x141b0  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x141b5  ldc.i4.s 0x32
0x141b7  ldstr    aThisIsProofTok// "This is proof token scenario, so settin"...
0x141bc  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x141c1  ldloc.0
0x141c2  call     valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPOAuthProofTokenTypes Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::GetProofTokenType(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity claimsIdentity)
0x141c7  stloc.3
0x141c8  ldloc.3
0x141c9  ldc.i4.1
0x141ca  bne.un.s loc_141EA
0x141cc  ldc.i4   0x164F398
0x141d1  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x141d6  ldc.i4.s 0x32
0x141d8  ldstr    aThisIsApponlyP// "This is AppOnly proof token scenario, s"...
0x141dd  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x141e2  ldarg.0
0x141e3  ldc.i4.2
0x141e4  call     instance void Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::set_IdentityType(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPIncomingOAuthIdentityType value)
0x141e9  ret
0x141ea  ldloc.3
0x141eb  ldc.i4.2
0x141ec  bne.un.s loc_1420C
0x141ee  ldc.i4   0x164F399
0x141f3  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x141f8  ldc.i4.s 0x32
0x141fa  ldstr    aThisIsAppplusu// "This is AppPlusUser proof token scenrio"...
0x141ff  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x14204  ldarg.0
0x14205  ldc.i4.3
0x14206  call     instance void Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::set_IdentityType(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPIncomingOAuthIdentityType value)
0x1420b  ret
0x1420c  ldc.i4   0x164F39A
0x14211  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x14216  ldc.i4.s 0x32
0x14218  ldstr    aThisIsUseronly// "This is UserOnly proof token scenrio, s"...
0x1421d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x14222  ldarg.0
0x14223  ldc.i4.1
0x14224  call     instance void Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::set_IdentityType(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPIncomingOAuthIdentityType value)
0x14229  ret
0x1422a  ldarg.0
0x1422b  ldc.i4.1
0x1422c  call     instance void Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::set_IdentityType(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPIncomingOAuthIdentityType value)
0x14231  ret
```
