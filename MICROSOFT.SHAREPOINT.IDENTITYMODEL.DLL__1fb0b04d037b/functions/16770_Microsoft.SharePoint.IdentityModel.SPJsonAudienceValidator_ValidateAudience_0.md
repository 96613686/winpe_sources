# Microsoft.SharePoint.IdentityModel.SPJsonAudienceValidator::ValidateAudience_0

- ea: `0x16770`
- end: `0x1692d`
- name: `Microsoft.SharePoint.IdentityModel.SPJsonAudienceValidator::ValidateAudience_0`
- size: `445`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18860`

## callees

- `0x8940`
- `0x15d60`
- `0x15ed0`
- `0x15fc0`
- `0x160b0`
- `0x16460`
- `0x16510`
- `0x165c0`
- `0x16670`
- `0x16770`

## string_xrefs

- `0x16789`: `token`
- `0x1677f`: `The token is null.`
- `0x167dd`: `Trying relative URI audience validation.`
- `0x16821`: `Trying absolute URI with tenant id audience validation.`
- `0x16865`: `Trying absolute URI audience validation.`
- `0x167a0`: `Validating Json token audience.`
- `0x168cb`: `The token audience is NOT valid. Audience: '{0}', Mode: '{1}'.`
- `0x16902`: `The token audience is valid. Audience: '{0}', Mode: '{1}'.`

## pseudocode

```c

```

## disassembly

```asm
0x16770  ldarg.1
0x16771  brtrue.s loc_16794
0x16773  ldc.i4   0x809350
0x16778  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x1677d  ldc.i4.s 0xA
0x1677f  ldstr    aTheTokenIsNull// "The token is null."
0x16784  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x16789  ldstr    aToken// "token"
0x1678e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x16793  throw
0x16794  ldc.i4   0x1254786
0x16799  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x1679e  ldc.i4.s 0x64
0x167a0  ldstr    aValidatingJson// "Validating Json token audience."
0x167a5  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x167aa  ldc.i4.0
0x167ab  stloc.0
0x167ac  ldnull
0x167ad  stloc.1
0x167ae  ldarg.0
0x167af  call     instance valuetype Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode Microsoft.SharePoint.IdentityModel.SPAudienceValidator::get_ValidationMode()
0x167b4  box      Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode
0x167b9  ldc.i4.2
0x167ba  box      Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode
0x167bf  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x167c4  brfalse.s loc_167EF
0x167c6  ldarg.0
0x167c7  ldarg.1
0x167c8  ldloca.s 1
0x167ca  call     instance bool Microsoft.SharePoint.IdentityModel.SPJsonAudienceValidator::TryToGetRelativeUriParametersFromToken(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken token, [out] class Microsoft.SharePoint.IdentityModel.SPAudienceValidationParameters& validationParams)
0x167cf  brfalse.s loc_167EF
0x167d1  ldc.i4   0x1254787
0x167d6  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x167db  ldc.i4.s 0x64
0x167dd  ldstr    aTryingRelative// "Trying relative URI audience validation"...
0x167e2  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x167e7  ldarg.0
0x167e8  ldloc.1
0x167e9  call     instance bool Microsoft.SharePoint.IdentityModel.SPJsonAudienceValidator::TryValidateAudienceRelativeUri(class Microsoft.SharePoint.IdentityModel.SPAudienceValidationParameters validationParams)
0x167ee  stloc.0
0x167ef  ldloc.0
0x167f0  brtrue.s loc_16833
0x167f2  ldarg.0
0x167f3  call     instance valuetype Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode Microsoft.SharePoint.IdentityModel.SPAudienceValidator::get_ValidationMode()
0x167f8  box      Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode
0x167fd  ldc.i4.8
0x167fe  box      Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode
0x16803  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x16808  brfalse.s loc_16833
0x1680a  ldarg.0
0x1680b  ldarg.1
0x1680c  ldloca.s 1
0x1680e  call     instance bool Microsoft.SharePoint.IdentityModel.SPJsonAudienceValidator::TryToGetAbsoluteUriWithTenantIdParametersFromToken(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken token, [out] class Microsoft.SharePoint.IdentityModel.SPAudienceValidationParameters& validationParams)
0x16813  brfalse.s loc_16833
0x16815  ldc.i4   0x1254788
0x1681a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x1681f  ldc.i4.s 0x64
0x16821  ldstr    aTryingAbsolute// "Trying absolute URI with tenant id audi"...
0x16826  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1682b  ldarg.0
0x1682c  ldloc.1
0x1682d  call     instance bool Microsoft.SharePoint.IdentityModel.SPJsonAudienceValidator::TryValidateAudienceAbsoluteUriWithTenantId(class Microsoft.SharePoint.IdentityModel.SPAudienceValidationParameters validationParams)
0x16832  stloc.0
0x16833  ldloc.0
0x16834  brtrue.s loc_16877
0x16836  ldarg.0
0x16837  call     instance valuetype Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode Microsoft.SharePoint.IdentityModel.SPAudienceValidator::get_ValidationMode()
0x1683c  box      Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode
0x16841  ldc.i4.1
0x16842  box      Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode
0x16847  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x1684c  brfalse.s loc_16877
0x1684e  ldarg.0
0x1684f  ldarg.1
0x16850  ldloca.s 1
0x16852  call     instance bool Microsoft.SharePoint.IdentityModel.SPJsonAudienceValidator::TryToGetAbsoluteUriParametersFromToken(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken token, [out] class Microsoft.SharePoint.IdentityModel.SPAudienceValidationParameters& validationParams)
0x16857  brfalse.s loc_16877
0x16859  ldc.i4   0x1254789
0x1685e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x16863  ldc.i4.s 0x64
0x16865  ldstr    aTryingAbsolute_0// "Trying absolute URI audience validation"...
0x1686a  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1686f  ldarg.0
0x16870  ldloc.1
0x16871  call     instance bool Microsoft.SharePoint.IdentityModel.SPJsonAudienceValidator::TryValidateAudienceAbsoluteUri(class Microsoft.SharePoint.IdentityModel.SPAudienceValidationParameters validationParams)
0x16876  stloc.0
0x16877  ldloc.0
0x16878  brtrue.s loc_168BC
0x1687a  ldarg.0
0x1687b  call     instance valuetype Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode Microsoft.SharePoint.IdentityModel.SPAudienceValidator::get_ValidationMode()
0x16880  box      Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode
0x16885  ldc.i4.s 0x10
0x16887  box      Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode
0x1688c  call     instance bool [mscorlib]System.Enum::HasFlag(class [mscorlib]System.Enum)
0x16891  brfalse.s loc_168BC
0x16893  ldarg.0
0x16894  ldarg.1
0x16895  ldloca.s 1
0x16897  call     instance bool Microsoft.SharePoint.IdentityModel.SPJsonAudienceValidator::TryToGetAppIdParametersFromToken(class [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken token, [out] class Microsoft.SharePoint.IdentityModel.SPAudienceValidationParameters& validationParams)
0x1689c  brfalse.s loc_168BC
0x1689e  ldc.i4   0x125478A
0x168a3  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x168a8  ldc.i4.s 0x64
0x168aa  ldstr    aTryingApplicat// "Trying application id audience validati"...
0x168af  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x168b4  ldarg.0
0x168b5  ldloc.1
0x168b6  call     instance bool Microsoft.SharePoint.IdentityModel.SPJsonAudienceValidator::TryValidateAudienceGuidAppId(class Microsoft.SharePoint.IdentityModel.SPAudienceValidationParameters validationParams)
0x168bb  stloc.0
0x168bc  ldloc.0
0x168bd  brtrue.s loc_168F6
0x168bf  ldc.i4   0x809351
0x168c4  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x168c9  ldc.i4.s 0xA
0x168cb  ldstr    aTheTokenAudien_2// "The token audience is NOT valid. Audien"...
0x168d0  ldc.i4.2
0x168d1  newarr   [mscorlib]System.Object
0x168d6  stloc.2
0x168d7  ldloc.2
0x168d8  ldc.i4.0
0x168d9  ldarg.1
0x168da  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Audience()
0x168df  stelem.ref
0x168e0  ldloc.2
0x168e1  ldc.i4.1
0x168e2  ldarg.0
0x168e3  call     instance valuetype Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode Microsoft.SharePoint.IdentityModel.SPAudienceValidator::get_ValidationMode()
0x168e8  box      Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode
0x168ed  stelem.ref
0x168ee  ldloc.2
0x168ef  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x168f4  br.s     loc_1692B
0x168f6  ldc.i4   0x809352
0x168fb  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x16900  ldc.i4.s 0x32
0x16902  ldstr    aTheTokenAudien_3// "The token audience is valid. Audience: "...
0x16907  ldc.i4.2
0x16908  newarr   [mscorlib]System.Object
0x1690d  stloc.3
0x1690e  ldloc.3
0x1690f  ldc.i4.0
0x16910  ldarg.1
0x16911  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_Audience()
0x16916  stelem.ref
0x16917  ldloc.3
0x16918  ldc.i4.1
0x16919  ldarg.0
0x1691a  call     instance valuetype Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode Microsoft.SharePoint.IdentityModel.SPAudienceValidator::get_ValidationMode()
0x1691f  box      Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode
0x16924  stelem.ref
0x16925  ldloc.3
0x16926  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1692b  ldloc.0
0x1692c  ret
```
