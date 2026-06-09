# Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::IsTrustedForDelegation

- ea: `0x17890`
- end: `0x17993`
- name: `Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::IsTrustedForDelegation`
- size: `259`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x17580`
- `0x1a1f0`

## callees

- `0x169c0`
- `0x17890`
- `0x1bf90`

## string_xrefs

- `0x178f5`: `IsTrustedForDelegation: Well Known app {0} trusted for delegation with Evo Token.`
- `0x1791e`: `IsTrustedForDelegation: It's not Well Known app {0} trusted for delegation with Evo Token.`
- `0x1796e`: `trustedForImpersonation`

## pseudocode

```c

```

## disassembly

```asm
0x17890  ldarg.0
0x17891  brtrue.s loc_178B4
0x17893  ldc.i4   0x650408
0x17898  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x1789d  ldc.i4.s 0xA
0x1789f  ldstr    aTheIdentityIsN// "The identity is null."
0x178a4  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x178a9  ldstr    aIdentity// "identity"
0x178ae  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x178b3  throw
0x178b4  ldc.i4   0x2890
0x178b9  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Flighting.Runtime.VariantConfiguration::IsGlobalExpFeatureToggleEnabled(valuetype [Microsoft.SharePoint.Flighting]Microsoft.SharePoint.Flighting.ExpFeatureId)
0x178be  brfalse  loc_17954
0x178c3  ldarg.0
0x178c4  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Claims()
0x178c9  ldstr    aAppid// "appid"
0x178ce  call     class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenExtensions::GetSingleClaim(class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> self, string claimType)
0x178d3  stloc.0
0x178d4  ldloc.0
0x178d5  brfalse.s loc_1793E
0x178d7  ldsfld   string[] [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPServerToServerProtocolConstants::WellKnwonAppsTrustedForDelegation
0x178dc  ldloc.0
0x178dd  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_Value()
0x178e2  call     T0x2B000018
0x178e7  brfalse.s loc_17912
0x178e9  ldc.i4   0x72339C
0x178ee  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x178f3  ldc.i4.s 0x32
0x178f5  ldstr    aIstrustedforde// "IsTrustedForDelegation: Well Known app "...
0x178fa  ldc.i4.1
0x178fb  newarr   [mscorlib]System.Object
0x17900  stloc.3
0x17901  ldloc.3
0x17902  ldc.i4.0
0x17903  ldloc.0
0x17904  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_Value()
0x17909  stelem.ref
0x1790a  ldloc.3
0x1790b  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x17910  ldc.i4.1
0x17911  ret
0x17912  ldc.i4   0x72339D
0x17917  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x1791c  ldc.i4.s 0x64
0x1791e  ldstr    aIstrustedforde_0// "IsTrustedForDelegation: It's not Well K"...
0x17923  ldc.i4.1
0x17924  newarr   [mscorlib]System.Object
0x17929  stloc.s  4
0x1792b  ldloc.s  4
0x1792d  ldc.i4.0
0x1792e  ldloc.0
0x1792f  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_Value()
0x17934  stelem.ref
0x17935  ldloc.s  4
0x17937  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1793c  br.s     loc_17954
0x1793e  ldc.i4   0x72339E
0x17943  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x17948  ldc.i4.s 0x64
0x1794a  ldstr    aIstrustedforde_1// "IsTrustedForDelegation: AppId Claim typ"...
0x1794f  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x17954  ldarg.0
0x17955  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Claims()
0x1795a  ldstr    aTrustedfordele// "trustedfordelegation"
0x1795f  call     class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenExtensions::GetSingleClaim(class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> self, string claimType)
0x17964  stloc.1
0x17965  ldloc.1
0x17966  brtrue.s loc_1797E
0x17968  ldarg.0
0x17969  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Claims()
0x1796e  ldstr    aTrustedforimpe// "trustedForImpersonation"
0x17973  call     class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenExtensions::GetSingleClaim(class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> self, string claimType)
0x17978  stloc.1
0x17979  ldloc.1
0x1797a  brtrue.s loc_1797E
0x1797c  ldc.i4.0
0x1797d  ret
0x1797e  ldc.i4.0
0x1797f  stloc.2
0x17980  ldloc.1
0x17981  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_Value()
0x17986  ldloca.s 2
0x17988  call     bool [mscorlib]System.Boolean::TryParse(string, bool&)
0x1798d  brtrue.s loc_17991
0x1798f  ldc.i4.0
0x17990  ret
0x17991  ldloc.2
0x17992  ret
```
