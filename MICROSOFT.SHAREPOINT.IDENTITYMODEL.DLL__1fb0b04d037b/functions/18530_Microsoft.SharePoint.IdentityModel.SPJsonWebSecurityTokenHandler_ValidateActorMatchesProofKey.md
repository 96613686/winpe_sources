# Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::ValidateActorMatchesProofKey

- ea: `0x18530`
- end: `0x186db`
- name: `Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::ValidateActorMatchesProofKey`
- size: `427`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x183e0`

## callees

- `0x18180`
- `0x18530`
- `0x19000`

## string_xrefs

- `0x18597`: `proofToken`
- `0x1858d`: `The proofToken is null.`
- `0x185da`: `No trusted login provider found for the proof token.`
- `0x1868e`: `The actor name identifier claim value doesn't match proof token provider name. ClaimType: '{0}', ClaimValue: '{1};, ProviderName: '{2}'.`

## pseudocode

```c

```

## disassembly

```asm
0x18530  ldarg.0
0x18531  brtrue.s loc_18554
0x18533  ldc.i4   0x65040F
0x18538  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::get_Category()
0x1853d  ldc.i4.s 0xA
0x1853f  ldstr    aTheIdentitiesI// "The identities is null."
0x18544  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x18549  ldstr    aIdentities// "identities"
0x1854e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x18553  throw
0x18554  ldarg.0
0x18555  callvirt instance int32 [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Count()
0x1855a  brtrue.s loc_1857E
0x1855c  ldc.i4   0x650410
0x18561  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::get_Category()
0x18566  ldc.i4.s 0xA
0x18568  ldstr    aTheIdentitiesI_0// "The identities is empty."
0x1856d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x18572  ldnull
0x18573  ldstr    aIdentities// "identities"
0x18578  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x1857d  throw
0x1857e  ldarg.1
0x1857f  brtrue.s loc_185A2
0x18581  ldc.i4   0x650411
0x18586  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::get_Category()
0x1858b  ldc.i4.s 0xA
0x1858d  ldstr    aTheProoftokenI// "The proofToken is null."
0x18592  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x18597  ldstr    aProoftoken_1// "proofToken"
0x1859c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x185a1  throw
0x185a2  ldarg.0
0x185a3  ldc.i4.0
0x185a4  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Item(int32)
0x185a9  isinst   [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentity
0x185ae  stloc.0
0x185af  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_Local()
0x185b4  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedLoginProviderCollection [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_TrustedLoginProviders()
0x185b9  ldarg.1
0x185ba  callvirt instance class [System]System.Security.Cryptography.X509Certificates.X509Certificate2 Microsoft.SharePoint.IdentityModel.SPProofTokenContext::get_SigningCertificate()
0x185bf  callvirt instance var<u1> class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedProviderCollection`1<class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedLoginProvider>::GetProviderBySigningCertificate(!!T0)
0x185c4  stloc.1
0x185c5  ldnull
0x185c6  ldloc.1
0x185c7  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0x185cc  brfalse.s loc_185FF
0x185ce  ldc.i4   0x14211B
0x185d3  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::get_Category()
0x185d8  ldc.i4.s 0xA
0x185da  ldstr    aNoTrustedLogin// "No trusted login provider found for the"...
0x185df  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x185e4  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x185e9  ldstr    aProvidernotfou// "ProviderNotFoundForThumbprint"
0x185ee  ldc.i4.0
0x185ef  newarr   [mscorlib]System.Object
0x185f4  call     string [Microsoft.SharePoint]Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo, string, object[])
0x185f9  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x185fe  throw
0x185ff  ldloc.0
0x18600  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentity::get_Actor()
0x18605  brtrue.s loc_18638
0x18607  ldc.i4   0x14211C
0x1860c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::get_Category()
0x18611  ldc.i4.s 0xA
0x18613  ldstr    aNoActorIdentit// "No actor identity found on the identity"...
0x18618  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1861d  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18622  ldstr    aIdentitydoesno// "IdentityDoesNotHaveActor"
0x18627  ldc.i4.0
0x18628  newarr   [mscorlib]System.Object
0x1862d  call     string [Microsoft.SharePoint]Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo, string, object[])
0x18632  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x18637  throw
0x18638  ldloc.0
0x18639  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentity::get_Actor()
0x1863e  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x18643  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPServerToServerProtocolConstants::get_InternalUserPrincipalNameClaimType()
0x18648  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimCollectionExtensions::GetSingleClaim(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection, string)
0x1864d  stloc.2
0x1864e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18653  callvirt instance int32 [mscorlib]System.Globalization.CultureInfo::get_LCID()
0x18658  call     class [mscorlib]System.Globalization.CompareInfo [mscorlib]System.Globalization.CompareInfo::GetCompareInfo(int32)
0x1865d  stloc.3
0x1865e  ldloc.2
0x1865f  brfalse.s loc_18682
0x18661  ldloc.2
0x18662  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x18667  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x1866c  brtrue.s loc_18682
0x1866e  ldloc.3
0x1866f  ldloc.2
0x18670  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x18675  ldloc.1
0x18676  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x1867b  callvirt instance int32 [mscorlib]System.Globalization.CompareInfo::Compare(string, string)
0x18680  brfalse.s loc_186DA
0x18682  ldc.i4   0x14211D
0x18687  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::get_Category()
0x1868c  ldc.i4.s 0x32
0x1868e  ldstr    aTheActorNameId// "The actor name identifier claim value d"...
0x18693  ldc.i4.3
0x18694  newarr   [mscorlib]System.Object
0x18699  stloc.s  4
0x1869b  ldloc.s  4
0x1869d  ldc.i4.0
0x1869e  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPServerToServerProtocolConstants::get_InternalUserPrincipalNameClaimType()
0x186a3  stelem.ref
0x186a4  ldloc.s  4
0x186a6  ldc.i4.1
0x186a7  ldloc.2
0x186a8  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x186ad  stelem.ref
0x186ae  ldloc.s  4
0x186b0  ldc.i4.2
0x186b1  ldloc.1
0x186b2  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Name()
0x186b7  stelem.ref
0x186b8  ldloc.s  4
0x186ba  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x186bf  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x186c4  ldstr    aActordoesnotma// "ActorDoesNotMatchThumbprint"
0x186c9  ldc.i4.0
0x186ca  newarr   [mscorlib]System.Object
0x186cf  call     string [Microsoft.SharePoint]Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo, string, object[])
0x186d4  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x186d9  throw
0x186da  ret
```
