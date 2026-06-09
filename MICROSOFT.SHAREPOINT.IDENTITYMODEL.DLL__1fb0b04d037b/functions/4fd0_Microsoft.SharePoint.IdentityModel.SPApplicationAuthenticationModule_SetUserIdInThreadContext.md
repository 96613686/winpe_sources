# Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::SetUserIdInThreadContext

- ea: `0x4fd0`
- end: `0x5095`
- name: `Microsoft.SharePoint.IdentityModel.SPApplicationAuthenticationModule::SetUserIdInThreadContext`
- size: `197`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x4940`

## callees

- `0x4fd0`
- `0x28920`

## string_xrefs

- `0x4fdd`: `guestusertoken`
- `0x5011`: `SPApplicationAuthenticationModule User doesn't have 'guestusertoken' claim`
- `0x5036`: `SPApplicationAuthenticationModule Setting Thread Context for guest user:{0}`
- `0x504f`: `SPApplicationAuthenticationModule Setting Thread Context Property for guest user`

## pseudocode

```c

```

## disassembly

```asm
0x4fd0  ldarg.2
0x4fd1  ldstr    aNameid// "nameid"
0x4fd6  call     class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim Microsoft.SharePoint.IdentityModel.SPClaimsUtility::GetSingleClaim(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken token, string claimType)
0x4fdb  stloc.0
0x4fdc  ldarg.2
0x4fdd  ldstr    aGuestusertoken// "guestusertoken"
0x4fe2  call     class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim Microsoft.SharePoint.IdentityModel.SPClaimsUtility::GetSingleClaim(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken token, string claimType)
0x4fe7  stloc.1
0x4fe8  ldloc.0
0x4fe9  brtrue.s loc_5002
0x4feb  ldc.i4   0x19A38E
0x4ff0  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x4ff5  ldc.i4.s 0x32
0x4ff7  ldstr    aSpapplicationa_72// "SPApplicationAuthenticationModule User "...
0x4ffc  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x5001  ret
0x5002  ldloc.1
0x5003  brtrue.s loc_501C
0x5005  ldc.i4   0x19A38F
0x500a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x500f  ldc.i4.s 0x32
0x5011  ldstr    aSpapplicationa_73// "SPApplicationAuthenticationModule User "...
0x5016  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x501b  ret
0x501c  ldloc.0
0x501d  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_Value()
0x5022  stloc.2
0x5023  ldloc.1
0x5024  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebTokenClaim::get_Value()
0x5029  stloc.3
0x502a  ldc.i4   0x19A390
0x502f  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ApplicationAuthentication()
0x5034  ldc.i4.s 0x32
0x5036  ldstr    aSpapplicationa_74// "SPApplicationAuthenticationModule Setti"...
0x503b  ldc.i4.1
0x503c  newarr   [mscorlib]System.Object
0x5041  stloc.s  5
0x5043  ldloc.s  5
0x5045  ldc.i4.0
0x5046  ldloc.2
0x5047  stelem.ref
0x5048  ldloc.s  5
0x504a  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x504f  ldstr    aSpapplicationa_75// "SPApplicationAuthenticationModule Setti"...
0x5054  ldc.i4.s 0x32
0x5056  ldc.i4.0
0x5057  newarr   [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor
0x505c  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.TraceSeverity, class [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.ISPScopedPerformanceMonitor[])
0x5061  stloc.s  6
0x5063  ldloc.2
0x5064  ldloc.3
0x5065  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPGuestUserContext::.ctor(string, string)
0x506a  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPGuestUserContextProperty::.ctor(class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPGuestUserContext)
0x506f  stloc.s  4
0x5071  ldloc.s  4
0x5073  call     T0x2B00000D
0x5078  ldarg.1
0x5079  ldnull
0x507a  call     void [Microsoft.SharePoint]Microsoft.SharePoint.WebControls.SPControl::SetContextWeb(class [System.Web]System.Web.HttpContext, class [Microsoft.SharePoint]Microsoft.SharePoint.SPWeb)
0x507f  ldarg.1
0x5080  ldnull
0x5081  call     void [Microsoft.SharePoint]Microsoft.SharePoint.WebControls.SPControl::SetContextSite(class [System.Web]System.Web.HttpContext, class [Microsoft.SharePoint]Microsoft.SharePoint.SPSite)
0x5086  leave.s  loc_5094
0x5088  ldloc.s  6
0x508a  brfalse.s loc_5093
0x508c  ldloc.s  6
0x508e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5093  endfinally
0x5094  ret
```
