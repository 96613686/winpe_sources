# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadTokenTrue

- ea: `0x2f080`
- end: `0x2f111`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::ReadTokenTrue`
- size: `145`
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
- `0x2f080`
- `0x30530`
- `0x306c0`

## string_xrefs

- `0x2f0f0`: `JsonUnknownData`

## pseudocode

```c

```

## disassembly

```asm
0x2f080  ldarg.0
0x2f081  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2f086  callvirt instance int32 [mscorlib]System.IO.TextReader::Read()
0x2f08b  dup
0x2f08c  stloc.0
0x2f08d  ldc.i4.s 0x74
0x2f08f  bne.un.s loc_2F0F0
0x2f091  ldarg.0
0x2f092  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2f097  callvirt instance int32 [mscorlib]System.IO.TextReader::Read()
0x2f09c  dup
0x2f09d  stloc.0
0x2f09e  ldc.i4.s 0x72
0x2f0a0  bne.un.s loc_2F0F0
0x2f0a2  ldarg.0
0x2f0a3  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2f0a8  callvirt instance int32 [mscorlib]System.IO.TextReader::Read()
0x2f0ad  dup
0x2f0ae  stloc.0
0x2f0af  ldc.i4.s 0x75
0x2f0b1  bne.un.s loc_2F0F0
0x2f0b3  ldarg.0
0x2f0b4  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2f0b9  callvirt instance int32 [mscorlib]System.IO.TextReader::Read()
0x2f0be  dup
0x2f0bf  stloc.0
0x2f0c0  ldc.i4.s 0x65
0x2f0c2  bne.un.s loc_2F0F0
0x2f0c4  ldarg.0
0x2f0c5  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2f0ca  callvirt instance int32 [mscorlib]System.IO.TextReader::Peek()
0x2f0cf  stloc.0
0x2f0d0  ldarg.0
0x2f0d1  ldloc.0
0x2f0d2  call     instance bool Microsoft.SharePoint.Client.ServerRuntime.JsonReader::IsTokenEnd(int32 ch)
0x2f0d7  brfalse.s loc_2F0F0
0x2f0d9  ldc.i4.8
0x2f0da  ldarg.1
0x2f0db  newobj   instance void Token::.ctor(valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType tokenType, int32 position)
0x2f0e0  stloc.1
0x2f0e1  ldloc.1
0x2f0e2  ldc.i4.1
0x2f0e3  callvirt instance void Token::set_BoolValue(bool value)
0x2f0e8  ldarg.0
0x2f0e9  call     instance void Microsoft.SharePoint.Client.ServerRuntime.JsonReader::SkipToNextToken()
0x2f0ee  ldloc.1
0x2f0ef  ret
0x2f0f0  ldstr    aJsonunknowndat// "JsonUnknownData"
0x2f0f5  ldc.i4.1
0x2f0f6  newarr   [mscorlib]System.Object
0x2f0fb  stloc.2
0x2f0fc  ldloc.2
0x2f0fd  ldc.i4.0
0x2f0fe  ldarg.1
0x2f0ff  box      [mscorlib]System.Int32
0x2f104  stelem.ref
0x2f105  ldloc.2
0x2f106  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2f10b  newobj   instance void [mscorlib]System.FormatException::.ctor(string)
0x2f110  throw
```
