# Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::IsAppOnlyWopiToken

- ea: `0x15090`
- end: `0x15107`
- name: `Microsoft.SharePoint.IdentityModel.SPIncomingTokenContext::IsAppOnlyWopiToken`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x16b90`

## callees

- `0x15090`
- `0x28110`

## string_xrefs

- `0x150a9`: `token`
- `0x150c0`: `WopiAppOnlyTokenFeature`
- `0x1509f`: `token is null.`
- `0x150df`: `IsAppOnlyWopiToken: wopitokentype: {0}`

## pseudocode

```c

```

## disassembly

```asm
0x15090  ldarg.0
0x15091  brtrue.s loc_150B4
0x15093  ldc.i4   0x12487DB
0x15098  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x1509d  ldc.i4.s 0x14
0x1509f  ldstr    aTokenIsNull// "token is null."
0x150a4  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x150a9  ldstr    aToken// "token"
0x150ae  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x150b3  throw
0x150b4  ldc.i4.0
0x150b5  stloc.0
0x150b6  ldsfld   valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPWOPIHost::WopiAppOnlyTokenFeature
0x150bb  ldstr    a05102016// "05/10/2016"
0x150c0  ldstr    aWopiapponlytok// "WopiAppOnlyTokenFeature"
0x150c5  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.Internal.SPKillSwitch::IsActivated(valuetype [mscorlib]System.Guid, string, string)
0x150ca  brtrue.s loc_15105
0x150cc  ldarg.0
0x150cd  call     valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WopiTokenType Microsoft.SharePoint.IdentityModel.SPClaimsUtility::GetWopiTokenType(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken token)
0x150d2  stloc.1
0x150d3  ldc.i4   0x12487DC
0x150d8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_ClaimsAuthentication()
0x150dd  ldc.i4.s 0x32
0x150df  ldstr    aIsapponlywopit// "IsAppOnlyWopiToken: wopitokentype: {0}"
0x150e4  ldc.i4.1
0x150e5  newarr   [mscorlib]System.Object
0x150ea  stloc.2
0x150eb  ldloc.2
0x150ec  ldc.i4.0
0x150ed  ldloc.1
0x150ee  box      [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.WopiTokenType
0x150f3  callvirt instance string [mscorlib]System.Object::ToString()
0x150f8  stelem.ref
0x150f9  ldloc.2
0x150fa  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x150ff  ldloc.1
0x15100  ldc.i4.3
0x15101  bne.un.s loc_15105
0x15103  ldc.i4.1
0x15104  stloc.0
0x15105  ldloc.0
0x15106  ret
```
