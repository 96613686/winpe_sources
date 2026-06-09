# Microsoft.SharePoint.IdentityModel.SPSessionAuthenticationModule::SetPrincipalFromSessionToken

- ea: `0x20410`
- end: `0x20461`
- name: `Microsoft.SharePoint.IdentityModel.SPSessionAuthenticationModule::SetPrincipalFromSessionToken`
- size: `81`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x20410`

## string_xrefs

- `0x2041f`: `SPSam.SetPrincipalFromSessionToken: Start`
- `0x20429`: `SPSam.SetPrincipalFromSessionToken::WifCodeCall`
- `0x20456`: `SPSam.SetPrincipalFromSessionToken: End`

## pseudocode

```c

```

## disassembly

```asm
0x20410  ldc.i4   0x20F881
0x20415  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x2041a  ldc.i4   0xC8
0x2041f  ldstr    aSpsamSetprinci// "SPSam.SetPrincipalFromSessionToken: Sta"...
0x20424  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x20429  ldstr    aSpsamSetprinci_0// "SPSam.SetPrincipalFromSessionToken::Wif"...
0x2042e  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string)
0x20433  stloc.0
0x20434  ldarg.0
0x20435  ldarg.1
0x20436  call     instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.SessionAuthenticationModule::SetPrincipalFromSessionToken(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SessionSecurityToken)
0x2043b  leave.s  loc_20447
0x2043d  ldloc.0
0x2043e  brfalse.s loc_20446
0x20440  ldloc.0
0x20441  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20446  endfinally
0x20447  ldc.i4   0x20F882
0x2044c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x20451  ldc.i4   0xC8
0x20456  ldstr    aSpsamSetprinci_1// "SPSam.SetPrincipalFromSessionToken: End"
0x2045b  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x20460  ret
```
