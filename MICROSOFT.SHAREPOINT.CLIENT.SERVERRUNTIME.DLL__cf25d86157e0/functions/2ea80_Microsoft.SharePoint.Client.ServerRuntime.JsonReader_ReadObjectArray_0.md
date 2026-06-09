# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadObjectArray_0

- ea: `0x2ea80`
- end: `0x2eaf6`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadObjectArray_0`
- size: `118`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2e8e0`
- `0x2ea70`

## callees

- `0x16f10`
- `0x2d8f0`
- `0x2e8e0`
- `0x2ea80`
- `0x2eb00`
- `0x2eb40`
- `0x30550`
- `0x30560`

## string_xrefs

- `0x2ea9c`: `JsonDataTypeNotMatch`

## pseudocode

```c

```

## disassembly

```asm
0x2ea80  ldarg.0
0x2ea81  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadToken()
0x2ea86  stloc.0
0x2ea87  ldloc.0
0x2ea88  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2ea8d  ldc.i4.s 0xB
0x2ea8f  bne.un.s loc_2EA93
0x2ea91  ldnull
0x2ea92  ret
0x2ea93  ldloc.0
0x2ea94  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2ea99  ldc.i4.2
0x2ea9a  beq.s    loc_2EAC2
0x2ea9c  ldstr    aJsondatatypeno// "JsonDataTypeNotMatch"
0x2eaa1  ldc.i4.1
0x2eaa2  newarr   [mscorlib]System.Object
0x2eaa7  stloc.3
0x2eaa8  ldloc.3
0x2eaa9  ldc.i4.0
0x2eaaa  ldloc.0
0x2eaab  callvirt instance int32 Token::get_Position()
0x2eab0  box      [mscorlib]System.Int32
0x2eab5  stelem.ref
0x2eab6  ldloc.3
0x2eab7  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2eabc  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x2eac1  throw
0x2eac2  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<object>::.ctor()
0x2eac7  stloc.1
0x2eac8  br.s     loc_2EAD9
0x2eaca  ldarg.0
0x2eacb  ldarg.1
0x2eacc  call     instance object Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadObject(class [mscorlib]System.Type fallbackType)
0x2ead1  stloc.2
0x2ead2  ldloc.1
0x2ead3  ldloc.2
0x2ead4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<object>::Add(var<u1>)
0x2ead9  ldarg.0
0x2eada  call     instance class Token Microsoft.SharePoint.Client.ServerRuntime.JsonReader::PeekToken()
0x2eadf  dup
0x2eae0  stloc.0
0x2eae1  callvirt instance valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType Token::get_Type()
0x2eae6  ldc.i4.3
0x2eae7  bne.un.s loc_2EACA
0x2eae9  ldarg.0
0x2eaea  call     instance void Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadArrayEnd()
0x2eaef  ldloc.1
0x2eaf0  callvirt instance var<u1>[] class [mscorlib]System.Collections.Generic.List`1<object>::ToArray()
0x2eaf5  ret
```
