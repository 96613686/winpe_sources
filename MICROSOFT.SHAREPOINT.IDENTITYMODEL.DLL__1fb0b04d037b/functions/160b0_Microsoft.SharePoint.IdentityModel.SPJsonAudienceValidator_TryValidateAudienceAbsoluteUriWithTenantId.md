# Microsoft.SharePoint.IdentityModel.SPJsonAudienceValidator::TryValidateAudienceAbsoluteUriWithTenantId

- ea: `0x160b0`
- end: `0x161cb`
- name: `Microsoft.SharePoint.IdentityModel.SPJsonAudienceValidator::TryValidateAudienceAbsoluteUriWithTenantId`
- size: `283`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x162c0`
- `0x16770`

## callees

- `0x8940`
- `0x8f60`
- `0x97a0`
- `0x97c0`
- `0x160b0`

## string_xrefs

- `0x1611c`: `The AudienceUri is null.`
- `0x160f1`: `The ValidationMode is not set to include absolute uri.`
- `0x161a6`: `Exception validating absolute audience URI. Audience: '{0}', Exception: '{1}'.`
- `0x16171`: `The AudienceUri and TenantID are NOT valid.`
- `0x1618b`: `The AudienceUri and TenantID are valid.`

## pseudocode

```c

```

## disassembly

```asm
0x160b0  ldarg.1
0x160b1  brtrue.s loc_160CB
0x160b3  ldc.i4   0x80931F
0x160b8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x160bd  ldc.i4.s 0xA
0x160bf  ldstr    aTheValidationp// "The validationParams is null."
0x160c4  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x160c9  ldc.i4.0
0x160ca  ret
0x160cb  ldc.i4.0
0x160cc  stloc.0
0x160cd  ldarg.0
0x160ce  call     instance valuetype Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode Microsoft.SharePoint.IdentityModel.SPAudienceValidator::get_ValidationMode()
0x160d3  box      Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode
0x160d8  ldc.i4.8
0x160d9  box      Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode
0x160de  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x160e3  brtrue.s loc_16102
0x160e5  ldc.i4   0x809320
0x160ea  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x160ef  ldc.i4.s 0xA
0x160f1  ldstr    aTheValidationm_1// "The ValidationMode is not set to includ"...
0x160f6  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x160fb  ldc.i4.0
0x160fc  stloc.0
0x160fd  br       loc_16197
0x16102  ldnull
0x16103  ldarg.1
0x16104  callvirt instance class [System]System.Uri Microsoft.SharePoint.IdentityModel.SPAudienceValidationParameters::get_AudienceUri()
0x16109  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x1610e  brfalse.s loc_1612A
0x16110  ldc.i4   0x809321
0x16115  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x1611a  ldc.i4.s 0xA
0x1611c  ldstr    aTheAudienceuri_2// "The AudienceUri is null."
0x16121  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x16126  ldc.i4.0
0x16127  stloc.0
0x16128  br.s     loc_16197
0x1612a  ldarg.1
0x1612b  callvirt instance string Microsoft.SharePoint.IdentityModel.SPAudienceValidationParameters::get_TenantId()
0x16130  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x16135  brfalse.s loc_16151
0x16137  ldc.i4   0x809322
0x1613c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x16141  ldc.i4.s 0xA
0x16143  ldstr    aTheTenantidIsN// "The TenantId is null or empty."
0x16148  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1614d  ldc.i4.0
0x1614e  stloc.0
0x1614f  br.s     loc_16197
0x16151  ldarg.0
0x16152  ldarg.1
0x16153  callvirt instance class [System]System.Uri Microsoft.SharePoint.IdentityModel.SPAudienceValidationParameters::get_AudienceUri()
0x16158  ldarg.1
0x16159  callvirt instance string Microsoft.SharePoint.IdentityModel.SPAudienceValidationParameters::get_TenantId()
0x1615e  call     instance bool Microsoft.SharePoint.IdentityModel.SPAudienceValidator::ValidateAudienceMatchesCurrentRequest(class [System]System.Uri audienceUri, string audienceTenantId)
0x16163  brtrue.s loc_1617F
0x16165  ldc.i4   0x809323
0x1616a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x1616f  ldc.i4.s 0x32
0x16171  ldstr    aTheAudienceuri_3// "The AudienceUri and TenantID are NOT va"...
0x16176  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1617b  ldc.i4.0
0x1617c  stloc.0
0x1617d  br.s     loc_16197
0x1617f  ldc.i4   0x809340
0x16184  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x16189  ldc.i4.s 0x32
0x1618b  ldstr    aTheAudienceuri_4// "The AudienceUri and TenantID are valid."
0x16190  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x16195  ldc.i4.1
0x16196  stloc.0
0x16197  leave.s  loc_161C9
0x16199  stloc.1
0x1619a  ldc.i4   0x809341
0x1619f  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x161a4  ldc.i4.s 0xA
0x161a6  ldstr    aExceptionValid_2// "Exception validating absolute audience "...
0x161ab  ldc.i4.2
0x161ac  newarr   [mscorlib]System.Object
0x161b1  stloc.2
0x161b2  ldloc.2
0x161b3  ldc.i4.0
0x161b4  ldarg.1
0x161b5  callvirt instance class [System]System.Uri Microsoft.SharePoint.IdentityModel.SPAudienceValidationParameters::get_AudienceUri()
0x161ba  stelem.ref
0x161bb  ldloc.2
0x161bc  ldc.i4.1
0x161bd  ldloc.1
0x161be  stelem.ref
0x161bf  ldloc.2
0x161c0  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x161c5  ldc.i4.0
0x161c6  stloc.0
0x161c7  leave.s  loc_161C9
0x161c9  ldloc.0
0x161ca  ret
```
