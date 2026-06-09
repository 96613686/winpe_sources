# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadTokenNull

- ea: `0x2f1d0`
- end: `0x2f25b`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadTokenNull`
- size: `139`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2ece0`

## callees

- `0x16f10`
- `0x2ec80`
- `0x2f050`
- `0x2f1d0`
- `0x30530`

## string_xrefs

- `0x2f23a`: `JsonUnknownData`

## pseudocode

```c

```

## disassembly

```asm
0x2f1d0  ldarg.0
0x2f1d1  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2f1d6  callvirt instance int32 [mscorlib]System.IO.TextReader::Read()
0x2f1db  dup
0x2f1dc  stloc.0
0x2f1dd  ldc.i4.s 0x6E
0x2f1df  bne.un.s loc_2F23A
0x2f1e1  ldarg.0
0x2f1e2  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2f1e7  callvirt instance int32 [mscorlib]System.IO.TextReader::Read()
0x2f1ec  dup
0x2f1ed  stloc.0
0x2f1ee  ldc.i4.s 0x75
0x2f1f0  bne.un.s loc_2F23A
0x2f1f2  ldarg.0
0x2f1f3  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2f1f8  callvirt instance int32 [mscorlib]System.IO.TextReader::Read()
0x2f1fd  dup
0x2f1fe  stloc.0
0x2f1ff  ldc.i4.s 0x6C
0x2f201  bne.un.s loc_2F23A
0x2f203  ldarg.0
0x2f204  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2f209  callvirt instance int32 [mscorlib]System.IO.TextReader::Read()
0x2f20e  dup
0x2f20f  stloc.0
0x2f210  ldc.i4.s 0x6C
0x2f212  bne.un.s loc_2F23A
0x2f214  ldarg.0
0x2f215  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2f21a  callvirt instance int32 [mscorlib]System.IO.TextReader::Peek()
0x2f21f  stloc.0
0x2f220  ldarg.0
0x2f221  ldloc.0
0x2f222  call     instance bool Microsoft.SharePoint.Client.ServerRuntime.JsonReader::IsTokenEnd(int32 ch)
0x2f227  brfalse.s loc_2F23A
0x2f229  ldc.i4.s 0xB
0x2f22b  ldarg.1
0x2f22c  newobj   instance void Token::.ctor(valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType tokenType, int32 position)
0x2f231  stloc.1
0x2f232  ldarg.0
0x2f233  call     instance void Microsoft.SharePoint.Client.ServerRuntime.JsonReader::SkipToNextToken()
0x2f238  ldloc.1
0x2f239  ret
0x2f23a  ldstr    aJsonunknowndat// "JsonUnknownData"
0x2f23f  ldc.i4.1
0x2f240  newarr   [mscorlib]System.Object
0x2f245  stloc.2
0x2f246  ldloc.2
0x2f247  ldc.i4.0
0x2f248  ldarg.1
0x2f249  box      [mscorlib]System.Int32
0x2f24e  stelem.ref
0x2f24f  ldloc.2
0x2f250  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2f255  newobj   instance void [mscorlib]System.FormatException::.ctor(string)
0x2f25a  throw
```
