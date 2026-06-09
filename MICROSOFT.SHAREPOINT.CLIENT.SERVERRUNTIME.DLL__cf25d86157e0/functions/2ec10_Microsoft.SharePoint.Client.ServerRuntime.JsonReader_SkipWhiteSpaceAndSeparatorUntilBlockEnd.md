# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::SkipWhiteSpaceAndSeparatorUntilBlockEnd

- ea: `0x2ec10`
- end: `0x2ec73`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::SkipWhiteSpaceAndSeparatorUntilBlockEnd`
- size: `99`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2ec80`

## callees

- `0x16f00`
- `0x17b40`
- `0x2ec10`

## string_xrefs

- `0x2ec62`: `JsonNotWellFormated`

## pseudocode

```c

```

## disassembly

```asm
0x2ec10  ldc.i4.0
0x2ec11  stloc.0
0x2ec12  ldc.i4.0
0x2ec13  stloc.1
0x2ec14  br.s     loc_2EC4C
0x2ec16  ldloc.2
0x2ec17  conv.u2
0x2ec18  call     bool [mscorlib]System.Char::IsWhiteSpace(char)
0x2ec1d  brfalse.s loc_2EC2D
0x2ec1f  ldarg.0
0x2ec20  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2ec25  callvirt instance int32 Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader::Skip()
0x2ec2a  pop
0x2ec2b  br.s     loc_2EC4C
0x2ec2d  ldloc.0
0x2ec2e  brtrue.s loc_2EC44
0x2ec30  ldloc.2
0x2ec31  ldarg.1
0x2ec32  bne.un.s loc_2EC44
0x2ec34  ldc.i4.1
0x2ec35  stloc.0
0x2ec36  ldarg.0
0x2ec37  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2ec3c  callvirt instance int32 Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader::Skip()
0x2ec41  pop
0x2ec42  br.s     loc_2EC4C
0x2ec44  ldloc.2
0x2ec45  ldarg.2
0x2ec46  bne.un.s loc_2EC5C
0x2ec48  ldc.i4.1
0x2ec49  stloc.1
0x2ec4a  br.s     loc_2EC5C
0x2ec4c  ldarg.0
0x2ec4d  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2ec52  callvirt instance int32 [mscorlib]System.IO.TextReader::Peek()
0x2ec57  dup
0x2ec58  stloc.2
0x2ec59  ldc.i4.m1
0x2ec5a  bne.un.s loc_2EC16
0x2ec5c  ldloc.0
0x2ec5d  brtrue.s loc_2EC72
0x2ec5f  ldloc.1
0x2ec60  brtrue.s loc_2EC72
0x2ec62  ldstr    aJsonnotwellfor// "JsonNotWellFormated"
0x2ec67  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId)
0x2ec6c  newobj   instance void [mscorlib]System.FormatException::.ctor(string)
0x2ec71  throw
0x2ec72  ret
```
