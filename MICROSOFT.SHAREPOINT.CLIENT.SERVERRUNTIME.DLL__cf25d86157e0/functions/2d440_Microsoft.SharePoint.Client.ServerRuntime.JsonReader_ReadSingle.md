# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadSingle

- ea: `0x2d440`
- end: `0x2d4a1`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadSingle`
- size: `97`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2d4b0`
- `0x2de20`

## callees

- `0x16f10`
- `0x2d440`
- `0x2eb40`
- `0x30550`
- `0x30560`
- `0x305e0`
- `0x30620`
- `0x30660`

## string_xrefs

- `0x2d47b`: `JsonDataTypeNotMatch`

## pseudocode

```c

```

## disassembly

```asm
0x2d440  ldarg.0
0x2d441  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2d446  stloc.0
0x2d447  ldloc.0
0x2d448  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2d44d  ldc.i4.5
0x2d44e  bne.un.s loc_2D458
0x2d450  ldloc.0
0x2d451  callvirt instance int64 Token::get_LongValue()
0x2d456  conv.r4
0x2d457  ret
0x2d458  ldloc.0
0x2d459  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2d45e  ldc.i4.6
0x2d45f  bne.un.s loc_2D46A
0x2d461  ldloc.0
0x2d462  callvirt instance unsigned int64 Token::get_ULongValue()
0x2d467  conv.r.un
0x2d468  conv.r4
0x2d469  ret
0x2d46a  ldloc.0
0x2d46b  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2d470  ldc.i4.7
0x2d471  bne.un.s loc_2D47B
0x2d473  ldloc.0
0x2d474  callvirt instance float64 Token::get_DoubleValue()
0x2d479  conv.r4
0x2d47a  ret
0x2d47b  ldstr    aJsondatatypeno// "JsonDataTypeNotMatch"
0x2d480  ldc.i4.1
0x2d481  newarr   [mscorlib]System.Object
0x2d486  stloc.1
0x2d487  ldloc.1
0x2d488  ldc.i4.0
0x2d489  ldloc.0
0x2d48a  callvirt instance int32 Token::get_Position()
0x2d48f  box      [mscorlib]System.Int32
0x2d494  stelem.ref
0x2d495  ldloc.1
0x2d496  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2d49b  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2d4a0  throw
```
