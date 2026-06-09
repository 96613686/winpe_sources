# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadInt16

- ea: `0x2d250`
- end: `0x2d28e`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadInt16`
- size: `62`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2d290`
- `0x2dac0`

## callees

- `0x16f10`
- `0x2d250`
- `0x2eb40`
- `0x30550`
- `0x30560`
- `0x305e0`

## string_xrefs

- `0x2d268`: `JsonDataTypeNotMatch`

## pseudocode

```c

```

## disassembly

```asm
0x2d250  ldarg.0
0x2d251  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2d256  stloc.0
0x2d257  ldloc.0
0x2d258  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2d25d  ldc.i4.5
0x2d25e  bne.un.s loc_2D268
0x2d260  ldloc.0
0x2d261  callvirt instance int64 Token::get_LongValue()
0x2d266  conv.i2
0x2d267  ret
0x2d268  ldstr    aJsondatatypeno// "JsonDataTypeNotMatch"
0x2d26d  ldc.i4.1
0x2d26e  newarr   [mscorlib]System.Object
0x2d273  stloc.1
0x2d274  ldloc.1
0x2d275  ldc.i4.0
0x2d276  ldloc.0
0x2d277  callvirt instance int32 Token::get_Position()
0x2d27c  box      [mscorlib]System.Int32
0x2d281  stelem.ref
0x2d282  ldloc.1
0x2d283  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2d288  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2d28d  throw
```
