# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::PeekName

- ea: `0x2d9b0`
- end: `0x2d9ee`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::PeekName`
- size: `62`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callees

- `0x16f10`
- `0x2d9b0`
- `0x2eb00`
- `0x30550`
- `0x30560`
- `0x30570`

## string_xrefs

- `0x2d9c8`: `JsonDataTypeNotMatch`

## pseudocode

```c

```

## disassembly

```asm
0x2d9b0  ldarg.0
0x2d9b1  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::PeekToken()
0x2d9b6  stloc.0
0x2d9b7  ldloc.0
0x2d9b8  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2d9bd  ldc.i4.s 0xC
0x2d9bf  bne.un.s loc_2D9C8
0x2d9c1  ldloc.0
0x2d9c2  callvirt instance string Token::get_StringValue()
0x2d9c7  ret
0x2d9c8  ldstr    aJsondatatypeno// "JsonDataTypeNotMatch"
0x2d9cd  ldc.i4.1
0x2d9ce  newarr   [mscorlib]System.Object
0x2d9d3  stloc.1
0x2d9d4  ldloc.1
0x2d9d5  ldc.i4.0
0x2d9d6  ldloc.0
0x2d9d7  callvirt instance int32 Token::get_Position()
0x2d9dc  box      [mscorlib]System.Int32
0x2d9e1  stelem.ref
0x2d9e2  ldloc.1
0x2d9e3  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2d9e8  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2d9ed  throw
```
