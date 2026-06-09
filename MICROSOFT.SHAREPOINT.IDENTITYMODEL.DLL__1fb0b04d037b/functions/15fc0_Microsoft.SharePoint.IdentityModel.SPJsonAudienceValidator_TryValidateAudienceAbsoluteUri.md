# Microsoft.SharePoint.IdentityModel.SPJsonAudienceValidator::TryValidateAudienceAbsoluteUri

- ea: `0x15fc0`
- end: `0x160ab`
- name: `Microsoft.SharePoint.IdentityModel.SPJsonAudienceValidator::TryValidateAudienceAbsoluteUri`
- size: `235`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x162c0`
- `0x16770`

## callees

- `0x8940`
- `0x8b70`
- `0x97a0`
- `0x15fc0`

## string_xrefs

- `0x16029`: `The AudienceUri is null.`
- `0x16001`: `The ValidationMode is not set to include absolute uri.`
- `0x16051`: `The absolute AudienceUri is NOT valid.`
- `0x1606b`: `The absolute AudienceUri is valid.`
- `0x16086`: `Exception validating absolute audience URI. Audience: '{0}', Exception: '{1}'.`

## pseudocode

```c

```

## disassembly

```asm
0x15fc0  ldarg.1
0x15fc1  brtrue.s loc_15FDB
0x15fc3  ldc.i4   0x809319
0x15fc8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x15fcd  ldc.i4.s 0xA
0x15fcf  ldstr    aTheValidationp// "The validationParams is null."
0x15fd4  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x15fd9  ldc.i4.0
0x15fda  ret
0x15fdb  ldc.i4.0
0x15fdc  stloc.0
0x15fdd  ldarg.0
0x15fde  call     instance valuetype Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode Microsoft.SharePoint.IdentityModel.SPAudienceValidator::get_ValidationMode()
0x15fe3  box      Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode
0x15fe8  ldc.i4.1
0x15fe9  box      Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode
0x15fee  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x15ff3  brtrue.s loc_1600F
0x15ff5  ldc.i4   0x80931A
0x15ffa  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x15fff  ldc.i4.s 0xA
0x16001  ldstr    aTheValidationm_1// "The ValidationMode is not set to includ"...
0x16006  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1600b  ldc.i4.0
0x1600c  stloc.0
0x1600d  br.s     loc_16077
0x1600f  ldnull
0x16010  ldarg.1
0x16011  callvirt instance class [System]System.Uri Microsoft.SharePoint.IdentityModel.SPAudienceValidationParameters::get_AudienceUri()
0x16016  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x1601b  brfalse.s loc_16037
0x1601d  ldc.i4   0x80931B
0x16022  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x16027  ldc.i4.s 0xA
0x16029  ldstr    aTheAudienceuri_2// "The AudienceUri is null."
0x1602e  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x16033  ldc.i4.0
0x16034  stloc.0
0x16035  br.s     loc_16077
0x16037  ldarg.0
0x16038  ldarg.1
0x16039  callvirt instance class [System]System.Uri Microsoft.SharePoint.IdentityModel.SPAudienceValidationParameters::get_AudienceUri()
0x1603e  callvirt instance bool Microsoft.SharePoint.IdentityModel.SPAudienceValidator::ValidateAbsoluteUriAudience(class [System]System.Uri audienceUri)
0x16043  brtrue.s loc_1605F
0x16045  ldc.i4   0x80931C
0x1604a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x1604f  ldc.i4.s 0x32
0x16051  ldstr    aTheAbsoluteAud// "The absolute AudienceUri is NOT valid."
0x16056  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1605b  ldc.i4.0
0x1605c  stloc.0
0x1605d  br.s     loc_16077
0x1605f  ldc.i4   0x80931D
0x16064  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x16069  ldc.i4.s 0x32
0x1606b  ldstr    aTheAbsoluteAud_0// "The absolute AudienceUri is valid."
0x16070  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x16075  ldc.i4.1
0x16076  stloc.0
0x16077  leave.s  loc_160A9
0x16079  stloc.1
0x1607a  ldc.i4   0x80931E
0x1607f  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x16084  ldc.i4.s 0xA
0x16086  ldstr    aExceptionValid_2// "Exception validating absolute audience "...
0x1608b  ldc.i4.2
0x1608c  newarr   [mscorlib]System.Object
0x16091  stloc.2
0x16092  ldloc.2
0x16093  ldc.i4.0
0x16094  ldarg.1
0x16095  callvirt instance class [System]System.Uri Microsoft.SharePoint.IdentityModel.SPAudienceValidationParameters::get_AudienceUri()
0x1609a  stelem.ref
0x1609b  ldloc.2
0x1609c  ldc.i4.1
0x1609d  ldloc.1
0x1609e  stelem.ref
0x1609f  ldloc.2
0x160a0  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x160a5  ldc.i4.0
0x160a6  stloc.0
0x160a7  leave.s  loc_160A9
0x160a9  ldloc.0
0x160aa  ret
```
