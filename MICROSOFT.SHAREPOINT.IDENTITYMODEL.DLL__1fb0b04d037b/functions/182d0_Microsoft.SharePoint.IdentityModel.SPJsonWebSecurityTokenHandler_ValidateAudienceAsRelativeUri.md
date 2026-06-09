# Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::ValidateAudienceAsRelativeUri

- ea: `0x182d0`
- end: `0x18363`
- name: `Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::ValidateAudienceAsRelativeUri`
- size: `147`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x8830`
- `0x89f0`
- `0x18180`
- `0x182d0`

## string_xrefs

- `0x182f4`: `Json token audience validation failed.`
- `0x18314`: `Json token audience validation failed as token audience is not a valid absolute uri. Token Audience: '{0}'.`
- `0x18344`: `Json token audience validation failed as audience validator couldn't be initialized.`

## pseudocode

```c

```

## disassembly

```asm
0x182d0  ldarg.0
0x182d1  ldc.i4.2
0x182d2  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0x182d7  stloc.0
0x182d8  ldc.i4.2
0x182d9  newobj   instance void Microsoft.SharePoint.IdentityModel.SPAudienceValidator::.ctor(valuetype Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode validationMode)
0x182de  stloc.1
0x182df  ldloc.1
0x182e0  ldloc.0
0x182e1  callvirt instance bool Microsoft.SharePoint.IdentityModel.SPAudienceValidator::ValidateAudience(class [System]System.Uri audienceUri)
0x182e6  brtrue.s loc_18305
0x182e8  ldc.i4   0xCB2DE
0x182ed  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::get_Category()
0x182f2  ldc.i4.s 0x64
0x182f4  ldstr    aJsonTokenAudie// "Json token audience validation failed."
0x182f9  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x182fe  ldloc.0
0x182ff  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPInvalidAudienceUriOAuthException::.ctor(class [System]System.Uri)
0x18304  throw
0x18305  leave.s  loc_18362
0x18307  pop
0x18308  ldc.i4   0x4454DE
0x1830d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::get_Category()
0x18312  ldc.i4.s 0x32
0x18314  ldstr    aJsonTokenAudie_0// "Json token audience validation failed a"...
0x18319  ldc.i4.1
0x1831a  newarr   [mscorlib]System.Object
0x1831f  stloc.3
0x18320  ldloc.3
0x18321  ldc.i4.0
0x18322  ldarg.0
0x18323  stelem.ref
0x18324  ldloc.3
0x18325  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1832a  ldarg.0
0x1832b  ldc.i4.0
0x1832c  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0x18331  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPInvalidAudienceUriOAuthException::.ctor(class [System]System.Uri)
0x18336  throw
0x18337  stloc.2
0x18338  ldc.i4   0x4454DF
0x1833d  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::get_Category()
0x18342  ldc.i4.s 0x64
0x18344  ldstr    aJsonTokenAudie_1// "Json token audience validation failed a"...
0x18349  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1834e  ldarg.0
0x1834f  ldc.i4.0
0x18350  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0x18355  ldnull
0x18356  ldloc.2
0x18357  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.AudienceUriValidationFailedException::.ctor(string, class [mscorlib]System.Exception)
0x1835c  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPInvalidAudienceUriOAuthException::.ctor(class [System]System.Uri, class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.AudienceUriValidationFailedException)
0x18361  throw
0x18362  ret
```
