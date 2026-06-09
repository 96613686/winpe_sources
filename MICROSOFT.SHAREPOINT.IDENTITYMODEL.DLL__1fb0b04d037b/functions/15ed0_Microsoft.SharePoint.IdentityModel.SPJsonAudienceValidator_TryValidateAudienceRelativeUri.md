# Microsoft.SharePoint.IdentityModel.SPJsonAudienceValidator::TryValidateAudienceRelativeUri

- ea: `0x15ed0`
- end: `0x15fc0`
- name: `Microsoft.SharePoint.IdentityModel.SPJsonAudienceValidator::TryValidateAudienceRelativeUri`
- size: `240`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x162c0`
- `0x16770`

## callees

- `0x8940`
- `0x9240`
- `0x97a0`
- `0x15ed0`

## string_xrefs

- `0x15f11`: `The ValidationMode is not set to include relative uri.`
- `0x15f39`: `The AudienceUri is null.`
- `0x15f66`: `The relative AudienceUri is NOT valid.`
- `0x15f80`: `The relative AudienceUri is valid.`
- `0x15f9b`: `Exception validating relative audience URI. Audience: '{0}', Exception: '{1}'.`

## pseudocode

```c

```

## disassembly

```asm
0x15ed0  ldarg.1
0x15ed1  brtrue.s loc_15EEB
0x15ed3  ldc.i4   0x809313
0x15ed8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x15edd  ldc.i4.s 0xA
0x15edf  ldstr    aTheValidationp// "The validationParams is null."
0x15ee4  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x15ee9  ldc.i4.0
0x15eea  ret
0x15eeb  ldc.i4.0
0x15eec  stloc.0
0x15eed  ldarg.0
0x15eee  call     instance valuetype Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode Microsoft.SharePoint.IdentityModel.SPAudienceValidator::get_ValidationMode()
0x15ef3  box      Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode
0x15ef8  ldc.i4.2
0x15ef9  box      Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode
0x15efe  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x15f03  brtrue.s loc_15F1F
0x15f05  ldc.i4   0x809314
0x15f0a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x15f0f  ldc.i4.s 0xA
0x15f11  ldstr    aTheValidationm_0// "The ValidationMode is not set to includ"...
0x15f16  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x15f1b  ldc.i4.0
0x15f1c  stloc.0
0x15f1d  br.s     loc_15F8C
0x15f1f  ldnull
0x15f20  ldarg.1
0x15f21  callvirt instance class [System]System.Uri Microsoft.SharePoint.IdentityModel.SPAudienceValidationParameters::get_AudienceUri()
0x15f26  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x15f2b  brfalse.s loc_15F47
0x15f2d  ldc.i4   0x809315
0x15f32  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x15f37  ldc.i4.s 0xA
0x15f39  ldstr    aTheAudienceuri_2// "The AudienceUri is null."
0x15f3e  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x15f43  ldc.i4.0
0x15f44  stloc.0
0x15f45  br.s     loc_15F8C
0x15f47  ldarg.0
0x15f48  ldarg.1
0x15f49  callvirt instance class [System]System.Uri Microsoft.SharePoint.IdentityModel.SPAudienceValidationParameters::get_AudienceUri()
0x15f4e  callvirt instance string [System]System.Uri::get_OriginalString()
0x15f53  call     instance bool Microsoft.SharePoint.IdentityModel.SPAudienceValidator::ValidateAudienceMatchesCurrentRequest(string audienceUri)
0x15f58  brtrue.s loc_15F74
0x15f5a  ldc.i4   0x809316
0x15f5f  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x15f64  ldc.i4.s 0x32
0x15f66  ldstr    aTheRelativeAud// "The relative AudienceUri is NOT valid."
0x15f6b  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x15f70  ldc.i4.0
0x15f71  stloc.0
0x15f72  br.s     loc_15F8C
0x15f74  ldc.i4   0x809317
0x15f79  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x15f7e  ldc.i4.s 0x32
0x15f80  ldstr    aTheRelativeAud_0// "The relative AudienceUri is valid."
0x15f85  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x15f8a  ldc.i4.1
0x15f8b  stloc.0
0x15f8c  leave.s  loc_15FBE
0x15f8e  stloc.1
0x15f8f  ldc.i4   0x809318
0x15f94  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x15f99  ldc.i4.s 0xA
0x15f9b  ldstr    aExceptionValid_1// "Exception validating relative audience "...
0x15fa0  ldc.i4.2
0x15fa1  newarr   [mscorlib]System.Object
0x15fa6  stloc.2
0x15fa7  ldloc.2
0x15fa8  ldc.i4.0
0x15fa9  ldarg.1
0x15faa  callvirt instance class [System]System.Uri Microsoft.SharePoint.IdentityModel.SPAudienceValidationParameters::get_AudienceUri()
0x15faf  stelem.ref
0x15fb0  ldloc.2
0x15fb1  ldc.i4.1
0x15fb2  ldloc.1
0x15fb3  stelem.ref
0x15fb4  ldloc.2
0x15fb5  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x15fba  ldc.i4.0
0x15fbb  stloc.0
0x15fbc  leave.s  loc_15FBE
0x15fbe  ldloc.0
0x15fbf  ret
```
