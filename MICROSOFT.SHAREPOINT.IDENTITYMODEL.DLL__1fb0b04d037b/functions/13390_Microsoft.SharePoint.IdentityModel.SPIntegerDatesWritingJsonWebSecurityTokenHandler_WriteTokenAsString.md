# Microsoft.SharePoint.IdentityModel.SPIntegerDatesWritingJsonWebSecurityTokenHandler::WriteTokenAsString

- ea: `0x13390`
- end: `0x13443`
- name: `Microsoft.SharePoint.IdentityModel.SPIntegerDatesWritingJsonWebSecurityTokenHandler::WriteTokenAsString`
- size: `179`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x13220`
- `0x13390`
- `0x13470`
- `0x13480`

## string_xrefs

- `0x13393`: `token`
- `0x133ad`: `token`
- `0x133a8`: `Unsupported token type`

## pseudocode

```c

```

## disassembly

```asm
0x13390  ldarg.1
0x13391  brtrue.s loc_1339E
0x13393  ldstr    aToken// "token"
0x13398  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x1339d  throw
0x1339e  ldarg.1
0x1339f  isinst   Microsoft.SharePoint.IdentityModel.SPIntegerDatesWritingJsonWebSecurityToken
0x133a4  stloc.0
0x133a5  ldloc.0
0x133a6  brtrue.s loc_133B8
0x133a8  ldstr    aUnsupportedTok// "Unsupported token type"
0x133ad  ldstr    aToken// "token"
0x133b2  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x133b7  throw
0x133b8  ldloc.0
0x133b9  callvirt instance bool [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_CanWriteSourceData()
0x133be  brfalse.s loc_133C7
0x133c0  ldloc.0
0x133c1  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::WriteSourceData()
0x133c6  ret
0x133c7  ldloc.0
0x133c8  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::CreateHeaderClaims()
0x133cd  stloc.1
0x133ce  ldloc.0
0x133cf  callvirt instance class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> Microsoft.SharePoint.IdentityModel.SPIntegerDatesWritingJsonWebSecurityToken::CreatePayloadClaimsWithIntegerDates()
0x133d4  stloc.2
0x133d5  ldnull
0x133d6  stloc.3
0x133d7  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x133dc  ldstr    a01// "{0}.{1}"
0x133e1  ldc.i4.2
0x133e2  newarr   [mscorlib]System.Object
0x133e7  stloc.s  5
0x133e9  ldloc.s  5
0x133eb  ldc.i4.0
0x133ec  ldloc.1
0x133ed  call     string Microsoft.SharePoint.IdentityModel.DictionaryExtension::EncodeToJson(class [mscorlib]System.Collections.Generic.IDictionary`2<string, string> self)
0x133f2  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPBase64UrlEncoder::Encode(string)
0x133f7  stelem.ref
0x133f8  ldloc.s  5
0x133fa  ldc.i4.1
0x133fb  ldloc.2
0x133fc  call     string Microsoft.SharePoint.IdentityModel.DictionaryExtension::EncodeToJson(class [mscorlib]System.Collections.Generic.IDictionary`2<string, object> self)
0x13401  call     string [Microsoft.SharePoint]Microsoft.SharePoint.Utilities.SPBase64UrlEncoder::Encode(string)
0x13406  stelem.ref
0x13407  ldloc.s  5
0x13409  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x1340e  stloc.3
0x1340f  ldarg.0
0x13410  ldloc.3
0x13411  ldloc.0
0x13412  callvirt instance class [System.IdentityModel]System.IdentityModel.Tokens.SigningCredentials [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityToken::get_SigningCredentials()
0x13417  callvirt instance string [Microsoft.IdentityModel.Extensions]Microsoft.IdentityModel.S2S.Tokens.JsonWebSecurityTokenHandler::Sign(string, class [System.IdentityModel]System.IdentityModel.Tokens.SigningCredentials)
0x1341c  stloc.s  4
0x1341e  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x13423  ldstr    a01// "{0}.{1}"
0x13428  ldc.i4.2
0x13429  newarr   [mscorlib]System.Object
0x1342e  stloc.s  6
0x13430  ldloc.s  6
0x13432  ldc.i4.0
0x13433  ldloc.3
0x13434  stelem.ref
0x13435  ldloc.s  6
0x13437  ldc.i4.1
0x13438  ldloc.s  4
0x1343a  stelem.ref
0x1343b  ldloc.s  6
0x1343d  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x13442  ret
```
