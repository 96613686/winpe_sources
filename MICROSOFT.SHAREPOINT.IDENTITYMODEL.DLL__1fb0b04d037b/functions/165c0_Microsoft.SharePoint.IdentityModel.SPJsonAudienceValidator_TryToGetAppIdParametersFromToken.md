# Microsoft.SharePoint.IdentityModel.SPJsonAudienceValidator::TryToGetAppIdParametersFromToken

- ea: `0x165c0`
- end: `0x1666e`
- name: `Microsoft.SharePoint.IdentityModel.SPJsonAudienceValidator::TryToGetAppIdParametersFromToken`
- size: `174`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x16770`

## callees

- `0x97f0`
- `0x98c0`
- `0x165c0`

## string_xrefs

- `0x165cf`: `The token is null.`
- `0x165fe`: `The token audience is not a GUID.`
- `0x16636`: `The token has a GUID audience.`

## pseudocode

```c

```

## disassembly

```asm
0x165c0  ldarg.1
0x165c1  brtrue.s loc_165DE
0x165c3  ldc.i4   0x1211412
0x165c8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x165cd  ldc.i4.s 0xA
0x165cf  ldstr    aTheTokenIsNull// "The token is null."
0x165d4  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x165d9  ldarg.2
0x165da  ldnull
0x165db  stind.ref
0x165dc  ldc.i4.0
0x165dd  ret
0x165de  ldc.i4.0
0x165df  stloc.0
0x165e0  ldarg.2
0x165e1  ldnull
0x165e2  stind.ref
0x165e3  ldarg.1
0x165e4  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Audience()
0x165e9  ldloca.s 1
0x165eb  call     bool [mscorlib]System.Guid::TryParse(string, valuetype [mscorlib]System.Guid&)
0x165f0  brtrue.s loc_1660C
0x165f2  ldc.i4   0x1211413
0x165f7  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x165fc  ldc.i4.s 0x32
0x165fe  ldstr    aTheTokenAudien_1// "The token audience is not a GUID."
0x16603  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x16608  ldc.i4.0
0x16609  stloc.0
0x1660a  br.s     loc_16640
0x1660c  ldarg.2
0x1660d  newobj   instance void Microsoft.SharePoint.IdentityModel.SPAudienceValidationParameters::.ctor()
0x16612  stloc.2
0x16613  ldloc.2
0x16614  ldloca.s 1
0x16616  constrained. [mscorlib]System.Guid
0x1661c  callvirt instance string [mscorlib]System.Object::ToString()
0x16621  callvirt instance void Microsoft.SharePoint.IdentityModel.SPAudienceValidationParameters::set_ApplicationId(string value)
0x16626  ldloc.2
0x16627  stind.ref
0x16628  ldc.i4.1
0x16629  stloc.0
0x1662a  ldc.i4   0x1211414
0x1662f  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x16634  ldc.i4.s 0x64
0x16636  ldstr    aTheTokenHasAGu// "The token has a GUID audience."
0x1663b  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x16640  leave.s  loc_1666C
0x16642  stloc.3
0x16643  ldc.i4   0x1211415
0x16648  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x1664d  ldc.i4.s 0xA
0x1664f  ldstr    aExceptionBuild// "Exception building audience paramters. "...
0x16654  ldc.i4.1
0x16655  newarr   [mscorlib]System.Object
0x1665a  stloc.s  4
0x1665c  ldloc.s  4
0x1665e  ldc.i4.0
0x1665f  ldloc.3
0x16660  stelem.ref
0x16661  ldloc.s  4
0x16663  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x16668  ldc.i4.0
0x16669  stloc.0
0x1666a  leave.s  loc_1666C
0x1666c  ldloc.0
0x1666d  ret
```
