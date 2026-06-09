# Microsoft.SharePoint.IdentityModel.SPSaml11SecurityTokenHandler::ValidateTokenAudienceConditions

- ea: `0x1be40`
- end: `0x1bee3`
- name: `Microsoft.SharePoint.IdentityModel.SPSaml11SecurityTokenHandler::ValidateTokenAudienceConditions`
- size: `163`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x20170`

## callees

- `0x1bc70`
- `0x1bca0`
- `0x1be40`

## string_xrefs

- `0x1be59`: `token`
- `0x1be9b`: `token`
- `0x1bec5`: `token`
- `0x1be4f`: `The token is null.`
- `0x1be7a`: `The token is not a SamlSecurityToken token. TokenType: '{0}'.`
- `0x1beba`: `The saml token has no assertions.`

## pseudocode

```c

```

## disassembly

```asm
0x1be40  ldarg.0
0x1be41  brtrue.s loc_1BE64
0x1be43  ldc.i4   0x7CC191
0x1be48  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPSaml11SecurityTokenHandler::get_Category()
0x1be4d  ldc.i4.s 0xA
0x1be4f  ldstr    aTheTokenIsNull// "The token is null."
0x1be54  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1be59  ldstr    aToken// "token"
0x1be5e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1be63  throw
0x1be64  ldarg.0
0x1be65  isinst   [System.IdentityModel]System.IdentityModel.Tokens.SamlSecurityToken
0x1be6a  stloc.0
0x1be6b  ldloc.0
0x1be6c  brtrue.s loc_1BEA6
0x1be6e  ldc.i4   0x7CC192
0x1be73  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPSaml11SecurityTokenHandler::get_Category()
0x1be78  ldc.i4.s 0xA
0x1be7a  ldstr    aTheTokenIsNotA_4// "The token is not a SamlSecurityToken to"...
0x1be7f  ldc.i4.1
0x1be80  newarr   [mscorlib]System.Object
0x1be85  stloc.2
0x1be86  ldloc.2
0x1be87  ldc.i4.0
0x1be88  ldarg.0
0x1be89  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x1be8e  callvirt instance string [mscorlib]System.Object::ToString()
0x1be93  stelem.ref
0x1be94  ldloc.2
0x1be95  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1be9a  ldnull
0x1be9b  ldstr    aToken// "token"
0x1bea0  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x1bea5  throw
0x1bea6  ldloc.0
0x1bea7  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SamlAssertion [System.IdentityModel]System.IdentityModel.Tokens.SamlSecurityToken::get_Assertion()
0x1beac  brtrue.s loc_1BED0
0x1beae  ldc.i4   0x7CC193
0x1beb3  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPSaml11SecurityTokenHandler::get_Category()
0x1beb8  ldc.i4.s 0xA
0x1beba  ldstr    aTheSamlTokenHa// "The saml token has no assertions."
0x1bebf  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x1bec4  ldnull
0x1bec5  ldstr    aToken// "token"
0x1beca  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x1becf  throw
0x1bed0  ldloc.0
0x1bed1  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SamlAssertion [System.IdentityModel]System.IdentityModel.Tokens.SamlSecurityToken::get_Assertion()
0x1bed6  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SamlConditions [System.IdentityModel]System.IdentityModel.Tokens.SamlAssertion::get_Conditions()
0x1bedb  call     bool Microsoft.SharePoint.IdentityModel.SPSaml11SecurityTokenHandler::ValidateAudienceConditions(class [System.IdentityModel]System.IdentityModel.Tokens.SamlConditions conditions)
0x1bee0  stloc.1
0x1bee1  ldloc.1
0x1bee2  ret
```
