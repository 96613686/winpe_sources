# Microsoft.SharePoint.IdentityModel.SPAudienceValidator::ValidateAbsoluteUriAudience

- ea: `0x8b70`
- end: `0x8c31`
- name: `Microsoft.SharePoint.IdentityModel.SPAudienceValidator::ValidateAbsoluteUriAudience`
- size: `193`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x8a40`
- `0x15fc0`

## callees

- `0x88c0`
- `0x88e0`
- `0x8900`
- `0x8920`
- `0x8b70`
- `0x8c40`
- `0x9760`

## string_xrefs

- `0x8b85`: `The audienceUri is null.`
- `0x8b8f`: `audienceUri`
- `0x8bae`: `IisSettings are not loaded, they are required for SPAudienceValidationMode.AbsoluteUri mode.`
- `0x8beb`: `The absolute uri validation failed. AudienceUri: '{0}'.`
- `0x8c14`: `The absolute uri validation succeeded. AudienceUri: '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0x8b70  ldnull
0x8b71  ldarg.1
0x8b72  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x8b77  brfalse.s loc_8B9A
0x8b79  ldc.i4   0x809304
0x8b7e  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x8b83  ldc.i4.s 0xA
0x8b85  ldstr    aTheAudienceuri_0// "The audienceUri is null."
0x8b8a  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x8b8f  ldstr    aAudienceuri// "audienceUri"
0x8b94  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x8b99  throw
0x8b9a  ldarg.0
0x8b9b  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPIisSettings Microsoft.SharePoint.IdentityModel.SPAudienceValidator::get_IisSettings()
0x8ba0  brtrue.s loc_8BBE
0x8ba2  ldc.i4   0xCB2C5
0x8ba7  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x8bac  ldc.i4.s 0xA
0x8bae  ldstr    aIissettingsAre// "IisSettings are not loaded, they are re"...
0x8bb3  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x8bb8  newobj   instance void Microsoft.SharePoint.IdentityModel.SPAudienceValidatorInitializationException::.ctor()
0x8bbd  throw
0x8bbe  ldarg.1
0x8bbf  ldarg.0
0x8bc0  call     instance class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPWebApplication Microsoft.SharePoint.IdentityModel.SPAudienceValidator::get_RequestWebApplication()
0x8bc5  callvirt instance valuetype [mscorlib]System.Guid [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPPersistedObject::get_Id()
0x8bca  ldarg.0
0x8bcb  call     instance valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPUrlZone Microsoft.SharePoint.IdentityModel.SPAudienceValidator::get_RequestZone()
0x8bd0  ldarg.0
0x8bd1  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<string> Microsoft.SharePoint.IdentityModel.SPAudienceValidator::get_TrustedLoginProviderNames()
0x8bd6  call     bool Microsoft.SharePoint.IdentityModel.SPAudienceValidator::ValidateSingleAudienceCondition(class [System]System.Uri audienceUri, valuetype [mscorlib]System.Guid requestWebAppId, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Administration.SPUrlZone requestZone, class [mscorlib]System.Collections.Generic.IEnumerable`1<string> trustedLoginProviderNames)
0x8bdb  stloc.0
0x8bdc  ldloc.0
0x8bdd  brtrue.s loc_8C08
0x8bdf  ldc.i4   0x8C561F
0x8be4  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x8be9  ldc.i4.s 0xA
0x8beb  ldstr    aTheAbsoluteUri// "The absolute uri validation failed. Aud"...
0x8bf0  ldc.i4.1
0x8bf1  newarr   [mscorlib]System.Object
0x8bf6  stloc.1
0x8bf7  ldloc.1
0x8bf8  ldc.i4.0
0x8bf9  ldarg.1
0x8bfa  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSSanitizer::SanitizeAbsoluteUri(class [System]System.Uri)
0x8bff  stelem.ref
0x8c00  ldloc.1
0x8c01  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x8c06  br.s     loc_8C2F
0x8c08  ldc.i4   0x8C5620
0x8c0d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_AudienceValidation()
0x8c12  ldc.i4.s 0x32
0x8c14  ldstr    aTheAbsoluteUri_0// "The absolute uri validation succeeded. "...
0x8c19  ldc.i4.1
0x8c1a  newarr   [mscorlib]System.Object
0x8c1f  stloc.2
0x8c20  ldloc.2
0x8c21  ldc.i4.0
0x8c22  ldarg.1
0x8c23  call     class [System]System.Uri [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSSanitizer::SanitizeAbsoluteUri(class [System]System.Uri)
0x8c28  stelem.ref
0x8c29  ldloc.2
0x8c2a  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x8c2f  ldloc.0
0x8c30  ret
```
