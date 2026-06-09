# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadByte

- ea: `0x2d1a0`
- end: `0x2d1de`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadByte`
- size: `62`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2d1e0`

## callees

- `0x16f10`
- `0x2d1a0`
- `0x2eb40`
- `0x30550`
- `0x30560`
- `0x305e0`

## string_xrefs

- `0x2d1b8`: `JsonDataTypeNotMatch`

## pseudocode

```c

```

## disassembly

```asm
0x2d1a0  ldarg.0
0x2d1a1  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2d1a6  stloc.0
0x2d1a7  ldloc.0
0x2d1a8  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2d1ad  ldc.i4.5
0x2d1ae  bne.un.s loc_2D1B8
0x2d1b0  ldloc.0
0x2d1b1  callvirt instance int64 Token::get_LongValue()
0x2d1b6  conv.u1
0x2d1b7  ret
0x2d1b8  ldstr    aJsondatatypeno// "JsonDataTypeNotMatch"
0x2d1bd  ldc.i4.1
0x2d1be  newarr   [mscorlib]System.Object
0x2d1c3  stloc.1
0x2d1c4  ldloc.1
0x2d1c5  ldc.i4.0
0x2d1c6  ldloc.0
0x2d1c7  callvirt instance int32 Token::get_Position()
0x2d1cc  box      [mscorlib]System.Int32
0x2d1d1  stelem.ref
0x2d1d2  ldloc.1
0x2d1d3  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2d1d8  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2d1dd  throw
```
