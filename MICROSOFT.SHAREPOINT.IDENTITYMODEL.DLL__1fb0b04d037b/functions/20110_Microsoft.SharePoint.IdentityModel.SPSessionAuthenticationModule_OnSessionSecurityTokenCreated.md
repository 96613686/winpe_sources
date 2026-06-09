# Microsoft.SharePoint.IdentityModel.SPSessionAuthenticationModule::OnSessionSecurityTokenCreated

- ea: `0x20110`
- end: `0x20161`
- name: `Microsoft.SharePoint.IdentityModel.SPSessionAuthenticationModule::OnSessionSecurityTokenCreated`
- size: `81`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x20110`

## string_xrefs

- `0x2011f`: `SPSam.OnSessionSecurityTokenCreated: Start`
- `0x20129`: `SPSam.OnSessionSecurityTokenCreated::WifCodeCall`
- `0x20156`: `SPSam.OnSessionSecurityTokenCreated: End`

## pseudocode

```c

```

## disassembly

```asm
0x20110  ldc.i4   0x20F859
0x20115  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x2011a  ldc.i4   0xC8
0x2011f  ldstr    aSpsamOnsession// "SPSam.OnSessionSecurityTokenCreated: St"...
0x20124  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x20129  ldstr    aSpsamOnsession_0// "SPSam.OnSessionSecurityTokenCreated::Wi"...
0x2012e  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPMonitoredScope::.ctor(string)
0x20133  stloc.0
0x20134  ldarg.0
0x20135  ldarg.1
0x20136  call     instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.SessionAuthenticationModule::OnSessionSecurityTokenCreated(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Web.SessionSecurityTokenCreatedEventArgs)
0x2013b  leave.s  loc_20147
0x2013d  ldloc.0
0x2013e  brfalse.s loc_20146
0x20140  ldloc.0
0x20141  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x20146  endfinally
0x20147  ldc.i4   0x20F85A
0x2014c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x20151  ldc.i4   0xC8
0x20156  ldstr    aSpsamOnsession_1// "SPSam.OnSessionSecurityTokenCreated: En"...
0x2015b  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x20160  ret
```
