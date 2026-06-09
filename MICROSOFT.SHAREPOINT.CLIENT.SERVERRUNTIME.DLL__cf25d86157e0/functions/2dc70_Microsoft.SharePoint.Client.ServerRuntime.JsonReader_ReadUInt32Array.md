# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadUInt32Array

- ea: `0x2dc70`
- end: `0x2dce1`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadUInt32Array`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2dcf0`

## callees

- `0x16f10`
- `0x2d340`
- `0x2d8f0`
- `0x2dc70`
- `0x2eb00`
- `0x2eb40`
- `0x30550`
- `0x30560`

## string_xrefs

- `0x2dc92`: `JsonDataTypeNotMatch`

## pseudocode

```c

```

## disassembly

```asm
0x2dc70  ldarg.0
0x2dc71  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2dc76  stloc.0
0x2dc77  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<unsigned int32>::.ctor()
0x2dc7c  stloc.1
0x2dc7d  ldloc.0
0x2dc7e  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2dc83  ldc.i4.s 0xB
0x2dc85  bne.un.s loc_2DC89
0x2dc87  ldnull
0x2dc88  ret
0x2dc89  ldloc.0
0x2dc8a  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2dc8f  ldc.i4.2
0x2dc90  beq.s    loc_2DCC4
0x2dc92  ldstr    aJsondatatypeno// "JsonDataTypeNotMatch"
0x2dc97  ldc.i4.1
0x2dc98  newarr   [mscorlib]System.Object
0x2dc9d  stloc.2
0x2dc9e  ldloc.2
0x2dc9f  ldc.i4.0
0x2dca0  ldloc.0
0x2dca1  callvirt instance int32 Token::get_Position()
0x2dca6  box      [mscorlib]System.Int32
0x2dcab  stelem.ref
0x2dcac  ldloc.2
0x2dcad  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2dcb2  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2dcb7  throw
0x2dcb8  ldloc.1
0x2dcb9  ldarg.0
0x2dcba  call     instance unsigned int32 Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadUInt32()
0x2dcbf  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<unsigned int32>::Add(var<u1>)
0x2dcc4  ldarg.0
0x2dcc5  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::PeekToken()
0x2dcca  dup
0x2dccb  stloc.0
0x2dccc  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2dcd1  ldc.i4.3
0x2dcd2  bne.un.s loc_2DCB8
0x2dcd4  ldarg.0
0x2dcd5  call     instance void Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadArrayEnd()
0x2dcda  ldloc.1
0x2dcdb  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<unsigned int32>::ToArray()
0x2dce0  ret
```
