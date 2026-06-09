# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadUInt64Array

- ea: `0x2dd90`
- end: `0x2de01`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadUInt64Array`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2de10`

## callees

- `0x16f10`
- `0x2d3e0`
- `0x2d8f0`
- `0x2dd90`
- `0x2eb00`
- `0x2eb40`
- `0x30550`
- `0x30560`

## string_xrefs

- `0x2ddb2`: `JsonDataTypeNotMatch`

## pseudocode

```c

```

## disassembly

```asm
0x2dd90  ldarg.0
0x2dd91  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2dd96  stloc.0
0x2dd97  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<unsigned int64>::.ctor()
0x2dd9c  stloc.1
0x2dd9d  ldloc.0
0x2dd9e  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2dda3  ldc.i4.s 0xB
0x2dda5  bne.un.s loc_2DDA9
0x2dda7  ldnull
0x2dda8  ret
0x2dda9  ldloc.0
0x2ddaa  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2ddaf  ldc.i4.2
0x2ddb0  beq.s    loc_2DDE4
0x2ddb2  ldstr    aJsondatatypeno// "JsonDataTypeNotMatch"
0x2ddb7  ldc.i4.1
0x2ddb8  newarr   [mscorlib]System.Object
0x2ddbd  stloc.2
0x2ddbe  ldloc.2
0x2ddbf  ldc.i4.0
0x2ddc0  ldloc.0
0x2ddc1  callvirt instance int32 Token::get_Position()
0x2ddc6  box      [mscorlib]System.Int32
0x2ddcb  stelem.ref
0x2ddcc  ldloc.2
0x2ddcd  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2ddd2  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2ddd7  throw
0x2ddd8  ldloc.1
0x2ddd9  ldarg.0
0x2ddda  call     instance unsigned int64 Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadUInt64()
0x2dddf  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<unsigned int64>::Add(var<u1>)
0x2dde4  ldarg.0
0x2dde5  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::PeekToken()
0x2ddea  dup
0x2ddeb  stloc.0
0x2ddec  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2ddf1  ldc.i4.3
0x2ddf2  bne.un.s loc_2DDD8
0x2ddf4  ldarg.0
0x2ddf5  call     instance void Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadArrayEnd()
0x2ddfa  ldloc.1
0x2ddfb  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<unsigned int64>::ToArray()
0x2de00  ret
```
