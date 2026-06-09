# Microsoft.SharePoint.IdentityModel.SPJsonAudienceValidator::TryValidateAudienceProofToken

- ea: `0x161d0`
- end: `0x162c0`
- name: `Microsoft.SharePoint.IdentityModel.SPJsonAudienceValidator::TryValidateAudienceProofToken`
- size: `240`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x162c0`

## callees

- `0x8940`
- `0x9180`
- `0x97a0`
- `0x161d0`

## string_xrefs

- `0x16239`: `The AudienceUri is null.`
- `0x16211`: `The ValidationMode is not set to include absolute uri.`
- `0x1629b`: `Exception validating absolute audience URI. Audience: '{0}', Exception: '{1}'.`
- `0x16266`: `The proof token audience is NOT valid.`
- `0x16280`: `The proof token audience is valid.`

## pseudocode

```c

```

## disassembly

```asm
0x161d0  ldarg.1
0x161d1  brtrue.s loc_161EB
0x161d3  ldc.i4   0x809342
0x161d8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x161dd  ldc.i4.s 0xA
0x161df  ldstr    aTheValidationp// "The validationParams is null."
0x161e4  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x161e9  ldc.i4.0
0x161ea  ret
0x161eb  ldc.i4.0
0x161ec  stloc.0
0x161ed  ldarg.0
0x161ee  call     instance valuetype Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode Microsoft.SharePoint.IdentityModel.SPAudienceValidator::get_ValidationMode()
0x161f3  box      Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode
0x161f8  ldc.i4.4
0x161f9  box      Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode
0x161fe  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x16203  brtrue.s loc_1621F
0x16205  ldc.i4   0x809343
0x1620a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x1620f  ldc.i4.s 0xA
0x16211  ldstr    aTheValidationm_1// "The ValidationMode is not set to includ"...
0x16216  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1621b  ldc.i4.0
0x1621c  stloc.0
0x1621d  br.s     loc_1628C
0x1621f  ldnull
0x16220  ldarg.1
0x16221  callvirt instance class [System]System.Uri Microsoft.SharePoint.IdentityModel.SPAudienceValidationParameters::get_AudienceUri()
0x16226  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x1622b  brfalse.s loc_16247
0x1622d  ldc.i4   0x809344
0x16232  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x16237  ldc.i4.s 0xA
0x16239  ldstr    aTheAudienceuri_2// "The AudienceUri is null."
0x1623e  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x16243  ldc.i4.0
0x16244  stloc.0
0x16245  br.s     loc_1628C
0x16247  ldarg.0
0x16248  ldarg.1
0x16249  callvirt instance class [System]System.Uri Microsoft.SharePoint.IdentityModel.SPAudienceValidationParameters::get_AudienceUri()
0x1624e  callvirt instance string [System]System.Uri::get_OriginalString()
0x16253  call     instance bool Microsoft.SharePoint.IdentityModel.SPAudienceValidator::ValidateAudienceMatchesCurrentRequestWithWildCard(string audienceUri)
0x16258  brtrue.s loc_16274
0x1625a  ldc.i4   0x809345
0x1625f  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x16264  ldc.i4.s 0x32
0x16266  ldstr    aTheProofTokenA// "The proof token audience is NOT valid."
0x1626b  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x16270  ldc.i4.0
0x16271  stloc.0
0x16272  br.s     loc_1628C
0x16274  ldc.i4   0x809346
0x16279  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x1627e  ldc.i4.s 0x32
0x16280  ldstr    aTheProofTokenA_0// "The proof token audience is valid."
0x16285  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1628a  ldc.i4.1
0x1628b  stloc.0
0x1628c  leave.s  loc_162BE
0x1628e  stloc.1
0x1628f  ldc.i4   0x809347
0x16294  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x16299  ldc.i4.s 0xA
0x1629b  ldstr    aExceptionValid_2// "Exception validating absolute audience "...
0x162a0  ldc.i4.2
0x162a1  newarr   [mscorlib]System.Object
0x162a6  stloc.2
0x162a7  ldloc.2
0x162a8  ldc.i4.0
0x162a9  ldarg.1
0x162aa  callvirt instance class [System]System.Uri Microsoft.SharePoint.IdentityModel.SPAudienceValidationParameters::get_AudienceUri()
0x162af  stelem.ref
0x162b0  ldloc.2
0x162b1  ldc.i4.1
0x162b2  ldloc.1
0x162b3  stelem.ref
0x162b4  ldloc.2
0x162b5  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x162ba  ldc.i4.0
0x162bb  stloc.0
0x162bc  leave.s  loc_162BE
0x162be  ldloc.0
0x162bf  ret
```
