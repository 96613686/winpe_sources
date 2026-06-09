# Microsoft.SharePoint.IdentityModel.SPJsonAudienceValidator::ValidateAudience

- ea: `0x162c0`
- end: `0x16460`
- name: `Microsoft.SharePoint.IdentityModel.SPJsonAudienceValidator::ValidateAudience`
- size: `416`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callees

- `0x8940`
- `0x15d60`
- `0x15ed0`
- `0x15fc0`
- `0x160b0`
- `0x161d0`
- `0x162c0`

## string_xrefs

- `0x1630a`: `Trying relative URI audience validation.`
- `0x16343`: `Trying absolute URI with tenant id audience validation.`
- `0x1637c`: `Trying absolute URI audience validation.`
- `0x163b5`: `Trying proof token audience validation.`

## pseudocode

```c

```

## disassembly

```asm
0x162c0  ldarg.1
0x162c1  brtrue.s loc_162E4
0x162c3  ldc.i4   0x809348
0x162c8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x162cd  ldc.i4.s 0xA
0x162cf  ldstr    aTheValidationp// "The validationParams is null."
0x162d4  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x162d9  ldstr    aValidationpara// "validationParams"
0x162de  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x162e3  throw
0x162e4  ldc.i4.0
0x162e5  stloc.0
0x162e6  ldarg.0
0x162e7  call     instance valuetype Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode Microsoft.SharePoint.IdentityModel.SPAudienceValidator::get_ValidationMode()
0x162ec  box      Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode
0x162f1  ldc.i4.2
0x162f2  box      Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode
0x162f7  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x162fc  brfalse.s loc_1631C
0x162fe  ldc.i4   0x1254781
0x16303  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x16308  ldc.i4.s 0x64
0x1630a  ldstr    aTryingRelative// "Trying relative URI audience validation"...
0x1630f  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x16314  ldarg.0
0x16315  ldarg.1
0x16316  call     instance bool Microsoft.SharePoint.IdentityModel.SPJsonAudienceValidator::TryValidateAudienceRelativeUri(class Microsoft.SharePoint.IdentityModel.SPAudienceValidationParameters validationParams)
0x1631b  stloc.0
0x1631c  ldloc.0
0x1631d  brtrue.s loc_16355
0x1631f  ldarg.0
0x16320  call     instance valuetype Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode Microsoft.SharePoint.IdentityModel.SPAudienceValidator::get_ValidationMode()
0x16325  box      Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode
0x1632a  ldc.i4.8
0x1632b  box      Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode
0x16330  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x16335  brfalse.s loc_16355
0x16337  ldc.i4   0x1254782
0x1633c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x16341  ldc.i4.s 0x64
0x16343  ldstr    aTryingAbsolute// "Trying absolute URI with tenant id audi"...
0x16348  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1634d  ldarg.0
0x1634e  ldarg.1
0x1634f  call     instance bool Microsoft.SharePoint.IdentityModel.SPJsonAudienceValidator::TryValidateAudienceAbsoluteUriWithTenantId(class Microsoft.SharePoint.IdentityModel.SPAudienceValidationParameters validationParams)
0x16354  stloc.0
0x16355  ldloc.0
0x16356  brtrue.s loc_1638E
0x16358  ldarg.0
0x16359  call     instance valuetype Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode Microsoft.SharePoint.IdentityModel.SPAudienceValidator::get_ValidationMode()
0x1635e  box      Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode
0x16363  ldc.i4.1
0x16364  box      Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode
0x16369  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x1636e  brfalse.s loc_1638E
0x16370  ldc.i4   0x1254783
0x16375  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x1637a  ldc.i4.s 0x64
0x1637c  ldstr    aTryingAbsolute_0// "Trying absolute URI audience validation"...
0x16381  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x16386  ldarg.0
0x16387  ldarg.1
0x16388  call     instance bool Microsoft.SharePoint.IdentityModel.SPJsonAudienceValidator::TryValidateAudienceAbsoluteUri(class Microsoft.SharePoint.IdentityModel.SPAudienceValidationParameters validationParams)
0x1638d  stloc.0
0x1638e  ldloc.0
0x1638f  brtrue.s loc_163C7
0x16391  ldarg.0
0x16392  call     instance valuetype Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode Microsoft.SharePoint.IdentityModel.SPAudienceValidator::get_ValidationMode()
0x16397  box      Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode
0x1639c  ldc.i4.4
0x1639d  box      Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode
0x163a2  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x163a7  brfalse.s loc_163C7
0x163a9  ldc.i4   0x1254784
0x163ae  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x163b3  ldc.i4.s 0x64
0x163b5  ldstr    aTryingProofTok// "Trying proof token audience validation."
0x163ba  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x163bf  ldarg.0
0x163c0  ldarg.1
0x163c1  call     instance bool Microsoft.SharePoint.IdentityModel.SPJsonAudienceValidator::TryValidateAudienceProofToken(class Microsoft.SharePoint.IdentityModel.SPAudienceValidationParameters validationParams)
0x163c6  stloc.0
0x163c7  ldloc.0
0x163c8  brtrue.s loc_16401
0x163ca  ldarg.0
0x163cb  call     instance valuetype Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode Microsoft.SharePoint.IdentityModel.SPAudienceValidator::get_ValidationMode()
0x163d0  box      Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode
0x163d5  ldc.i4.s 0x10
0x163d7  box      Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode
0x163dc  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x163e1  brfalse.s loc_16401
0x163e3  ldc.i4   0x1254785
0x163e8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x163ed  ldc.i4.s 0x64
0x163ef  ldstr    aTryingApplicat// "Trying application id audience validati"...
0x163f4  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x163f9  ldarg.0
0x163fa  ldarg.1
0x163fb  call     instance bool Microsoft.SharePoint.IdentityModel.SPJsonAudienceValidator::TryValidateAudienceGuidAppId(class Microsoft.SharePoint.IdentityModel.SPAudienceValidationParameters validationParams)
0x16400  stloc.0
0x16401  ldloc.0
0x16402  brtrue.s loc_16432
0x16404  ldc.i4   0x809349
0x16409  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x1640e  ldc.i4.s 0xA
0x16410  ldstr    aTheValidationp_1// "The validationParams are NOT valid. Mod"...
0x16415  ldc.i4.1
0x16416  newarr   [mscorlib]System.Object
0x1641b  stloc.1
0x1641c  ldloc.1
0x1641d  ldc.i4.0
0x1641e  ldarg.0
0x1641f  call     instance valuetype Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode Microsoft.SharePoint.IdentityModel.SPAudienceValidator::get_ValidationMode()
0x16424  box      Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode
0x16429  stelem.ref
0x1642a  ldloc.1
0x1642b  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x16430  br.s     loc_1645E
0x16432  ldc.i4   0x80934A
0x16437  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x1643c  ldc.i4.s 0x32
0x1643e  ldstr    aTheValidationp_2// "The validationParams are valid. Mode: '"...
0x16443  ldc.i4.1
0x16444  newarr   [mscorlib]System.Object
0x16449  stloc.2
0x1644a  ldloc.2
0x1644b  ldc.i4.0
0x1644c  ldarg.0
0x1644d  call     instance valuetype Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode Microsoft.SharePoint.IdentityModel.SPAudienceValidator::get_ValidationMode()
0x16452  box      Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode
0x16457  stelem.ref
0x16458  ldloc.2
0x16459  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1645e  ldloc.0
0x1645f  ret
```
