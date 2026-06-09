# Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::ValidateTokenIssuer_1

- ea: `0x17380`
- end: `0x1743b`
- name: `Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::ValidateTokenIssuer_1`
- size: `187`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x17280`

## callees

- `0x169c0`
- `0x17380`

## string_xrefs

- `0x173b8`: `The tokenIssuer is null or empty.`
- `0x173c2`: `tokenIssuer`
- `0x173f5`: `Mismatch between issuer name retrieved from registry and json token issuer name. RegisteredIssuerName: '{0}', TokenIssuerName: '{1}'.`
- `0x17424`: `Validated json token issuer. TokenIssuerName: '{0}'`

## pseudocode

```c

```

## disassembly

```asm
0x17380  ldarg.1
0x17381  brtrue.s loc_173A4
0x17383  ldc.i4   0x650402
0x17388  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x1738d  ldc.i4.s 0xA
0x1738f  ldstr    aTheSymmetricsi// "The symmetricSigningKey is null."
0x17394  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x17399  ldstr    aSymmetricsigni// "symmetricSigningKey"
0x1739e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x173a3  throw
0x173a4  ldarg.2
0x173a5  call     bool [mscorlib]System.String::IsNullOrWhiteSpace(string)
0x173aa  brfalse.s loc_173CD
0x173ac  ldc.i4   0x650403
0x173b1  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x173b6  ldc.i4.s 0xA
0x173b8  ldstr    aTheTokenissuer// "The tokenIssuer is null or empty."
0x173bd  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x173c2  ldstr    aTokenissuer// "tokenIssuer"
0x173c7  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x173cc  throw
0x173cd  ldarg.0
0x173ce  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenHandlerConfiguration [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenHandler::get_Configuration()
0x173d3  callvirt instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.IssuerNameRegistry [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.SecurityTokenHandlerConfiguration::get_IssuerNameRegistry()
0x173d8  ldarg.1
0x173d9  ldarg.2
0x173da  callvirt instance string [Microsoft.IdentityModel]Microsoft.IdentityModel.Tokens.IssuerNameRegistry::GetIssuerName(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken, string)
0x173df  stloc.0
0x173e0  ldloc.0
0x173e1  ldarg.2
0x173e2  call     bool [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPTrustedIssuerComparer::Matches(string, string)
0x173e7  brtrue.s loc_17415
0x173e9  ldc.i4   0x35F7D2
0x173ee  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x173f3  ldc.i4.s 0x32
0x173f5  ldstr    aMismatchBetwee// "Mismatch between issuer name retrieved "...
0x173fa  ldc.i4.2
0x173fb  newarr   [mscorlib]System.Object
0x17400  stloc.1
0x17401  ldloc.1
0x17402  ldc.i4.0
0x17403  ldloc.0
0x17404  stelem.ref
0x17405  ldloc.1
0x17406  ldc.i4.1
0x17407  ldarg.2
0x17408  stelem.ref
0x17409  ldloc.1
0x1740a  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1740f  newobj   instance void [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPIssuerNameAndNameIdMismatchException::.ctor()
0x17414  throw
0x17415  ldc.i4   0x7CC18C
0x1741a  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityBaseTokenHandler::get_Category()
0x1741f  ldc.i4   0xC8
0x17424  ldstr    aValidatedJsonT// "Validated json token issuer. TokenIssue"...
0x17429  ldc.i4.1
0x1742a  newarr   [mscorlib]System.Object
0x1742f  stloc.2
0x17430  ldloc.2
0x17431  ldc.i4.0
0x17432  ldarg.2
0x17433  stelem.ref
0x17434  ldloc.2
0x17435  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x1743a  ret
```
