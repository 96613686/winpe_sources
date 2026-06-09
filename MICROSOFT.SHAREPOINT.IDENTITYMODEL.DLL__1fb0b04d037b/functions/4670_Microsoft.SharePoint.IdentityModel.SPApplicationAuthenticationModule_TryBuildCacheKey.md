# Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::TryBuildCacheKey

- ea: `0x4670`
- end: `0x48c0`
- name: `Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::TryBuildCacheKey`
- size: `592`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x4500`

## callees

- `0x4670`

## string_xrefs

- `0x470f`: `SPApplicationAuthenticationModule: Can't reliably build a cache key. [ClaimType: {0}, ClaimValue:{1}] found in incoming token`
- `0x476e`: `SPApplicationAuthenticationModule: Can't build a cache key, NameId claim or NameIdIssuer are null. [NameId:{0}], [NameIdIssuer:{1}]`
- `0x47a9`: `SPApplicationAuthenticationModule: Encoding cache key. Available values: [IdentityProvider:{0}] [NameId:{1}]`
- `0x48a4`: `SPApplicationAuthenticationModule: Generated cachekey {0}`

## pseudocode

```c

```

## disassembly

```asm
0x4670  ldarg.0
0x4671  brtrue.s loc_467E
0x4673  ldstr    aUseridentity// "userIdentity"
0x4678  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x467d  throw
0x467e  ldarg.1
0x467f  ldnull
0x4680  stind.ref
0x4681  ldarg.0
0x4682  call     class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPIdentityContext [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPIdentityContext::Create(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity)
0x4687  stloc.0
0x4688  ldnull
0x4689  stloc.1
0x468a  ldnull
0x468b  stloc.2
0x468c  ldc.i4.1
0x468d  stloc.3
0x468e  ldloc.0
0x468f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPIdentityContext::GetOutboundS2SClaims()
0x4694  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim>::GetEnumerator()
0x4699  stloc.s  9
0x469b  br       loc_473D
0x46a0  ldloc.s  9
0x46a2  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim>::get_Current()
0x46a7  stloc.s  4
0x46a9  ldloc.s  4
0x46ab  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_ClaimType()
0x46b0  ldstr    aNameid// "nameid"
0x46b5  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimTypes::Equals(string, string)
0x46ba  brfalse.s loc_46D0
0x46bc  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimTypes::get_NameId()
0x46c1  ldloc.s  4
0x46c3  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_Value()
0x46c8  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::.ctor(string, string)
0x46cd  stloc.1
0x46ce  br.s     loc_473D
0x46d0  ldloc.s  4
0x46d2  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_ClaimType()
0x46d7  ldstr    aNii// "nii"
0x46dc  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimTypes::Equals(string, string)
0x46e1  brfalse.s loc_46F7
0x46e3  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimTypes::get_NameIdIssuer()
0x46e8  ldloc.s  4
0x46ea  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_Value()
0x46ef  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::.ctor(string, string)
0x46f4  stloc.2
0x46f5  br.s     loc_473D
0x46f7  ldc.i4   0x2B2F
0x46fc  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x4701  brtrue.s loc_473D
0x4703  ldc.i4   0x2563DC
0x4708  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x470d  ldc.i4.s 0x64
0x470f  ldstr    aSpapplicationa_46// "SPApplicationAuthenticationModule: Can'"...
0x4714  ldc.i4.2
0x4715  newarr   [mscorlib]System.Object
0x471a  stloc.s  0xA
0x471c  ldloc.s  0xA
0x471e  ldc.i4.0
0x471f  ldloc.s  4
0x4721  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_ClaimType()
0x4726  stelem.ref
0x4727  ldloc.s  0xA
0x4729  ldc.i4.1
0x472a  ldloc.s  4
0x472c  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_Value()
0x4731  stelem.ref
0x4732  ldloc.s  0xA
0x4734  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x4739  ldc.i4.0
0x473a  stloc.3
0x473b  br.s     loc_4749
0x473d  ldloc.s  9
0x473f  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4744  brtrue   loc_46A0
0x4749  leave.s  loc_4757
0x474b  ldloc.s  9
0x474d  brfalse.s loc_4756
0x474f  ldloc.s  9
0x4751  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4756  endfinally
0x4757  ldloc.3
0x4758  brtrue.s loc_475C
0x475a  ldc.i4.0
0x475b  ret
0x475c  ldloc.1
0x475d  brfalse.s loc_4762
0x475f  ldloc.2
0x4760  brtrue.s loc_478E
0x4762  ldc.i4   0x2563DD
0x4767  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x476c  ldc.i4.s 0x64
0x476e  ldstr    aSpapplicationa_47// "SPApplicationAuthenticationModule: Can'"...
0x4773  ldc.i4.2
0x4774  newarr   [mscorlib]System.Object
0x4779  stloc.s  0xB
0x477b  ldloc.s  0xB
0x477d  ldc.i4.0
0x477e  ldloc.1
0x477f  stelem.ref
0x4780  ldloc.s  0xB
0x4782  ldc.i4.1
0x4783  ldloc.2
0x4784  stelem.ref
0x4785  ldloc.s  0xB
0x4787  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x478c  ldc.i4.0
0x478d  ret
0x478e  ldloc.2
0x478f  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.IdentityServices.SPAuthenticationPipelineClaimMappingManager::ApplyClaimsTransformationToInternal(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim)
0x4794  stloc.s  5
0x4796  ldloc.s  5
0x4798  brtrue.s loc_479D
0x479a  ldloc.2
0x479b  stloc.s  5
0x479d  ldc.i4   0x2563DE
0x47a2  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x47a7  ldc.i4.s 0x64
0x47a9  ldstr    aSpapplicationa_48// "SPApplicationAuthenticationModule: Enco"...
0x47ae  ldc.i4.2
0x47af  newarr   [mscorlib]System.Object
0x47b4  stloc.s  0xC
0x47b6  ldloc.s  0xC
0x47b8  ldc.i4.0
0x47b9  ldloc.s  5
0x47bb  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x47c0  stelem.ref
0x47c1  ldloc.s  0xC
0x47c3  ldc.i4.1
0x47c4  ldloc.1
0x47c5  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x47ca  stelem.ref
0x47cb  ldloc.s  0xC
0x47cd  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x47d2  ldloc.s  5
0x47d4  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x47d9  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPIdentityProviders::GetIdentityProviderType(string)
0x47de  call     valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPOriginalIssuerType [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPOriginalIssuers::GetOriginalIssuerTypeForIdentityProviderType(string)
0x47e3  stloc.s  6
0x47e5  ldloc.s  6
0x47e7  ldloc.s  5
0x47e9  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x47ee  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPOriginalIssuers::GetIssuerIdentifier(string)
0x47f3  ldloc.1
0x47f4  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x47f9  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimProviderManager::EncodeProviderUserKey(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPOriginalIssuerType, string, string)
0x47fe  stloc.s  7
0x4800  ldloc.s  7
0x4802  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x4807  brfalse.s loc_4846
0x4809  ldloc.s  6
0x480b  ldc.i4.s 0x74
0x480d  beq.s    loc_4844
0x480f  ldc.i4   0x35D0D5
0x4814  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x4819  ldc.i4.s 0xA
0x481b  ldstr    aSpapplicationa_49// "SPApplicationAuthenticationModule: Gene"...
0x4820  ldc.i4.2
0x4821  newarr   [mscorlib]System.Object
0x4826  stloc.s  0xD
0x4828  ldloc.s  0xD
0x482a  ldc.i4.0
0x482b  ldloc.1
0x482c  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x4831  stelem.ref
0x4832  ldloc.s  0xD
0x4834  ldc.i4.1
0x4835  ldloc.s  5
0x4837  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0x483c  stelem.ref
0x483d  ldloc.s  0xD
0x483f  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x4844  ldc.i4.0
0x4845  ret
0x4846  ldc.i4   0x2563DF
0x484b  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x4850  ldc.i4.s 0x64
0x4852  ldstr    aSpapplicationa_50// "SPApplicationAuthenticationModule: Deco"...
0x4857  ldc.i4.1
0x4858  newarr   [mscorlib]System.Object
0x485d  stloc.s  0xE
0x485f  ldloc.s  0xE
0x4861  ldc.i4.0
0x4862  ldloc.s  7
0x4864  stelem.ref
0x4865  ldloc.s  0xE
0x4867  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x486c  ldloc.s  7
0x486e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimEncodingManager::DecodeClaim(string)
0x4873  stloc.s  8
0x4875  ldarg.1
0x4876  ldloc.s  8
0x4878  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaim::get_ClaimType()
0x487d  ldloc.s  8
0x487f  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaim::get_Value()
0x4884  ldloc.s  8
0x4886  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaim::get_ValueType()
0x488b  ldloc.s  8
0x488d  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaim::get_OriginalIssuer()
0x4892  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimEncodingManager::EncodeClaimIntoFormsSuffix(string, string, string, string)
0x4897  stind.ref
0x4898  ldc.i4   0x2563E0
0x489d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x48a2  ldc.i4.s 0x64
0x48a4  ldstr    aSpapplicationa_51// "SPApplicationAuthenticationModule: Gene"...
0x48a9  ldc.i4.1
0x48aa  newarr   [mscorlib]System.Object
0x48af  stloc.s  0xF
0x48b1  ldloc.s  0xF
0x48b3  ldc.i4.0
0x48b4  ldarg.1
0x48b5  ldind.ref
0x48b6  stelem.ref
0x48b7  ldloc.s  0xF
0x48b9  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x48be  ldc.i4.1
0x48bf  ret
```
