# Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::IsProofTokenRequired

- ea: `0x187d0`
- end: `0x1885e`
- name: `Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::IsProofTokenRequired`
- size: `142`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18370`

## callees

- `0x18180`
- `0x187d0`

## string_xrefs

- `0x18808`: `No identities in the json token so no proof token validation required.`
- `0x1883a`: `No single proof key claim so no proof token validation required.`
- `0x18852`: `There is a single proof key claim so proof token validation required.`

## pseudocode

```c

```

## disassembly

```asm
0x187d0  ldarg.1
0x187d1  brtrue.s loc_187F4
0x187d3  ldc.i4   0x650413
0x187d8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::get_Category()
0x187dd  ldc.i4.s 0xA
0x187df  ldstr    aTheIdentitiesI// "The identities is null."
0x187e4  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x187e9  ldstr    aIdentities// "identities"
0x187ee  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x187f3  throw
0x187f4  ldarg.1
0x187f5  callvirt instance int32 [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Count()
0x187fa  brtrue.s loc_18814
0x187fc  ldc.i4   0x142120
0x18801  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::get_Category()
0x18806  ldc.i4.s 0x64
0x18808  ldstr    aNoIdentitiesIn// "No identities in the json token so no p"...
0x1880d  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x18812  ldc.i4.0
0x18813  ret
0x18814  ldarg.1
0x18815  ldc.i4.0
0x18816  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection::get_Item(int32)
0x1881b  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0x18820  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimTypes::get_ProofKey()
0x18825  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimCollectionExtensions::GetSingleClaim(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection, string)
0x1882a  stloc.0
0x1882b  ldloc.0
0x1882c  brtrue.s loc_18846
0x1882e  ldc.i4   0x7CC18E
0x18833  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::get_Category()
0x18838  ldc.i4.s 0x64
0x1883a  ldstr    aNoSingleProofK// "No single proof key claim so no proof t"...
0x1883f  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x18844  ldc.i4.0
0x18845  ret
0x18846  ldc.i4   0x7CC18F
0x1884b  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::get_Category()
0x18850  ldc.i4.s 0x64
0x18852  ldstr    aThereIsASingle// "There is a single proof key claim so pr"...
0x18857  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1885c  ldc.i4.1
0x1885d  ret
```
