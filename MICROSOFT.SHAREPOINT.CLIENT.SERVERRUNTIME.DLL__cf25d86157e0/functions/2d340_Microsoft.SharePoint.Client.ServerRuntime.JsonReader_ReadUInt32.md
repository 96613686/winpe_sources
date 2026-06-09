# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadUInt32

- ea: `0x2d340`
- end: `0x2d37e`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadUInt32`
- size: `62`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2d380`
- `0x2dc70`

## callees

- `0x16f10`
- `0x2d340`
- `0x2eb40`
- `0x30550`
- `0x30560`
- `0x305e0`

## string_xrefs

- `0x2d358`: `JsonDataTypeNotMatch`

## pseudocode

```c

```

## disassembly

```asm
0x2d340  ldarg.0
0x2d341  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2d346  stloc.0
0x2d347  ldloc.0
0x2d348  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2d34d  ldc.i4.5
0x2d34e  bne.un.s loc_2D358
0x2d350  ldloc.0
0x2d351  callvirt instance int64 Token::get_LongValue()
0x2d356  conv.u4
0x2d357  ret
0x2d358  ldstr    aJsondatatypeno// "JsonDataTypeNotMatch"
0x2d35d  ldc.i4.1
0x2d35e  newarr   [mscorlib]System.Object
0x2d363  stloc.1
0x2d364  ldloc.1
0x2d365  ldc.i4.0
0x2d366  ldloc.0
0x2d367  callvirt instance int32 Token::get_Position()
0x2d36c  box      [mscorlib]System.Int32
0x2d371  stelem.ref
0x2d372  ldloc.1
0x2d373  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2d378  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2d37d  throw
```
