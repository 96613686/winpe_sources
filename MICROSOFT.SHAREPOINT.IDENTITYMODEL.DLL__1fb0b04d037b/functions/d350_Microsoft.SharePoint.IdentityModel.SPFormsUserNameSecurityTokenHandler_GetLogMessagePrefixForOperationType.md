# Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::GetLogMessagePrefixForOperationType

- ea: `0xd350`
- end: `0xd3b8`
- name: `Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::GetLogMessagePrefixForOperationType`
- size: `104`
- prototype: ``
- caller_count: `7`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0xd2c0`
- `0xd400`
- `0xd760`
- `0xd8f0`
- `0xda00`
- `0xdb40`
- `0xdb80`

## callees

- `0xd240`
- `0xd350`

## string_xrefs

- `0xd364`: `Token Handler: Claims Forms Sign-In: `
- `0xd36c`: `Token Handler: Claims Forms Rebuild: `
- `0xd380`: `Token Handler: Unkown operation type found. Type: '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0xd350  ldnull
0xd351  stloc.0
0xd352  ldarg.1
0xd353  stloc.1
0xd354  ldloc.1
0xd355  switch   loc_D364, loc_D36C
0xd362  br.s     loc_D374
0xd364  ldstr    aTokenHandlerCl// "Token Handler: Claims Forms Sign-In: "
0xd369  stloc.0
0xd36a  br.s     loc_D3B6
0xd36c  ldstr    aTokenHandlerCl_0// "Token Handler: Claims Forms Rebuild: "
0xd371  stloc.0
0xd372  br.s     loc_D3B6
0xd374  ldc.i4   0x15D60B
0xd379  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.IdentityModel.SPFormsUserNameSecurityTokenHandler::get_Category()
0xd37e  ldc.i4.s 0xA
0xd380  ldstr    aTokenHandlerUn// "Token Handler: Unkown operation type fo"...
0xd385  ldc.i4.1
0xd386  newarr   [mscorlib]System.Object
0xd38b  stloc.2
0xd38c  ldloc.2
0xd38d  ldc.i4.0
0xd38e  ldarg.1
0xd38f  box      Microsoft.SharePoint.IdentityModel.SPFormOperation
0xd394  stelem.ref
0xd395  ldloc.2
0xd396  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0xd39b  ldstr    aArgumentenumun// "ArgumentEnumUnsupportedValue"
0xd3a0  ldc.i4.0
0xd3a1  newarr   [mscorlib]System.Object
0xd3a6  call     string [Microsoft.SharePoint]Microsoft.SharePoint.SPResource::GetString(string, object[])
0xd3ab  ldstr    aOperationtype// "operationType"
0xd3b0  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0xd3b5  throw
0xd3b6  ldloc.0
0xd3b7  ret
```
