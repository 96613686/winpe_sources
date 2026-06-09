# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadDecimalArray

- ea: `0x2df40`
- end: `0x2dfb1`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadDecimalArray`
- size: `113`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2dfc0`

## callees

- `0x16f10`
- `0x2d530`
- `0x2d8f0`
- `0x2df40`
- `0x2eb00`
- `0x2eb40`
- `0x30550`
- `0x30560`

## string_xrefs

- `0x2df62`: `JsonDataTypeNotMatch`

## pseudocode

```c

```

## disassembly

```asm
0x2df40  ldarg.0
0x2df41  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2df46  stloc.0
0x2df47  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Decimal>::.ctor()
0x2df4c  stloc.1
0x2df4d  ldloc.0
0x2df4e  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2df53  ldc.i4.s 0xB
0x2df55  bne.un.s loc_2DF59
0x2df57  ldnull
0x2df58  ret
0x2df59  ldloc.0
0x2df5a  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2df5f  ldc.i4.2
0x2df60  beq.s    loc_2DF94
0x2df62  ldstr    aJsondatatypeno// "JsonDataTypeNotMatch"
0x2df67  ldc.i4.1
0x2df68  newarr   [mscorlib]System.Object
0x2df6d  stloc.2
0x2df6e  ldloc.2
0x2df6f  ldc.i4.0
0x2df70  ldloc.0
0x2df71  callvirt instance int32 Token::get_Position()
0x2df76  box      [mscorlib]System.Int32
0x2df7b  stelem.ref
0x2df7c  ldloc.2
0x2df7d  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2df82  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2df87  throw
0x2df88  ldloc.1
0x2df89  ldarg.0
0x2df8a  call     instance valuetype [mscorlib]System.Decimal Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadDecimal()
0x2df8f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Decimal>::Add(var<u1>)
0x2df94  ldarg.0
0x2df95  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::PeekToken()
0x2df9a  dup
0x2df9b  stloc.0
0x2df9c  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2dfa1  ldc.i4.3
0x2dfa2  bne.un.s loc_2DF88
0x2dfa4  ldarg.0
0x2dfa5  call     instance void Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadArrayEnd()
0x2dfaa  ldloc.1
0x2dfab  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<valuetype [mscorlib]System.Decimal>::ToArray()
0x2dfb0  ret
```
