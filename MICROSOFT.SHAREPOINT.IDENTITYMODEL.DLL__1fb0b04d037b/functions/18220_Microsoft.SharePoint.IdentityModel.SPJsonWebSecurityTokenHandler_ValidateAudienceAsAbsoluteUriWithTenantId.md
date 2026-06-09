# Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::ValidateAudienceAsAbsoluteUriWithTenantId

- ea: `0x18220`
- end: `0x182ce`
- name: `Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::ValidateAudienceAsAbsoluteUriWithTenantId`
- size: `174`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x8830`
- `0x8a40`
- `0x97b0`
- `0x97d0`
- `0x98c0`
- `0x18180`
- `0x18220`

## string_xrefs

- `0x1825a`: `Json token audience validation failed.`
- `0x1827a`: `Json token audience validation failed as token audience is not a valid absolute uri. Token Audience: '{0}'.`
- `0x182ae`: `Json token audience validation failed as audience validator couldn't be initialized.`

## pseudocode

```c

```

## disassembly

```asm
0x18220  ldarg.1
0x18221  ldc.i4.1
0x18222  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0x18227  stloc.0
0x18228  ldc.i4.8
0x18229  newobj   instance void Microsoft.SharePoint.IdentityModel.SPAudienceValidator::.ctor(valuetype Microsoft.SharePoint.IdentityModel.SPAudienceValidationMode validationMode)
0x1822e  stloc.1
0x1822f  newobj   instance void Microsoft.SharePoint.IdentityModel.SPAudienceValidationParameters::.ctor()
0x18234  stloc.3
0x18235  ldloc.3
0x18236  ldloc.0
0x18237  callvirt instance void Microsoft.SharePoint.IdentityModel.SPAudienceValidationParameters::set_AudienceUri(class [System]System.Uri value)
0x1823c  ldloc.3
0x1823d  ldarg.2
0x1823e  callvirt instance void Microsoft.SharePoint.IdentityModel.SPAudienceValidationParameters::set_TenantId(string value)
0x18243  ldloc.3
0x18244  stloc.2
0x18245  ldloc.1
0x18246  ldloc.2
0x18247  callvirt instance bool Microsoft.SharePoint.IdentityModel.SPAudienceValidator::ValidateAudience(class Microsoft.SharePoint.IdentityModel.SPAudienceValidationParameters validationParams)
0x1824c  brtrue.s loc_1826B
0x1824e  ldc.i4   0x4454DC
0x18253  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::get_Category()
0x18258  ldc.i4.s 0x32
0x1825a  ldstr    aJsonTokenAudie// "Json token audience validation failed."
0x1825f  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x18264  ldloc.0
0x18265  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPInvalidAudienceUriOAuthException::.ctor(class [System]System.Uri)
0x1826a  throw
0x1826b  leave.s  loc_182CD
0x1826d  pop
0x1826e  ldc.i4   0x4454DD
0x18273  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::get_Category()
0x18278  ldc.i4.s 0x32
0x1827a  ldstr    aJsonTokenAudie_0// "Json token audience validation failed a"...
0x1827f  ldc.i4.1
0x18280  newarr   [mscorlib]System.Object
0x18285  stloc.s  5
0x18287  ldloc.s  5
0x18289  ldc.i4.0
0x1828a  ldarg.1
0x1828b  stelem.ref
0x1828c  ldloc.s  5
0x1828e  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x18293  ldarg.1
0x18294  ldc.i4.0
0x18295  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0x1829a  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPInvalidAudienceUriOAuthException::.ctor(class [System]System.Uri)
0x1829f  throw
0x182a0  stloc.s  4
0x182a2  ldc.i4   0xCB2DF
0x182a7  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::get_Category()
0x182ac  ldc.i4.s 0x32
0x182ae  ldstr    aJsonTokenAudie_1// "Json token audience validation failed a"...
0x182b3  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x182b8  ldarg.1
0x182b9  ldc.i4.0
0x182ba  newobj   instance void [System]System.Uri::.ctor(string, valuetype [System]System.UriKind)
0x182bf  ldnull
0x182c0  ldloc.s  4
0x182c2  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.AudienceUriValidationFailedException::.ctor(string, class [mscorlib]System.Exception)
0x182c7  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPInvalidAudienceUriOAuthException::.ctor(class [System]System.Uri, class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.AudienceUriValidationFailedException)
0x182cc  throw
0x182cd  ret
```
