# Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::ValidateProofToken

- ea: `0x186e0`
- end: `0x187c6`
- name: `Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::ValidateProofToken`
- size: `230`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x183e0`

## callees

- `0x18180`
- `0x186e0`
- `0x18fe0`
- `0x190c0`

## string_xrefs

- `0x186f9`: `proofToken`
- `0x186ef`: `The proofToken is null.`
- `0x18748`: `Proof token validation failed because timestamp is invalid. TimeStamp: '{0}'.`
- `0x18776`: `ProofTokenValidationFailed`
- `0x187af`: `ProofTokenValidationFailed`
- `0x187a0`: `Proof token signature validation failed.`

## pseudocode

```c

```

## disassembly

```asm
0x186e0  ldarg.1
0x186e1  brtrue.s loc_18704
0x186e3  ldc.i4   0x650412
0x186e8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::get_Category()
0x186ed  ldc.i4.s 0xA
0x186ef  ldstr    aTheProoftokenI// "The proofToken is null."
0x186f4  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x186f9  ldstr    aProoftoken_1// "proofToken"
0x186fe  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x18703  throw
0x18704  ldarg.1
0x18705  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.IdentityModel.SPProofTokenContext::get_Timestamp()
0x1870a  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x1870f  ldsfld   valuetype [mscorlib]System.TimeSpan [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPLoopbackTokenConstants::TimestampMaximumSkew
0x18714  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x18719  call     bool [mscorlib]System.DateTime::op_LessThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x1871e  brtrue.s loc_1873C
0x18720  ldarg.1
0x18721  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.IdentityModel.SPProofTokenContext::get_Timestamp()
0x18726  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x1872b  ldsfld   valuetype [mscorlib]System.TimeSpan [Microsoft.SharePoint]Microsoft.SharePoint.ApplicationServices.SPLoopbackTokenConstants::TimestampMaximumSkew
0x18730  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::op_Addition(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.TimeSpan)
0x18735  call     bool [mscorlib]System.DateTime::op_GreaterThan(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x1873a  brfalse.s loc_1878C
0x1873c  ldc.i4   0x14211E
0x18741  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::get_Category()
0x18746  ldc.i4.s 0x64
0x18748  ldstr    aProofTokenVali// "Proof token validation failed because t"...
0x1874d  ldc.i4.1
0x1874e  newarr   [mscorlib]System.Object
0x18753  stloc.0
0x18754  ldloc.0
0x18755  ldc.i4.0
0x18756  ldarg.1
0x18757  callvirt instance valuetype [mscorlib]System.DateTime Microsoft.SharePoint.IdentityModel.SPProofTokenContext::get_Timestamp()
0x1875c  stloc.1
0x1875d  ldloca.s 1
0x1875f  constrained. [mscorlib]System.DateTime
0x18765  callvirt instance string [mscorlib]System.Object::ToString()
0x1876a  stelem.ref
0x1876b  ldloc.0
0x1876c  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x18771  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x18776  ldstr    aProoftokenvali// "ProofTokenValidationFailed"
0x1877b  ldc.i4.0
0x1877c  newarr   [mscorlib]System.Object
0x18781  call     string [Microsoft.SharePoint]Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo, string, object[])
0x18786  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenException::.ctor(string)
0x1878b  throw
0x1878c  ldarg.1
0x1878d  callvirt instance bool Microsoft.SharePoint.IdentityModel.SPProofTokenContext::TryVerifySignature()
0x18792  brtrue.s loc_187C5
0x18794  ldc.i4   0x14211F
0x18799  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPJsonWebSecurityTokenHandler::get_Category()
0x1879e  ldc.i4.s 0x64
0x187a0  ldstr    aProofTokenSign// "Proof token signature validation failed"...
0x187a5  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x187aa  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InvariantCulture()
0x187af  ldstr    aProoftokenvali// "ProofTokenValidationFailed"
0x187b4  ldc.i4.0
0x187b5  newarr   [mscorlib]System.Object
0x187ba  call     string [Microsoft.SharePoint]Microsoft.SharePoint.SPResource::GetString(class [mscorlib]System.Globalization.CultureInfo, string, object[])
0x187bf  newobj   instance void [System.IdentityModel]System.IdentityModel.Tokens.SecurityTokenException::.ctor(string)
0x187c4  throw
0x187c5  ret
```
