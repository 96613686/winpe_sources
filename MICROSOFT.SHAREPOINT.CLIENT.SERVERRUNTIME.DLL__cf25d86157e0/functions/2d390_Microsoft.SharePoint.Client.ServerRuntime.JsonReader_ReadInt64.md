# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadInt64

- ea: `0x2d390`
- end: `0x2d3cd`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadInt64`
- size: `61`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2d3d0`
- `0x2dd00`

## callees

- `0x16f10`
- `0x2d390`
- `0x2eb40`
- `0x30550`
- `0x30560`
- `0x305e0`

## string_xrefs

- `0x2d3a7`: `JsonDataTypeNotMatch`

## pseudocode

```c

```

## disassembly

```asm
0x2d390  ldarg.0
0x2d391  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2d396  stloc.0
0x2d397  ldloc.0
0x2d398  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2d39d  ldc.i4.5
0x2d39e  bne.un.s loc_2D3A7
0x2d3a0  ldloc.0
0x2d3a1  callvirt instance int64 Token::get_LongValue()
0x2d3a6  ret
0x2d3a7  ldstr    aJsondatatypeno// "JsonDataTypeNotMatch"
0x2d3ac  ldc.i4.1
0x2d3ad  newarr   [mscorlib]System.Object
0x2d3b2  stloc.1
0x2d3b3  ldloc.1
0x2d3b4  ldc.i4.0
0x2d3b5  ldloc.0
0x2d3b6  callvirt instance int32 Token::get_Position()
0x2d3bb  box      [mscorlib]System.Int32
0x2d3c0  stelem.ref
0x2d3c1  ldloc.1
0x2d3c2  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2d3c7  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2d3cc  throw
```
