# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::TryReadStreamLink

- ea: `0x2fb90`
- end: `0x2fc85`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::TryReadStreamLink`
- size: `245`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2ece0`

## callees

- `0x16f10`
- `0x178e0`
- `0x17b50`
- `0x2ec80`
- `0x2fb90`
- `0x2fc90`
- `0x30530`
- `0x305b0`

## string_xrefs

- `0x2fc5f`: `JsonNotWellFormated`

## pseudocode

```c

```

## disassembly

```asm
0x2fb90  ldnull
0x2fb91  stloc.1
0x2fb92  ldc.i4.0
0x2fb93  stloc.2
0x2fb94  br.s     loc_2FB9A
0x2fb96  ldloc.2
0x2fb97  ldc.i4.1
0x2fb98  add
0x2fb99  stloc.2
0x2fb9a  ldloc.2
0x2fb9b  ldsfld   int32 Microsoft.SharePoint.Client.ServerRuntime.JsonReader::StreamLinkPrefixLength
0x2fba0  bge.s    loc_2FBBB
0x2fba2  ldarg.0
0x2fba3  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2fba8  ldloc.2
0x2fba9  callvirt instance int32 Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader::Peek(int32 position)
0x2fbae  ldstr    aBinary// "\"\\/Binary("
0x2fbb3  ldloc.2
0x2fbb4  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x2fbb9  beq.s    loc_2FB96
0x2fbbb  ldloc.2
0x2fbbc  ldsfld   int32 Microsoft.SharePoint.Client.ServerRuntime.JsonReader::StreamLinkPrefixLength
0x2fbc1  bne.un   loc_2FC83
0x2fbc6  ldc.i4.s 0xE
0x2fbc8  ldarg.1
0x2fbc9  newobj   instance void Token::.ctor(valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType tokenType, int32 position)
0x2fbce  stloc.1
0x2fbcf  ldarg.0
0x2fbd0  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2fbd5  ldsfld   int32 Microsoft.SharePoint.Client.ServerRuntime.JsonReader::StreamLinkPrefixLength
0x2fbda  callvirt instance int32 Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader::Skip(int32 count)
0x2fbdf  pop
0x2fbe0  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x2fbe5  stloc.3
0x2fbe6  br.s     loc_2FBF1
0x2fbe8  ldloc.3
0x2fbe9  ldloc.0
0x2fbea  conv.u2
0x2fbeb  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x2fbf0  pop
0x2fbf1  ldarg.0
0x2fbf2  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2fbf7  callvirt instance int32 [mscorlib]System.IO.TextReader::Read()
0x2fbfc  dup
0x2fbfd  stloc.0
0x2fbfe  ldc.i4.m1
0x2fbff  beq.s    loc_2FC06
0x2fc01  ldloc.0
0x2fc02  ldc.i4.s 0x29
0x2fc04  bne.un.s loc_2FBE8
0x2fc06  ldloc.0
0x2fc07  ldc.i4.s 0x29
0x2fc09  bne.un.s loc_2FC5F
0x2fc0b  ldarg.0
0x2fc0c  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2fc11  callvirt instance int32 [mscorlib]System.IO.TextReader::Read()
0x2fc16  ldc.i4.s 0x5C
0x2fc18  bne.un.s loc_2FC5F
0x2fc1a  ldarg.0
0x2fc1b  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2fc20  callvirt instance int32 [mscorlib]System.IO.TextReader::Read()
0x2fc25  ldc.i4.s 0x2F
0x2fc27  bne.un.s loc_2FC5F
0x2fc29  ldarg.0
0x2fc2a  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2fc2f  callvirt instance int32 [mscorlib]System.IO.TextReader::Read()
0x2fc34  ldc.i4.s 0x22
0x2fc36  bne.un.s loc_2FC5F
0x2fc38  ldloc.3
0x2fc39  callvirt instance string [mscorlib]System.Object::ToString()
0x2fc3e  stloc.s  4
0x2fc40  ldloc.s  4
0x2fc42  call     string [System.Web]System.Web.HttpUtility::UrlDecode(string)
0x2fc47  stloc.s  4
0x2fc49  ldloc.1
0x2fc4a  ldloc.s  4
0x2fc4c  callvirt instance void Token::set_StringValue(string value)
0x2fc51  ldarg.0
0x2fc52  call     instance void Microsoft.SharePoint.Client.ServerRuntime.JsonReader::SkipToNextToken()
0x2fc57  ldarg.0
0x2fc58  call     instance void Microsoft.SharePoint.Client.ServerRuntime.JsonReader::IncreaseObjectCount()
0x2fc5d  ldloc.1
0x2fc5e  ret
0x2fc5f  ldstr    aJsonnotwellfor// "JsonNotWellFormated"
0x2fc64  ldc.i4.1
0x2fc65  newarr   [mscorlib]System.Object
0x2fc6a  stloc.s  5
0x2fc6c  ldloc.s  5
0x2fc6e  ldc.i4.0
0x2fc6f  ldarg.1
0x2fc70  box      [mscorlib]System.Int32
0x2fc75  stelem.ref
0x2fc76  ldloc.s  5
0x2fc78  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2fc7d  newobj   instance void [mscorlib]System.FormatException::.ctor(string)
0x2fc82  throw
0x2fc83  ldloc.1
0x2fc84  ret
```
