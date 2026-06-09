# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::DecodeString

- ea: `0x2fd30`
- end: `0x2ff6c`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::DecodeString`
- size: `572`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2ece0`

## callees

- `0x16f10`
- `0x17a20`
- `0x2fcc0`
- `0x2fd30`

## string_xrefs

- `0x2fd46`: `JsonNotWellFormated`
- `0x2fe56`: `JsonNotWellFormated`
- `0x2fe7a`: `JsonNotWellFormated`
- `0x2fed3`: `JsonNotWellFormated`
- `0x2ff41`: `JsonNotWellFormated`

## pseudocode

```c

```

## disassembly

```asm
0x2fd30  ldarg.0
0x2fd31  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2fd36  callvirt instance int32 [mscorlib]System.IO.TextReader::Read()
0x2fd3b  stloc.0
0x2fd3c  ldloc.0
0x2fd3d  ldc.i4.s 0x22
0x2fd3f  beq.s    loc_2FD6A
0x2fd41  ldloc.0
0x2fd42  ldc.i4.s 0x27
0x2fd44  beq.s    loc_2FD6A
0x2fd46  ldstr    aJsonnotwellfor// "JsonNotWellFormated"
0x2fd4b  ldc.i4.1
0x2fd4c  newarr   [mscorlib]System.Object
0x2fd51  stloc.s  0xA
0x2fd53  ldloc.s  0xA
0x2fd55  ldc.i4.0
0x2fd56  ldarg.1
0x2fd57  box      [mscorlib]System.Int32
0x2fd5c  stelem.ref
0x2fd5d  ldloc.s  0xA
0x2fd5f  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2fd64  newobj   instance void [mscorlib]System.FormatException::.ctor(string)
0x2fd69  throw
0x2fd6a  ldloc.0
0x2fd6b  stloc.1
0x2fd6c  ldarg.0
0x2fd6d  ldfld    class [mscorlib]System.Text.StringBuilder Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_decodeStringBuf
0x2fd72  stloc.2
0x2fd73  ldloc.2
0x2fd74  ldc.i4.0
0x2fd75  callvirt instance void [mscorlib]System.Text.StringBuilder::set_Length(int32)
0x2fd7a  ldc.i4.0
0x2fd7b  stloc.3
0x2fd7c  ldarg.0
0x2fd7d  ldfld    char[] Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_decodeStringHexChars
0x2fd82  stloc.s  4
0x2fd84  ldc.i4.0
0x2fd85  stloc.s  5
0x2fd87  ldarg.2
0x2fd88  brtrue.s loc_2FD97
0x2fd8a  ldarg.0
0x2fd8b  ldfld    valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonReaderOptions Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_options
0x2fd90  ldc.i4.2
0x2fd91  and
0x2fd92  ldc.i4.0
0x2fd93  ceq
0x2fd95  br.s     loc_2FD98
0x2fd97  ldc.i4.1
0x2fd98  stloc.s  7
0x2fd9a  br       loc_2FF28
0x2fd9f  ldloc.s  5
0x2fda1  brfalse  loc_2FF09
0x2fda6  ldloc.0
0x2fda7  stloc.s  0xB
0x2fda9  ldloc.s  0xB
0x2fdab  ldc.i4.s 0x5C
0x2fdad  bgt.s    loc_2FDE3
0x2fdaf  ldloc.s  0xB
0x2fdb1  ldc.i4.s 0x27
0x2fdb3  bgt.s    loc_2FDCC
0x2fdb5  ldloc.s  0xB
0x2fdb7  ldc.i4.s 0x22
0x2fdb9  beq      loc_2FEB6
0x2fdbe  ldloc.s  0xB
0x2fdc0  ldc.i4.s 0x27
0x2fdc2  beq      loc_2FEB0
0x2fdc7  br       loc_2FED3
0x2fdcc  ldloc.s  0xB
0x2fdce  ldc.i4.s 0x2F
0x2fdd0  beq      loc_2FEC2
0x2fdd5  ldloc.s  0xB
0x2fdd7  ldc.i4.s 0x5C
0x2fdd9  beq      loc_2FEBC
0x2fdde  br       loc_2FED3
0x2fde3  ldloc.s  0xB
0x2fde5  ldc.i4.s 0x66
0x2fde7  bgt.s    loc_2FE00
0x2fde9  ldloc.s  0xB
0x2fdeb  ldc.i4.s 0x62
0x2fded  beq      loc_2FEC8
0x2fdf2  ldloc.s  0xB
0x2fdf4  ldc.i4.s 0x66
0x2fdf6  beq      loc_2FECD
0x2fdfb  br       loc_2FED3
0x2fe00  ldloc.s  0xB
0x2fe02  ldc.i4.s 0x6E
0x2fe04  beq      loc_2FEAA
0x2fe09  ldloc.s  0xB
0x2fe0b  ldc.i4.s 0x72
0x2fe0d  sub
0x2fe0e  switch   loc_2FEA4, loc_2FED3, loc_2FE9E, loc_2FE28
0x2fe23  br       loc_2FED3
0x2fe28  ldarg.0
0x2fe29  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2fe2e  ldloc.s  4
0x2fe30  ldc.i4.4
0x2fe31  callvirt instance int32 Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader::Read(char[] buffer, int32 count)
0x2fe36  stloc.s  6
0x2fe38  ldloc.s  6
0x2fe3a  ldc.i4.4
0x2fe3b  bne.un.s loc_2FE7A
0x2fe3d  ldc.i4.0
0x2fe3e  stloc.s  9
0x2fe40  ldarg.0
0x2fe41  ldloc.s  4
0x2fe43  ldloca.s 9
0x2fe45  call     instance bool Microsoft.SharePoint.Client.ServerRuntime.JsonReader::Hex4ToInt(char[] hexChars, [out] int32& n)
0x2fe4a  brfalse.s loc_2FE56
0x2fe4c  ldloc.s  9
0x2fe4e  conv.u2
0x2fe4f  stloc.s  8
0x2fe51  br       loc_2FEF7
0x2fe56  ldstr    aJsonnotwellfor// "JsonNotWellFormated"
0x2fe5b  ldc.i4.1
0x2fe5c  newarr   [mscorlib]System.Object
0x2fe61  stloc.s  0xC
0x2fe63  ldloc.s  0xC
0x2fe65  ldc.i4.0
0x2fe66  ldarg.1
0x2fe67  box      [mscorlib]System.Int32
0x2fe6c  stelem.ref
0x2fe6d  ldloc.s  0xC
0x2fe6f  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2fe74  newobj   instance void [mscorlib]System.FormatException::.ctor(string)
0x2fe79  throw
0x2fe7a  ldstr    aJsonnotwellfor// "JsonNotWellFormated"
0x2fe7f  ldc.i4.1
0x2fe80  newarr   [mscorlib]System.Object
0x2fe85  stloc.s  0xD
0x2fe87  ldloc.s  0xD
0x2fe89  ldc.i4.0
0x2fe8a  ldarg.1
0x2fe8b  box      [mscorlib]System.Int32
0x2fe90  stelem.ref
0x2fe91  ldloc.s  0xD
0x2fe93  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2fe98  newobj   instance void [mscorlib]System.FormatException::.ctor(string)
0x2fe9d  throw
0x2fe9e  ldc.i4.s 9
0x2fea0  stloc.s  8
0x2fea2  br.s     loc_2FEF7
0x2fea4  ldc.i4.s 0xD
0x2fea6  stloc.s  8
0x2fea8  br.s     loc_2FEF7
0x2feaa  ldc.i4.s 0xA
0x2feac  stloc.s  8
0x2feae  br.s     loc_2FEF7
0x2feb0  ldc.i4.s 0x27
0x2feb2  stloc.s  8
0x2feb4  br.s     loc_2FEF7
0x2feb6  ldc.i4.s 0x22
0x2feb8  stloc.s  8
0x2feba  br.s     loc_2FEF7
0x2febc  ldc.i4.s 0x5C
0x2febe  stloc.s  8
0x2fec0  br.s     loc_2FEF7
0x2fec2  ldc.i4.s 0x2F
0x2fec4  stloc.s  8
0x2fec6  br.s     loc_2FEF7
0x2fec8  ldc.i4.8
0x2fec9  stloc.s  8
0x2fecb  br.s     loc_2FEF7
0x2fecd  ldc.i4.s 0xC
0x2fecf  stloc.s  8
0x2fed1  br.s     loc_2FEF7
0x2fed3  ldstr    aJsonnotwellfor// "JsonNotWellFormated"
0x2fed8  ldc.i4.1
0x2fed9  newarr   [mscorlib]System.Object
0x2fede  stloc.s  0xE
0x2fee0  ldloc.s  0xE
0x2fee2  ldc.i4.0
0x2fee3  ldarg.1
0x2fee4  box      [mscorlib]System.Int32
0x2fee9  stelem.ref
0x2feea  ldloc.s  0xE
0x2feec  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2fef1  newobj   instance void [mscorlib]System.FormatException::.ctor(string)
0x2fef6  throw
0x2fef7  ldloc.s  7
0x2fef9  brfalse.s loc_2FF04
0x2fefb  ldloc.2
0x2fefc  ldloc.s  8
0x2fefe  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x2ff03  pop
0x2ff04  ldc.i4.0
0x2ff05  stloc.s  5
0x2ff07  br.s     loc_2FF28
0x2ff09  ldloc.0
0x2ff0a  ldc.i4.s 0x5C
0x2ff0c  bne.un.s loc_2FF13
0x2ff0e  ldc.i4.1
0x2ff0f  stloc.s  5
0x2ff11  br.s     loc_2FF28
0x2ff13  ldloc.0
0x2ff14  ldloc.1
0x2ff15  bne.un.s loc_2FF1B
0x2ff17  ldc.i4.1
0x2ff18  stloc.3
0x2ff19  br.s     loc_2FF28
0x2ff1b  ldloc.s  7
0x2ff1d  brfalse.s loc_2FF28
0x2ff1f  ldloc.2
0x2ff20  ldloc.0
0x2ff21  conv.u2
0x2ff22  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x2ff27  pop
0x2ff28  ldloc.3
0x2ff29  brtrue.s loc_2FF3E
0x2ff2b  ldarg.0
0x2ff2c  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2ff31  callvirt instance int32 [mscorlib]System.IO.TextReader::Read()
0x2ff36  dup
0x2ff37  stloc.0
0x2ff38  ldc.i4.m1
0x2ff39  bne.un   loc_2FD9F
0x2ff3e  ldloc.3
0x2ff3f  brtrue.s loc_2FF65
0x2ff41  ldstr    aJsonnotwellfor// "JsonNotWellFormated"
0x2ff46  ldc.i4.1
0x2ff47  newarr   [mscorlib]System.Object
0x2ff4c  stloc.s  0xF
0x2ff4e  ldloc.s  0xF
0x2ff50  ldc.i4.0
0x2ff51  ldarg.1
0x2ff52  box      [mscorlib]System.Int32
0x2ff57  stelem.ref
0x2ff58  ldloc.s  0xF
0x2ff5a  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2ff5f  newobj   instance void [mscorlib]System.FormatException::.ctor(string)
0x2ff64  throw
0x2ff65  ldloc.2
0x2ff66  callvirt instance string [mscorlib]System.Object::ToString()
0x2ff6b  ret
```
