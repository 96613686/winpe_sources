# Microsoft.SharePoint.IdentityModel.SPSaml11SecurityTokenHandler::ValidateConditions

- ea: `0x1bef0`
- end: `0x1bf64`
- name: `Microsoft.SharePoint.IdentityModel.SPSaml11SecurityTokenHandler::ValidateConditions`
- size: `116`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x1bc70`
- `0x1bca0`
- `0x1bef0`

## string_xrefs

- `0x1bf02`: `Not validating SAML token audience restriction conditions.`
- `0x1bf22`: `Saml token failed to satisfy the audience restriction conditions.`
- `0x1bf2c`: `UnvalidatedAudienceUris`
- `0x1bf51`: `Saml token successfully satisfied the audience restriction conditions.`

## pseudocode

```c

```

## disassembly

```asm
0x1bef0  ldarg.2
0x1bef1  brtrue.s loc_1BF0E
0x1bef3  ldc.i4   0x7CC194
0x1bef8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPSaml11SecurityTokenHandler::get_Category()
0x1befd  ldc.i4   0xC8
0x1bf02  ldstr    aNotValidatingS// "Not validating SAML token audience rest"...
0x1bf07  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1bf0c  br.s     loc_1BF5B
0x1bf0e  ldarg.1
0x1bf0f  call     bool Microsoft.SharePoint.IdentityModel.SPSaml11SecurityTokenHandler::ValidateAudienceConditions(class [System.IdentityModel]System.IdentityModel.Tokens.SamlConditions conditions)
0x1bf14  brtrue.s loc_1BF42
0x1bf16  ldc.i4   0x7CC195
0x1bf1b  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPSaml11SecurityTokenHandler::get_Category()
0x1bf20  ldc.i4.s 0xA
0x1bf22  ldstr    aSamlTokenFaile// "Saml token failed to satisfy the audien"...
0x1bf27  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1bf2c  ldstr    aUnvalidatedaud// "UnvalidatedAudienceUris"
0x1bf31  ldc.i4.0
0x1bf32  newarr   [mscorlib]System.Object
0x1bf37  call     string [Microsoft.SharePoint]Microsoft.SharePoint.SPResource::GetString(string, object[])
0x1bf3c  newobj   instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.FailedAuthenticationException::.ctor(string)
0x1bf41  throw
0x1bf42  ldc.i4   0x7CC196
0x1bf47  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPSaml11SecurityTokenHandler::get_Category()
0x1bf4c  ldc.i4   0xC8
0x1bf51  ldstr    aSamlTokenSucce// "Saml token successfully satisfied the a"...
0x1bf56  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1bf5b  ldarg.0
0x1bf5c  ldarg.1
0x1bf5d  ldc.i4.0
0x1bf5e  call     instance void [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.Saml11.Saml11SecurityTokenHandler::ValidateConditions(class [System.IdentityModel]System.IdentityModel.Tokens.SamlConditions, bool)
0x1bf63  ret
```
