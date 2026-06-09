# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadArrayStart

- ea: `0x2d8b0`
- end: `0x2d8e7`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadArrayStart`
- size: `55`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2e580`
- `0x2e800`
- `0x2e880`

## callees

- `0x16f10`
- `0x2d8b0`
- `0x2eb40`
- `0x30550`
- `0x30560`

## string_xrefs

- `0x2d8c0`: `JsonDataTypeNotMatch`

## pseudocode

```c

```

## disassembly

```asm
0x2d8b0  ldarg.0
0x2d8b1  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2d8b6  stloc.0
0x2d8b7  ldloc.0
0x2d8b8  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2d8bd  ldc.i4.2
0x2d8be  beq.s    loc_2D8E6
0x2d8c0  ldstr    aJsondatatypeno// "JsonDataTypeNotMatch"
0x2d8c5  ldc.i4.1
0x2d8c6  newarr   [mscorlib]System.Object
0x2d8cb  stloc.1
0x2d8cc  ldloc.1
0x2d8cd  ldc.i4.0
0x2d8ce  ldloc.0
0x2d8cf  callvirt instance int32 Token::get_Position()
0x2d8d4  box      [mscorlib]System.Int32
0x2d8d9  stelem.ref
0x2d8da  ldloc.1
0x2d8db  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2d8e0  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2d8e5  throw
0x2d8e6  ret
```
