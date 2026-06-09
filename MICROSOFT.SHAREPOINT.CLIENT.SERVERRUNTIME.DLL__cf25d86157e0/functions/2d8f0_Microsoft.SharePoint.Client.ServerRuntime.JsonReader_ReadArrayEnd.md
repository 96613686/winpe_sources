# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadArrayEnd

- ea: `0x2d8f0`
- end: `0x2d927`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadArrayEnd`
- size: `55`
- prototype: ``
- caller_count: `19`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2da30`
- `0x2dac0`
- `0x2db50`
- `0x2dbe0`
- `0x2dc70`
- `0x2dd00`
- `0x2dd90`
- `0x2de20`
- `0x2deb0`
- `0x2df40`
- `0x2dfd0`
- `0x2e060`
- `0x2e0f0`
- `0x2e180`
- `0x2e210`
- `0x2e580`
- `0x2e800`
- `0x2e880`
- `0x2ea80`

## callees

- `0x16f10`
- `0x2d8f0`
- `0x2eb40`
- `0x30550`
- `0x30560`

## string_xrefs

- `0x2d900`: `JsonDataTypeNotMatch`

## pseudocode

```c

```

## disassembly

```asm
0x2d8f0  ldarg.0
0x2d8f1  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2d8f6  stloc.0
0x2d8f7  ldloc.0
0x2d8f8  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2d8fd  ldc.i4.3
0x2d8fe  beq.s    loc_2D926
0x2d900  ldstr    aJsondatatypeno// "JsonDataTypeNotMatch"
0x2d905  ldc.i4.1
0x2d906  newarr   [mscorlib]System.Object
0x2d90b  stloc.1
0x2d90c  ldloc.1
0x2d90d  ldc.i4.0
0x2d90e  ldloc.0
0x2d90f  callvirt instance int32 Token::get_Position()
0x2d914  box      [mscorlib]System.Int32
0x2d919  stelem.ref
0x2d91a  ldloc.1
0x2d91b  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2d920  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2d925  throw
0x2d926  ret
```
