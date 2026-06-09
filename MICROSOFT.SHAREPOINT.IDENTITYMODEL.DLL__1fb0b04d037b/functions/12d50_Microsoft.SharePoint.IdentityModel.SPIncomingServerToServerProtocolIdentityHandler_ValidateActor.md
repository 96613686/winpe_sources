# Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::ValidateActor

- ea: `0x12d50`
- end: `0x12ea5`
- name: `Microsoft.SharePoint.IdentityModel.SPIncomingServerToServerProtocolIdentityHandler::ValidateActor`
- size: `341`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x118a0`

## callees

- `0x12d50`
- `0x189a0`

## string_xrefs

- `0x12d53`: `token`
- `0x12d72`: `SPIncomingIdentityHandler: No identities in the token, no actor validation required.`
- `0x12d99`: `SPIncomingIdentityHandler: No actor present in the token, no actor validation required.`
- `0x12dc5`: `SPIncomingIdentityHandler: Token claims have multiple issuers.`
- `0x12dd4`: `MultipleIssuersForSameToken`
- `0x12e31`: `SPIncomingIdentityHandler: Actor doesn't have a name identifier.`
- `0x12e6b`: `SPIncomingIdentityHandler: Issuer identity:{0} doesn't not match actor:{1}.`

## pseudocode

```c

```

## disassembly

```asm
0x12d50  ldarg.0
0x12d51  brtrue.s loc_12D5E
0x12d53  ldstr    aToken// "token"
0x12d58  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x12d5d  throw
0x12d5e  ldarg.0
0x12d5f  callvirt instance int32 [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Count()
0x12d64  brtrue.s loc_12D7D
0x12d66  ldc.i4   0x151387
0x12d6b  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x12d70  ldc.i4.s 0x64
0x12d72  ldstr    aSpincomingiden_9// "SPIncomingIdentityHandler: No identitie"...
0x12d77  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x12d7c  ret
0x12d7d  ldarg.0
0x12d7e  ldc.i4.0
0x12d7f  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Item(int32)
0x12d84  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Actor()
0x12d89  stloc.0
0x12d8a  ldloc.0
0x12d8b  brtrue.s loc_12DA4
0x12d8d  ldc.i4   0x151388
0x12d92  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x12d97  ldc.i4.s 0x64
0x12d99  ldstr    aSpincomingiden_13// "SPIncomingIdentityHandler: No actor pre"...
0x12d9e  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x12da3  ret
0x12da4  ldarg.0
0x12da5  ldc.i4.0
0x12da6  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Item(int32)
0x12dab  call     string Microsoft.SharePoint.IdentityModel.SPClaimsIdentityExtensions::GetIssuerName(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity identity)
0x12db0  stloc.1
0x12db1  ldloc.1
0x12db2  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x12db7  brfalse.s loc_12DEA
0x12db9  ldc.i4   0x151389
0x12dbe  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x12dc3  ldc.i4.s 0x64
0x12dc5  ldstr    aSpincomingiden_14// "SPIncomingIdentityHandler: Token claims"...
0x12dca  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x12dcf  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12dd4  ldstr    aMultipleissuer// "MultipleIssuersForSameToken"
0x12dd9  ldc.i4.0
0x12dda  newarr   [mscorlib]System.Object
0x12ddf  call     string [Microsoft.SharePoint]Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo, string, object[])
0x12de4  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenValidationException::.ctor(string)
0x12de9  throw
0x12dea  ldloc.0
0x12deb  call     class [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPIdentityClaimSet [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPIdentityClaimSet::CreateFromClaimsIdentity(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity)
0x12df0  stloc.2
0x12df1  ldnull
0x12df2  stloc.3
0x12df3  ldloc.2
0x12df4  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPIdentityClaimSet::get_NameId()
0x12df9  brfalse.s loc_12E09
0x12dfb  ldloc.2
0x12dfc  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPIdentityClaimSet::get_NameId()
0x12e01  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x12e06  stloc.3
0x12e07  br.s     loc_12E1D
0x12e09  ldloc.2
0x12e0a  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPIdentityClaimSet::get_Upn()
0x12e0f  brfalse.s loc_12E1D
0x12e11  ldloc.2
0x12e12  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPIdentityClaimSet::get_Upn()
0x12e17  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x12e1c  stloc.3
0x12e1d  ldloc.3
0x12e1e  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x12e23  brfalse.s loc_12E56
0x12e25  ldc.i4   0x15138B
0x12e2a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x12e2f  ldc.i4.s 0x64
0x12e31  ldstr    aSpincomingiden_15// "SPIncomingIdentityHandler: Actor doesn'"...
0x12e36  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x12e3b  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12e40  ldstr    aActordoesnotha// "ActorDoesNotHaveNameIdentifier"
0x12e45  ldc.i4.0
0x12e46  newarr   [mscorlib]System.Object
0x12e4b  call     string [Microsoft.SharePoint]Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo, string, object[])
0x12e50  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenValidationException::.ctor(string)
0x12e55  throw
0x12e56  ldloc.1
0x12e57  ldloc.3
0x12e58  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x12e5d  brfalse.s loc_12EA4
0x12e5f  ldc.i4   0x15138C
0x12e64  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x12e69  ldc.i4.s 0x64
0x12e6b  ldstr    aSpincomingiden_16// "SPIncomingIdentityHandler: Issuer ident"...
0x12e70  ldc.i4.2
0x12e71  newarr   [mscorlib]System.Object
0x12e76  stloc.s  4
0x12e78  ldloc.s  4
0x12e7a  ldc.i4.0
0x12e7b  ldloc.1
0x12e7c  stelem.ref
0x12e7d  ldloc.s  4
0x12e7f  ldc.i4.1
0x12e80  ldloc.3
0x12e81  stelem.ref
0x12e82  ldloc.s  4
0x12e84  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x12e89  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x12e8e  ldstr    aIssueridentity// "IssuerIdentityDoesNotMatchActor"
0x12e93  ldc.i4.0
0x12e94  newarr   [mscorlib]System.Object
0x12e99  call     string [Microsoft.SharePoint]Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo, string, object[])
0x12e9e  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenValidationException::.ctor(string)
0x12ea3  throw
0x12ea4  ret
```
