# Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenExtensions::LogDump

- ea: `0x1c000`
- end: `0x1c141`
- name: `Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenExtensions::LogDump`
- size: `321`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x5b90`
- `0x1c000`

## callees

- `0x1c000`

## string_xrefs

- `0x1c00f`: `Dumping Security Token`
- `0x1c02e`: `SPSecurityTokenExtensions: Audience:{0}.`
- `0x1c055`: `SPSecurityTokenExtensions: Not Valid Before:{0}, Valid To:{1}.`
- `0x1c0a1`: `SPSecurityTokenExtensions: Issuer:{0}.`
- `0x1c0e2`: `SPSecurityTokenExtensions: Claim['{0}':'{1}'].`

## pseudocode

```c

```

## disassembly

```asm
0x1c000  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x1c005  ldc.i4.s 0x64
0x1c007  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::ShouldTrace(class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel)
0x1c00c  brtrue.s loc_1C00F
0x1c00e  ret
0x1c00f  ldstr    aDumpingSecurit// "Dumping Security Token"
0x1c014  ldc.i4.s 0x64
0x1c016  ldc.i4.0
0x1c017  newarr   [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x1c01c  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.TraceSeverity, class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[])
0x1c021  stloc.1
0x1c022  ldc.i4   0x199543
0x1c027  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x1c02c  ldc.i4.s 0x64
0x1c02e  ldstr    aSpsecuritytoke// "SPSecurityTokenExtensions: Audience:{0}"...
0x1c033  ldc.i4.1
0x1c034  newarr   [mscorlib]System.Object
0x1c039  stloc.2
0x1c03a  ldloc.2
0x1c03b  ldc.i4.0
0x1c03c  ldarg.0
0x1c03d  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Audience()
0x1c042  stelem.ref
0x1c043  ldloc.2
0x1c044  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1c049  ldc.i4   0x199544
0x1c04e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x1c053  ldc.i4.s 0x64
0x1c055  ldstr    aSpsecuritytoke_0// "SPSecurityTokenExtensions: Not Valid Be"...
0x1c05a  ldc.i4.2
0x1c05b  newarr   [mscorlib]System.Object
0x1c060  stloc.3
0x1c061  ldloc.3
0x1c062  ldc.i4.0
0x1c063  ldarg.0
0x1c064  callvirt instance valuetype [mscorlib]System.DateTime [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_ValidFrom()
0x1c069  stloc.s  4
0x1c06b  ldloca.s 4
0x1c06d  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::ToUniversalTime()
0x1c072  box      [mscorlib]System.DateTime
0x1c077  stelem.ref
0x1c078  ldloc.3
0x1c079  ldc.i4.1
0x1c07a  ldarg.0
0x1c07b  callvirt instance valuetype [mscorlib]System.DateTime [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken::get_ValidTo()
0x1c080  stloc.s  5
0x1c082  ldloca.s 5
0x1c084  call     instance valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::ToUniversalTime()
0x1c089  box      [mscorlib]System.DateTime
0x1c08e  stelem.ref
0x1c08f  ldloc.3
0x1c090  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1c095  ldc.i4   0x199545
0x1c09a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x1c09f  ldc.i4.s 0x64
0x1c0a1  ldstr    aSpsecuritytoke_1// "SPSecurityTokenExtensions: Issuer:{0}."
0x1c0a6  ldc.i4.1
0x1c0a7  newarr   [mscorlib]System.Object
0x1c0ac  stloc.s  6
0x1c0ae  ldloc.s  6
0x1c0b0  ldc.i4.0
0x1c0b1  ldarg.0
0x1c0b2  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Issuer()
0x1c0b7  stelem.ref
0x1c0b8  ldloc.s  6
0x1c0ba  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1c0bf  ldarg.0
0x1c0c0  callvirt instance class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim> [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Claims()
0x1c0c5  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.ObjectModel.ReadOnlyCollection`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim>::GetEnumerator()
0x1c0ca  stloc.s  7
0x1c0cc  br.s     loc_1C10A
0x1c0ce  ldloc.s  7
0x1c0d0  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim>::get_Current()
0x1c0d5  stloc.0
0x1c0d6  ldc.i4   0x199546
0x1c0db  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x1c0e0  ldc.i4.s 0x64
0x1c0e2  ldstr    aSpsecuritytoke_2// "SPSecurityTokenExtensions: Claim['{0}':"...
0x1c0e7  ldc.i4.2
0x1c0e8  newarr   [mscorlib]System.Object
0x1c0ed  stloc.s  8
0x1c0ef  ldloc.s  8
0x1c0f1  ldc.i4.0
0x1c0f2  ldloc.0
0x1c0f3  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_ClaimType()
0x1c0f8  stelem.ref
0x1c0f9  ldloc.s  8
0x1c0fb  ldc.i4.1
0x1c0fc  ldloc.0
0x1c0fd  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_Value()
0x1c102  stelem.ref
0x1c103  ldloc.s  8
0x1c105  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1c10a  ldloc.s  7
0x1c10c  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x1c111  brtrue.s loc_1C0CE
0x1c113  leave.s  loc_1C121
0x1c115  ldloc.s  7
0x1c117  brfalse.s loc_1C120
0x1c119  ldloc.s  7
0x1c11b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1c120  endfinally
0x1c121  ldarg.0
0x1c122  callvirt instance class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_ActorToken()
0x1c127  brfalse.s loc_1C134
0x1c129  ldarg.0
0x1c12a  callvirt instance class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_ActorToken()
0x1c12f  call     void Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenExtensions::LogDump(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken self)
0x1c134  leave.s  loc_1C140
0x1c136  ldloc.1
0x1c137  brfalse.s loc_1C13F
0x1c139  ldloc.1
0x1c13a  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1c13f  endfinally
0x1c140  ret
```
