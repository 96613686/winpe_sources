# Microsoft.SharePoint.IdentityModel.SPAudienceValidatingIdentityProofTokenHandler::ValidateToken

- ea: `0x86d0`
- end: `0x8738`
- name: `Microsoft.SharePoint.IdentityModel.SPAudienceValidatingIdentityProofTokenHandler::ValidateToken`
- size: `104`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x86a0`
- `0x86d0`
- `0x8740`

## string_xrefs

- `0x86e9`: `token`
- `0x86df`: `The token is null.`
- `0x871b`: `The token is not an SPIdentityProofToken. TokenType: '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0x86d0  ldarg.1
0x86d1  brtrue.s loc_86F4
0x86d3  ldc.i4   0x7CC160
0x86d8  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPAudienceValidatingIdentityProofTokenHandler::get_Category()
0x86dd  ldc.i4.s 0xA
0x86df  ldstr    aTheTokenIsNull// "The token is null."
0x86e4  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x86e9  ldstr    aToken// "token"
0x86ee  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x86f3  throw
0x86f4  ldarg.0
0x86f5  ldarg.1
0x86f6  call     instance class [Microsoft.IdentityModel]Microsoft.IdentityModel.Claims.ClaimsIdentityCollection [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPIdentityProofTokenHandler::ValidateToken(class [System.IdentityModel]System.IdentityModel.Tokens.SecurityToken)
0x86fb  stloc.0
0x86fc  ldarg.1
0x86fd  isinst   [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPIdentityProofToken
0x8702  stloc.1
0x8703  ldloc.1
0x8704  brfalse.s loc_870F
0x8706  ldarg.0
0x8707  ldloc.1
0x8708  call     instance void Microsoft.SharePoint.IdentityModel.SPAudienceValidatingIdentityProofTokenHandler::ValidateAudience(class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPIdentityProofToken identityProofToken)
0x870d  br.s     loc_8736
0x870f  ldc.i4   0x7CC161
0x8714  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPAudienceValidatingIdentityProofTokenHandler::get_Category()
0x8719  ldc.i4.s 0x32
0x871b  ldstr    aTheTokenIsNotA// "The token is not an SPIdentityProofToke"...
0x8720  ldc.i4.1
0x8721  newarr   [mscorlib]System.Object
0x8726  stloc.2
0x8727  ldloc.2
0x8728  ldc.i4.0
0x8729  ldarg.1
0x872a  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x872f  stelem.ref
0x8730  ldloc.2
0x8731  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x8736  ldloc.0
0x8737  ret
```
