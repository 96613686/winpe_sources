# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadTokenFalse

- ea: `0x2f120`
- end: `0x2f1c2`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadTokenFalse`
- size: `162`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2ece0`

## callees

- `0x16f10`
- `0x2ec80`
- `0x2f050`
- `0x2f120`
- `0x30530`
- `0x306c0`

## string_xrefs

- `0x2f1a1`: `JsonUnknownData`

## pseudocode

```c

```

## disassembly

```asm
0x2f120  ldarg.0
0x2f121  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2f126  callvirt instance int32 [mscorlib]System.IO.TextReader::Read()
0x2f12b  dup
0x2f12c  stloc.0
0x2f12d  ldc.i4.s 0x66
0x2f12f  bne.un.s loc_2F1A1
0x2f131  ldarg.0
0x2f132  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2f137  callvirt instance int32 [mscorlib]System.IO.TextReader::Read()
0x2f13c  dup
0x2f13d  stloc.0
0x2f13e  ldc.i4.s 0x61
0x2f140  bne.un.s loc_2F1A1
0x2f142  ldarg.0
0x2f143  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2f148  callvirt instance int32 [mscorlib]System.IO.TextReader::Read()
0x2f14d  dup
0x2f14e  stloc.0
0x2f14f  ldc.i4.s 0x6C
0x2f151  bne.un.s loc_2F1A1
0x2f153  ldarg.0
0x2f154  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2f159  callvirt instance int32 [mscorlib]System.IO.TextReader::Read()
0x2f15e  dup
0x2f15f  stloc.0
0x2f160  ldc.i4.s 0x73
0x2f162  bne.un.s loc_2F1A1
0x2f164  ldarg.0
0x2f165  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2f16a  callvirt instance int32 [mscorlib]System.IO.TextReader::Read()
0x2f16f  dup
0x2f170  stloc.0
0x2f171  ldc.i4.s 0x65
0x2f173  bne.un.s loc_2F1A1
0x2f175  ldarg.0
0x2f176  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2f17b  callvirt instance int32 [mscorlib]System.IO.TextReader::Peek()
0x2f180  stloc.0
0x2f181  ldarg.0
0x2f182  ldloc.0
0x2f183  call     instance bool Microsoft.SharePoint.Client.ServerRuntime.JsonReader::IsTokenEnd(int32 ch)
0x2f188  brfalse.s loc_2F1A1
0x2f18a  ldc.i4.8
0x2f18b  ldarg.1
0x2f18c  newobj   instance void Token::.ctor(valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType tokenType, int32 position)
0x2f191  stloc.1
0x2f192  ldloc.1
0x2f193  ldc.i4.0
0x2f194  callvirt instance void Token::set_BoolValue(bool value)
0x2f199  ldarg.0
0x2f19a  call     instance void Microsoft.SharePoint.Client.ServerRuntime.JsonReader::SkipToNextToken()
0x2f19f  ldloc.1
0x2f1a0  ret
0x2f1a1  ldstr    aJsonunknowndat// "JsonUnknownData"
0x2f1a6  ldc.i4.1
0x2f1a7  newarr   [mscorlib]System.Object
0x2f1ac  stloc.2
0x2f1ad  ldloc.2
0x2f1ae  ldc.i4.0
0x2f1af  ldarg.1
0x2f1b0  box      [mscorlib]System.Int32
0x2f1b5  stelem.ref
0x2f1b6  ldloc.2
0x2f1b7  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2f1bc  newobj   instance void [mscorlib]System.FormatException::.ctor(string)
0x2f1c1  throw
```
