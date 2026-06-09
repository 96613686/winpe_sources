# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadUInt16

- ea: `0x2d2a0`
- end: `0x2d2de`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadUInt16`
- size: `62`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2d2e0`
- `0x2db50`

## callees

- `0x16f10`
- `0x2d2a0`
- `0x2eb40`
- `0x30550`
- `0x30560`
- `0x305e0`

## string_xrefs

- `0x2d2b8`: `JsonDataTypeNotMatch`

## pseudocode

```c

```

## disassembly

```asm
0x2d2a0  ldarg.0
0x2d2a1  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2d2a6  stloc.0
0x2d2a7  ldloc.0
0x2d2a8  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2d2ad  ldc.i4.5
0x2d2ae  bne.un.s loc_2D2B8
0x2d2b0  ldloc.0
0x2d2b1  callvirt instance int64 Token::get_LongValue()
0x2d2b6  conv.u2
0x2d2b7  ret
0x2d2b8  ldstr    aJsondatatypeno// "JsonDataTypeNotMatch"
0x2d2bd  ldc.i4.1
0x2d2be  newarr   [mscorlib]System.Object
0x2d2c3  stloc.1
0x2d2c4  ldloc.1
0x2d2c5  ldc.i4.0
0x2d2c6  ldloc.0
0x2d2c7  callvirt instance int32 Token::get_Position()
0x2d2cc  box      [mscorlib]System.Int32
0x2d2d1  stelem.ref
0x2d2d2  ldloc.1
0x2d2d3  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2d2d8  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2d2dd  throw
```
