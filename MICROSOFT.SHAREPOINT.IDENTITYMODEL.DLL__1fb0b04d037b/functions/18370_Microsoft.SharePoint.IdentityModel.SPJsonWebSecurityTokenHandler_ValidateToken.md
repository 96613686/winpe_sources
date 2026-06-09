# Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::ValidateToken

- ea: `0x18370`
- end: `0x183d8`
- name: `Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::ValidateToken`
- size: `104`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x16a10`
- `0x18180`
- `0x18370`
- `0x187d0`

## string_xrefs

- `0x18389`: `token`
- `0x1837f`: `The token is null.`
- `0x183b1`: `Json token proof key claim exists, caller must call ValidateToken overload that accepts proof token as a parameter.`
- `0x183c0`: `ProofTokenMissing`

## pseudocode

```c

```

## disassembly

```asm
0x18370  ldarg.1
0x18371  brtrue.s loc_18394
0x18373  ldc.i4   0x65040C
0x18378  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::get_Category()
0x1837d  ldc.i4.s 0xA
0x1837f  ldstr    aTheTokenIsNull// "The token is null."
0x18384  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x18389  ldstr    aToken// "token"
0x1838e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x18393  throw
0x18394  ldarg.0
0x18395  ldarg.1
0x18396  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::ValidateToken(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken token)
0x1839b  stloc.0
0x1839c  ldarg.0
0x1839d  ldloc.0
0x1839e  call     instance bool Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::IsProofTokenRequired(class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection identities)
0x183a3  brfalse.s loc_183D6
0x183a5  ldc.i4   0x142115
0x183aa  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::get_Category()
0x183af  ldc.i4.s 0x64
0x183b1  ldstr    aJsonTokenProof// "Json token proof key claim exists, call"...
0x183b6  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x183bb  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x183c0  ldstr    aProoftokenmiss// "ProofTokenMissing"
0x183c5  ldc.i4.0
0x183c6  newarr   [mscorlib]System.Object
0x183cb  call     string [Microsoft.SharePoint]Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo, string, object[])
0x183d0  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenException::.ctor(string)
0x183d5  throw
0x183d6  ldloc.0
0x183d7  ret
```
