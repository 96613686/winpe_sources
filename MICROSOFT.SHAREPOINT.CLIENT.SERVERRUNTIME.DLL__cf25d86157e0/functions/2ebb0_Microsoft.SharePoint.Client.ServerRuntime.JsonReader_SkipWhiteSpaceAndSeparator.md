# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::SkipWhiteSpaceAndSeparator

- ea: `0x2ebb0`
- end: `0x2ec04`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::SkipWhiteSpaceAndSeparator`
- size: `84`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2ece0`

## callees

- `0x16f00`
- `0x17b40`
- `0x2ebb0`

## string_xrefs

- `0x2ebf3`: `JsonNotWellFormated`

## pseudocode

```c

```

## disassembly

```asm
0x2ebb0  ldc.i4.0
0x2ebb1  stloc.0
0x2ebb2  br.s     loc_2EBE0
0x2ebb4  ldloc.1
0x2ebb5  conv.u2
0x2ebb6  call     bool [mscorlib]System.Char::IsWhiteSpace(char)
0x2ebbb  brfalse.s loc_2EBCB
0x2ebbd  ldarg.0
0x2ebbe  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2ebc3  callvirt instance int32 Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader::Skip()
0x2ebc8  pop
0x2ebc9  br.s     loc_2EBE0
0x2ebcb  ldloc.0
0x2ebcc  brtrue.s loc_2EBF0
0x2ebce  ldloc.1
0x2ebcf  ldarg.1
0x2ebd0  bne.un.s loc_2EBF0
0x2ebd2  ldc.i4.1
0x2ebd3  stloc.0
0x2ebd4  ldarg.0
0x2ebd5  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2ebda  callvirt instance int32 Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader::Skip()
0x2ebdf  pop
0x2ebe0  ldarg.0
0x2ebe1  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2ebe6  callvirt instance int32 [mscorlib]System.IO.TextReader::Peek()
0x2ebeb  dup
0x2ebec  stloc.1
0x2ebed  ldc.i4.m1
0x2ebee  bne.un.s loc_2EBB4
0x2ebf0  ldloc.0
0x2ebf1  brtrue.s loc_2EC03
0x2ebf3  ldstr    aJsonnotwellfor// "JsonNotWellFormated"
0x2ebf8  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId)
0x2ebfd  newobj   instance void [mscorlib]System.FormatException::.ctor(string)
0x2ec02  throw
0x2ec03  ret
```
