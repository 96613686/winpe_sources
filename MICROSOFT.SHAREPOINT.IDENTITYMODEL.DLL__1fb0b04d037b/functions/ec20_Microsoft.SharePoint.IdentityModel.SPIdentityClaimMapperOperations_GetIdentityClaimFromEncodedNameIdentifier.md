# Microsoft.SharePoint.IdentityModel.SPIdentityClaimMapperOperations::GetIdentityClaimFromEncodedNameIdentifier

- ea: `0xec20`
- end: `0xecf9`
- name: `Microsoft.SharePoint.IdentityModel.SPIdentityClaimMapperOperations::GetIdentityClaimFromEncodedNameIdentifier`
- size: `217`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0xeba0`

## callees

- `0xec20`

## string_xrefs

- `0xec3c`: `An AccessToken request was found. Will try to get the encoded identity claim.`
- `0xec74`: `Getting the encoded identity from the AccessToken request succeeded. [nameId: {0}]`
- `0xeca1`: `Exception while trying to decode the Access Token's Name Identifier in SPIdentityClaimMapperOperations GetIdentityClaim: [nameId: {0}], Exception: {1}`
- `0xecd2`: `A Name Identifier claim could not be found in the SP or AccessToken`

## pseudocode

```c

```

## disassembly

```asm
0xec20  ldarg.0
0xec21  brtrue.s loc_EC2E
0xec23  ldstr    aInputclaims// "inputClaims"
0xec28  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xec2d  throw
0xec2e  ldnull
0xec2f  stloc.0
0xec30  ldc.i4   0x11A49F
0xec35  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xec3a  ldc.i4.s 0x64
0xec3c  ldstr    aAnAccesstokenR// "An AccessToken request was found. Will "...
0xec41  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xec46  ldarg.0
0xec47  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPServerToServerProtocolConstants::get_InternalNameIdClaimType()
0xec4c  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimCollectionExtensions::GetSingleClaim(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection, string)
0xec51  stloc.1
0xec52  ldloc.1
0xec53  brfalse.s loc_ECC6
0xec55  ldloc.1
0xec56  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0xec5b  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimEncodingManager::DecodeClaimFromFormsSuffix(string)
0xec60  stloc.2
0xec61  ldloc.2
0xec62  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSPClaimExtensions::CreateClaim(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaim)
0xec67  stloc.0
0xec68  ldc.i4   0x11A4A0
0xec6d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xec72  ldc.i4.s 0x64
0xec74  ldstr    aGettingTheEnco// "Getting the encoded identity from the A"...
0xec79  ldc.i4.1
0xec7a  newarr   [mscorlib]System.Object
0xec7f  stloc.s  4
0xec81  ldloc.s  4
0xec83  ldc.i4.0
0xec84  ldloc.1
0xec85  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0xec8a  stelem.ref
0xec8b  ldloc.s  4
0xec8d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xec92  leave.s  loc_ECF7
0xec94  stloc.3
0xec95  ldc.i4   0x11A4A1
0xec9a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xec9f  ldc.i4.s 0xA
0xeca1  ldstr    aExceptionWhile_0// "Exception while trying to decode the Ac"...
0xeca6  ldc.i4.2
0xeca7  newarr   [mscorlib]System.Object
0xecac  stloc.s  5
0xecae  ldloc.s  5
0xecb0  ldc.i4.0
0xecb1  ldloc.1
0xecb2  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0xecb7  stelem.ref
0xecb8  ldloc.s  5
0xecba  ldc.i4.1
0xecbb  ldloc.3
0xecbc  stelem.ref
0xecbd  ldloc.s  5
0xecbf  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xecc4  rethrow
0xecc6  ldc.i4   0x11A4A2
0xeccb  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xecd0  ldc.i4.s 0xA
0xecd2  ldstr    aANameIdentifie// "A Name Identifier claim could not be fo"...
0xecd7  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xecdc  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xece1  ldstr    aNoencodedident// "NoEncodedIdentityClaimFound"
0xece6  ldc.i4.0
0xece7  newarr   [mscorlib]System.Object
0xecec  call     string [Microsoft.SharePoint]Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo, string, object[])
0xecf1  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xecf6  throw
0xecf7  ldloc.0
0xecf8  ret
```
