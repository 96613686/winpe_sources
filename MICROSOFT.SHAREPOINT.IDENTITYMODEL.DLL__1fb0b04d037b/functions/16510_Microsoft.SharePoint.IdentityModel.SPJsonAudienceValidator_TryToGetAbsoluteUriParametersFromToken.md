# Microsoft.SharePoint.IdentityModel.SPJsonAudienceValidator::TryToGetAbsoluteUriParametersFromToken

- ea: `0x16510`
- end: `0x165b5`
- name: `Microsoft.SharePoint.IdentityModel.SPJsonAudienceValidator::TryToGetAbsoluteUriParametersFromToken`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x16770`

## callees

- `0x97b0`
- `0x98c0`
- `0x16510`

## string_xrefs

- `0x1651f`: `The token is null.`
- `0x16551`: `The token audience is not an absolute URI.`
- `0x1657d`: `The token has an absolute audience uri.`

## pseudocode

```c

```

## disassembly

```asm
0x16510  ldarg.1
0x16511  brtrue.s loc_1652E
0x16513  ldc.i4   0x121140E
0x16518  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x1651d  ldc.i4.s 0xA
0x1651f  ldstr    aTheTokenIsNull// "The token is null."
0x16524  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x16529  ldarg.2
0x1652a  ldnull
0x1652b  stind.ref
0x1652c  ldc.i4.0
0x1652d  ret
0x1652e  ldc.i4.0
0x1652f  stloc.0
0x16530  ldarg.2
0x16531  ldnull
0x16532  stind.ref
0x16533  ldnull
0x16534  stloc.1
0x16535  ldarg.1
0x16536  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Audience()
0x1653b  ldc.i4.1
0x1653c  ldloca.s 1
0x1653e  call     bool [System]System.Uri::TryCreate(string, valuetype [System]System.UriKind, class [System]System.Uri&)
0x16543  brtrue.s loc_1655F
0x16545  ldc.i4   0x121140F
0x1654a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x1654f  ldc.i4.s 0x32
0x16551  ldstr    aTheTokenAudien_0// "The token audience is not an absolute U"...
0x16556  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1655b  ldc.i4.0
0x1655c  stloc.0
0x1655d  br.s     loc_16587
0x1655f  ldarg.2
0x16560  newobj   instance void Microsoft.SharePoint.IdentityModel.SPAudienceValidationParameters::.ctor()
0x16565  stloc.2
0x16566  ldloc.2
0x16567  ldloc.1
0x16568  callvirt instance void Microsoft.SharePoint.IdentityModel.SPAudienceValidationParameters::set_AudienceUri(class [System]System.Uri value)
0x1656d  ldloc.2
0x1656e  stind.ref
0x1656f  ldc.i4.1
0x16570  stloc.0
0x16571  ldc.i4   0x1211410
0x16576  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x1657b  ldc.i4.s 0x64
0x1657d  ldstr    aTheTokenHasAnA// "The token has an absolute audience uri."
0x16582  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x16587  leave.s  loc_165B3
0x16589  stloc.3
0x1658a  ldc.i4   0x1211411
0x1658f  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x16594  ldc.i4.s 0xA
0x16596  ldstr    aExceptionBuild// "Exception building audience paramters. "...
0x1659b  ldc.i4.1
0x1659c  newarr   [mscorlib]System.Object
0x165a1  stloc.s  4
0x165a3  ldloc.s  4
0x165a5  ldc.i4.0
0x165a6  ldloc.3
0x165a7  stelem.ref
0x165a8  ldloc.s  4
0x165aa  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x165af  ldc.i4.0
0x165b0  stloc.0
0x165b1  leave.s  loc_165B3
0x165b3  ldloc.0
0x165b4  ret
```
