# Microsoft.SharePoint.IdentityModel.SPIdentityClaimResolver::EnsureOriginalUserLogonClaims

- ea: `0xef70`
- end: `0xf2d9`
- name: `Microsoft.SharePoint.IdentityModel.SPIdentityClaimResolver::EnsureOriginalUserLogonClaims`
- size: `873`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1d380`

## callees

- `0xcec0`
- `0xef70`

## string_xrefs

- `0xef79`: `contextUri`
- `0xf198`: `No roles were added for the mapped Forms identity. [UserIdentity: {0}], [RoleProviderName: {1}], [ContextUri: {2}]`
- `0xf1c8`: `No role provider found. [RoleProviderName: {0}], [ContextUri: {1}]`
- `0xf1f3`: `No Role provider for forms authentication. [ContextUri: {0}]`

## pseudocode

```c

```

## disassembly

```asm
0xef70  ldnull
0xef71  ldarg.0
0xef72  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0xef77  brfalse.s loc_EF84
0xef79  ldstr    aContexturi// "contextUri"
0xef7e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xef83  throw
0xef84  ldarg.1
0xef85  brtrue.s loc_EF92
0xef87  ldstr    aSharepointiden// "sharePointIdentityClaim"
0xef8c  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xef91  throw
0xef92  ldarg.2
0xef93  brtrue.s loc_EFA0
0xef95  ldstr    aLogonidentity// "logonIdentity"
0xef9a  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xef9f  throw
0xefa0  ldarg.3
0xefa1  brtrue.s loc_EFAE
0xefa3  ldstr    aOutputidentity// "outputIdentity"
0xefa8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xefad  throw
0xefae  ldnull
0xefaf  stloc.0
0xefb0  ldarg.1
0xefb1  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaim::get_Value()
0xefb6  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimEncodingManager::DecodeClaimFromFormsSuffix(string)
0xefbb  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaim::get_OriginalIssuer()
0xefc0  stloc.1
0xefc1  ldarg.0
0xefc2  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPIisSettings [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimProviderManager::GetSettingsForContext(class [System]System.Uri)
0xefc7  stloc.2
0xefc8  ldloc.2
0xefc9  brtrue.s loc_F00B
0xefcb  ldc.i4   0x21A5C5
0xefd0  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xefd5  ldc.i4.s 0xA
0xefd7  ldstr    aCouldNotGetSpi// "Could not get SPIisSettings for url '{0"...
0xefdc  ldc.i4.1
0xefdd  newarr   [mscorlib]System.Object
0xefe2  stloc.s  0xB
0xefe4  ldloc.s  0xB
0xefe6  ldc.i4.0
0xefe7  ldarg.0
0xefe8  stelem.ref
0xefe9  ldloc.s  0xB
0xefeb  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xeff0  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0xeff5  ldstr    aIissettingsnot// "IISSettingsNotFound"
0xeffa  ldc.i4.0
0xeffb  newarr   [mscorlib]System.Object
0xf000  call     string [Microsoft.SharePoint]Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo, string, object[])
0xf005  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0xf00a  throw
0xf00b  ldloc.2
0xf00c  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPIisSettings::get_UseWindowsClaimsAuthenticationProvider()
0xf011  brfalse.s loc_F07B
0xf013  ldloc.1
0xf014  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPIdentityProviderTypes::get_Windows()
0xf019  ldc.i4.5
0xf01a  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xf01f  brfalse.s loc_F07B
0xf021  ldarg.3
0xf022  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0xf027  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimTypes::get_UserLogonName()
0xf02c  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimCollectionExtensions::GetSingleClaim(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection, string)
0xf031  stloc.0
0xf032  ldloc.0
0xf033  brtrue   loc_F2D8
0xf038  ldc.i4   0x11A4C4
0xf03d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xf042  ldc.i4.s 0x64
0xf044  ldstr    aAddingTheUserl// "Adding the UserLogonName claim that is "...
0xf049  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xf04e  ldarg.3
0xf04f  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0xf054  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimTypes::get_UserLogonName()
0xf059  ldarg.2
0xf05a  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0xf05f  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimValueTypes::get_String()
0xf064  ldstr    aSharepoint// "SharePoint"
0xf069  ldc.i4.s 0x77
0xf06b  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPOriginalIssuers::Format(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPOriginalIssuerType)
0xf070  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::.ctor(string, string, string, string, string)
0xf075  callvirt instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection::Add(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim)
0xf07a  ret
0xf07b  ldloc.2
0xf07c  callvirt instance bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPIisSettings::get_UseFormsClaimsAuthenticationProvider()
0xf081  brfalse  loc_F20D
0xf086  ldloc.1
0xf087  ldarg.0
0xf088  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimTypes::get_UserLogonName()
0xf08d  call     string Microsoft.SharePoint.IdentityModel.SPFormsOriginalIssuerBuilder::CreateOriginalIssuerFromContext(class [System]System.Uri contextUri, string claimType)
0xf092  ldc.i4.5
0xf093  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0xf098  brfalse  loc_F20D
0xf09d  ldarg.3
0xf09e  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0xf0a3  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimTypes::get_UserLogonName()
0xf0a8  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimCollectionExtensions::GetSingleClaim(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection, string)
0xf0ad  stloc.0
0xf0ae  ldloc.0
0xf0af  brtrue.s loc_F0ED
0xf0b1  ldc.i4   0x11A4C5
0xf0b6  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xf0bb  ldc.i4.s 0x64
0xf0bd  ldstr    aAddingTheUserl_0// "Adding the UserLogonName claim that is "...
0xf0c2  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xf0c7  ldarg.3
0xf0c8  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0xf0cd  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimTypes::get_UserLogonName()
0xf0d2  ldarg.2
0xf0d3  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0xf0d8  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimValueTypes::get_String()
0xf0dd  ldstr    aSharepoint// "SharePoint"
0xf0e2  ldloc.1
0xf0e3  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::.ctor(string, string, string, string, string)
0xf0e8  callvirt instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection::Add(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim)
0xf0ed  ldloc.2
0xf0ee  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFormsAuthenticationProvider [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPIisSettings::get_FormsClaimsAuthenticationProvider()
0xf0f3  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPFormsAuthenticationProvider::get_RoleProvider()
0xf0f8  stloc.3
0xf0f9  ldloc.3
0xf0fa  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0xf0ff  brtrue   loc_F1E7
0xf104  call     class [System.Web]System.Web.Security.RoleProviderCollection [System.Web]System.Web.Security.Roles::get_Providers()
0xf109  ldloc.3
0xf10a  callvirt instance class [System.Web.ApplicationServices]System.Web.Security.RoleProvider [System.Web]System.Web.Security.RoleProviderCollection::get_Item(string)
0xf10f  stloc.s  4
0xf111  ldloc.s  4
0xf113  brfalse  loc_F1BC
0xf118  ldloc.s  4
0xf11a  ldarg.2
0xf11b  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0xf120  callvirt instance string[] [System.Web.ApplicationServices]System.Web.Security.RoleProvider::GetRolesForUser(string)
0xf125  stloc.s  5
0xf127  ldloc.s  5
0xf129  brfalse.s loc_F18C
0xf12b  ldarg.0
0xf12c  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimTypes::get_Role()
0xf131  call     string Microsoft.SharePoint.IdentityModel.SPFormsOriginalIssuerBuilder::CreateOriginalIssuerFromContext(class [System]System.Uri contextUri, string claimType)
0xf136  stloc.s  6
0xf138  ldc.i4   0x11A4C6
0xf13d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xf142  ldc.i4.s 0x64
0xf144  ldstr    aAddingRolesFor// "Adding Roles for the mapped Forms ident"...
0xf149  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xf14e  ldloc.s  5
0xf150  stloc.s  0xC
0xf152  ldc.i4.0
0xf153  stloc.s  0xD
0xf155  br.s     loc_F183
0xf157  ldloc.s  0xC
0xf159  ldloc.s  0xD
0xf15b  ldelem.ref
0xf15c  stloc.s  7
0xf15e  ldarg.3
0xf15f  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0xf164  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimTypes::get_Role()
0xf169  ldloc.s  7
0xf16b  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimValueTypes::get_String()
0xf170  ldnull
0xf171  ldloc.s  6
0xf173  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::.ctor(string, string, string, string, string)
0xf178  callvirt instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection::Add(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim)
0xf17d  ldloc.s  0xD
0xf17f  ldc.i4.1
0xf180  add
0xf181  stloc.s  0xD
0xf183  ldloc.s  0xD
0xf185  ldloc.s  0xC
0xf187  ldlen
0xf188  conv.i4
0xf189  blt.s    loc_F157
0xf18b  ret
0xf18c  ldc.i4   0x11A4C7
0xf191  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xf196  ldc.i4.s 0x14
0xf198  ldstr    aNoRolesWereAdd// "No roles were added for the mapped Form"...
0xf19d  ldc.i4.3
0xf19e  newarr   [mscorlib]System.Object
0xf1a3  stloc.s  0xE
0xf1a5  ldloc.s  0xE
0xf1a7  ldc.i4.0
0xf1a8  ldloc.0
0xf1a9  stelem.ref
0xf1aa  ldloc.s  0xE
0xf1ac  ldc.i4.1
0xf1ad  ldloc.3
0xf1ae  stelem.ref
0xf1af  ldloc.s  0xE
0xf1b1  ldc.i4.2
0xf1b2  ldarg.0
0xf1b3  stelem.ref
0xf1b4  ldloc.s  0xE
0xf1b6  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xf1bb  ret
0xf1bc  ldc.i4   0x11A4C8
0xf1c1  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xf1c6  ldc.i4.s 0x14
0xf1c8  ldstr    aNoRoleProvider// "No role provider found. [RoleProviderNa"...
0xf1cd  ldc.i4.2
0xf1ce  newarr   [mscorlib]System.Object
0xf1d3  stloc.s  0xF
0xf1d5  ldloc.s  0xF
0xf1d7  ldc.i4.0
0xf1d8  ldloc.3
0xf1d9  stelem.ref
0xf1da  ldloc.s  0xF
0xf1dc  ldc.i4.1
0xf1dd  ldarg.0
0xf1de  stelem.ref
0xf1df  ldloc.s  0xF
0xf1e1  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xf1e6  ret
0xf1e7  ldc.i4   0x24C3CD
0xf1ec  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xf1f1  ldc.i4.s 0x14
0xf1f3  ldstr    aNoRoleProvider_0// "No Role provider for forms authenticati"...
0xf1f8  ldc.i4.1
0xf1f9  newarr   [mscorlib]System.Object
0xf1fe  stloc.s  0x10
0xf200  ldloc.s  0x10
0xf202  ldc.i4.0
0xf203  ldarg.0
0xf204  stelem.ref
0xf205  ldloc.s  0x10
0xf207  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xf20c  ret
0xf20d  ldc.i4.s 0x74
0xf20f  ldloc.1
0xf210  call     valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPOriginalIssuerType [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPOriginalIssuers::GetIssuerType(string)
0xf215  bne.un   loc_F2C2
0xf21a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_Local()
0xf21f  stloc.s  8
0xf221  ldloc.1
0xf222  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPOriginalIssuers::GetIssuerIdentifier(string)
0xf227  stloc.s  9
0xf229  ldloc.s  8
0xf22b  ldloc.s  9
0xf22d  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPLoginProviderBase [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::GetLoginProviderByName(string)
0xf232  stloc.s  0xA
0xf234  ldnull
0xf235  ldloc.s  0xA
0xf237  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::op_Inequality(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject, class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject)
0xf23c  brfalse  loc_F2D8
0xf241  ldarg.3
0xf242  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0xf247  ldloc.s  0xA
0xf249  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedClaimTypeInformation [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPLoginProviderBase::get_IdentityClaimTypeInformation()
0xf24e  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedClaimTypeInformation::get_MappedClaimType()
0xf253  call     class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimCollectionExtensions::GetSingleClaim(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection, string)
0xf258  stloc.0
0xf259  ldloc.0
0xf25a  brtrue.s loc_F2D8
0xf25c  ldc.i4   0x11A4C9
0xf261  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xf266  ldc.i4.s 0x64
0xf268  ldstr    aAddingThe0Clai// "Adding the {0} claim that is missing in"...
0xf26d  ldc.i4.1
0xf26e  newarr   [mscorlib]System.Object
0xf273  stloc.s  0x11
0xf275  ldloc.s  0x11
0xf277  ldc.i4.0
0xf278  ldloc.s  0xA
0xf27a  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedClaimTypeInformation [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPLoginProviderBase::get_IdentityClaimTypeInformation()
0xf27f  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedClaimTypeInformation::get_MappedClaimType()
0xf284  stelem.ref
0xf285  ldloc.s  0x11
0xf287  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xf28c  ldarg.3
0xf28d  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.IClaimsIdentity::get_Claims()
0xf292  ldloc.s  0xA
0xf294  callvirt instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedClaimTypeInformation [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPLoginProviderBase::get_IdentityClaimTypeInformation()
0xf299  callvirt instance string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPTrustedClaimTypeInformation::get_MappedClaimType()
0xf29e  ldarg.2
0xf29f  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::get_Value()
0xf2a4  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPClaimValueTypes::get_String()
0xf2a9  ldstr    aSharepoint// "SharePoint"
0xf2ae  ldc.i4.s 0x74
0xf2b0  ldloc.s  9
0xf2b2  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPOriginalIssuers::Format(valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPOriginalIssuerType, string)
0xf2b7  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim::.ctor(string, string, string, string, string)
0xf2bc  callvirt instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimCollection::Add(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.Claim)
0xf2c1  ret
0xf2c2  ldc.i4   0x11A4CA
0xf2c7  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0xf2cc  ldc.i4.s 0x14
0xf2ce  ldstr    aCouldNotAddThe// "Could not add the original user logon c"...
0xf2d3  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0xf2d8  ret
```
