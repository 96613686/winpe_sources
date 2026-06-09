# Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::ValidateSecureTokenIfAppOnly

- ea: `0x11ad0`
- end: `0x11c16`
- name: `Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::ValidateSecureTokenIfAppOnly`
- size: `326`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x118a0`

## callees

- `0x11ad0`
- `0x12a60`

## string_xrefs

- `0x11aea`: `ValidateSecureTokenIfAppOnly: EvoStsAppOnlyTokens feature is not enabled`
- `0x11b18`: `ValidateSecureTokenIfAppOnly: No identities in the token`
- `0x11b3a`: `ValidateSecureTokenIfAppOnly: Identity in the token is null`
- `0x11b59`: `ValidateSecureTokenIfAppOnly: This is not an app-only token, returning.`
- `0x11b97`: `ValidateSecureTokenIfAppOnly: App only token was not retrieved using certificate, AppIdAcr = '{0}'`
- `0x11bba`: `UnsupportedAppOnlyToken`
- `0x11bff`: `UnsupportedAppOnlyToken`
- `0x11bf0`: `ValidateSecureTokenIfAppOnly: App only token does not have roles claim`

## pseudocode

```c

```

## disassembly

```asm
0x11ad0  ldc.i4   0x2912
0x11ad5  ldnull
0x11ad6  ldnull
0x11ad7  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.DarkDeploymentUtility::IsFeatureEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId, class [Microsoft.SharePoint]Microsoft.SharePoint.SPContext, class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb)
0x11adc  brtrue.s loc_11AF5
0x11ade  ldc.i4   0x71A657
0x11ae3  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x11ae8  ldc.i4.s 0x32
0x11aea  ldstr    aValidatesecure// "ValidateSecureTokenIfAppOnly: EvoStsApp"...
0x11aef  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x11af4  ret
0x11af5  ldarg.0
0x11af6  brtrue.s loc_11B03
0x11af8  ldstr    aResult_0// "result"
0x11afd  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x11b02  throw
0x11b03  ldc.i4.1
0x11b04  ldarg.0
0x11b05  callvirt instance int32 [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Count()
0x11b0a  beq.s    loc_11B23
0x11b0c  ldc.i4   0x71A658
0x11b11  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x11b16  ldc.i4.s 0x32
0x11b18  ldstr    aValidatesecure_0// "ValidateSecureTokenIfAppOnly: No identi"...
0x11b1d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x11b22  ret
0x11b23  ldarg.0
0x11b24  ldc.i4.0
0x11b25  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Item(int32)
0x11b2a  stloc.0
0x11b2b  ldloc.0
0x11b2c  brtrue.s loc_11B45
0x11b2e  ldc.i4   0x71A659
0x11b33  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x11b38  ldc.i4.s 0x32
0x11b3a  ldstr    aValidatesecure_1// "ValidateSecureTokenIfAppOnly: Identity "...
0x11b3f  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x11b44  ret
0x11b45  ldloc.0
0x11b46  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPApplicationOnlyIdentity::IsApplicationOnlyIdentity(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity)
0x11b4b  brtrue.s loc_11B64
0x11b4d  ldc.i4   0x71A65A
0x11b52  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x11b57  ldc.i4.s 0x64
0x11b59  ldstr    aValidatesecure_2// "ValidateSecureTokenIfAppOnly: This is n"...
0x11b5e  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x11b63  ret
0x11b64  ldloc.0
0x11b65  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x11b6a  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::GetAppIdAccredationClaim(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection claimCollection)
0x11b6f  stloc.1
0x11b70  ldloc.1
0x11b71  brfalse  loc_11C15
0x11b76  ldc.i4.m1
0x11b77  stloc.2
0x11b78  ldloc.1
0x11b79  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x11b7e  ldloca.s 2
0x11b80  call     bool [mscorlib]System.Int32::TryParse(string, int32&)
0x11b85  brfalse.s loc_11B8B
0x11b87  ldloc.2
0x11b88  ldc.i4.2
0x11b89  beq.s    loc_11BD0
0x11b8b  ldc.i4   0x71A65B
0x11b90  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x11b95  ldc.i4.s 0x32
0x11b97  ldstr    aValidatesecure_3// "ValidateSecureTokenIfAppOnly: App only "...
0x11b9c  ldc.i4.1
0x11b9d  newarr   [mscorlib]System.Object
0x11ba2  stloc.s  4
0x11ba4  ldloc.s  4
0x11ba6  ldc.i4.0
0x11ba7  ldloc.2
0x11ba8  box      [mscorlib]System.Int32
0x11bad  stelem.ref
0x11bae  ldloc.s  4
0x11bb0  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x11bb5  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x11bba  ldstr    aUnsupportedapp// "UnsupportedAppOnlyToken"
0x11bbf  ldc.i4.0
0x11bc0  newarr   [mscorlib]System.Object
0x11bc5  call     string [Microsoft.SharePoint]Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo, string, object[])
0x11bca  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenValidationException::.ctor(string)
0x11bcf  throw
0x11bd0  ldloc.0
0x11bd1  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x11bd6  ldstr    aRoles// "roles"
0x11bdb  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimCollectionExtensions::GetSingleClaim(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection, string)
0x11be0  stloc.3
0x11be1  ldloc.3
0x11be2  brtrue.s loc_11C15
0x11be4  ldc.i4   0x71A65C
0x11be9  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x11bee  ldc.i4.s 0x32
0x11bf0  ldstr    aValidatesecure_4// "ValidateSecureTokenIfAppOnly: App only "...
0x11bf5  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x11bfa  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x11bff  ldstr    aUnsupportedapp// "UnsupportedAppOnlyToken"
0x11c04  ldc.i4.0
0x11c05  newarr   [mscorlib]System.Object
0x11c0a  call     string [Microsoft.SharePoint]Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo, string, object[])
0x11c0f  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenValidationException::.ctor(string)
0x11c14  throw
0x11c15  ret
```
