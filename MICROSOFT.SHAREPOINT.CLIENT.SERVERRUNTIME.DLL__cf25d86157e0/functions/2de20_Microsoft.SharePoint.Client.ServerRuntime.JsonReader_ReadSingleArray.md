# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadSingleArray

- ea: `0x2de20`
- end: `0x2de91`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadSingleArray`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2dea0`

## callees

- `0x16f10`
- `0x2d440`
- `0x2d8f0`
- `0x2de20`
- `0x2eb00`
- `0x2eb40`
- `0x30550`
- `0x30560`

## string_xrefs

- `0x2de42`: `JsonDataTypeNotMatch`

## pseudocode

```c

```

## disassembly

```asm
0x2de20  ldarg.0
0x2de21  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2de26  stloc.0
0x2de27  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<float32>::.ctor()
0x2de2c  stloc.1
0x2de2d  ldloc.0
0x2de2e  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2de33  ldc.i4.s 0xB
0x2de35  bne.un.s loc_2DE39
0x2de37  ldnull
0x2de38  ret
0x2de39  ldloc.0
0x2de3a  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2de3f  ldc.i4.2
0x2de40  beq.s    loc_2DE74
0x2de42  ldstr    aJsondatatypeno// "JsonDataTypeNotMatch"
0x2de47  ldc.i4.1
0x2de48  newarr   [mscorlib]System.Object
0x2de4d  stloc.2
0x2de4e  ldloc.2
0x2de4f  ldc.i4.0
0x2de50  ldloc.0
0x2de51  callvirt instance int32 Token::get_Position()
0x2de56  box      [mscorlib]System.Int32
0x2de5b  stelem.ref
0x2de5c  ldloc.2
0x2de5d  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2de62  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2de67  throw
0x2de68  ldloc.1
0x2de69  ldarg.0
0x2de6a  call     instance float32 Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadSingle()
0x2de6f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<float32>::Add(var<u1>)
0x2de74  ldarg.0
0x2de75  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::PeekToken()
0x2de7a  dup
0x2de7b  stloc.0
0x2de7c  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2de81  ldc.i4.3
0x2de82  bne.un.s loc_2DE68
0x2de84  ldarg.0
0x2de85  call     instance void Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadArrayEnd()
0x2de8a  ldloc.1
0x2de8b  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<float32>::ToArray()
0x2de90  ret
```
