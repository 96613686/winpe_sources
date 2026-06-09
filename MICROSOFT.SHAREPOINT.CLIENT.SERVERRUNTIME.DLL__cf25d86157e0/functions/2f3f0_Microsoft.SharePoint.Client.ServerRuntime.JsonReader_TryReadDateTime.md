# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::TryReadDateTime

- ea: `0x2f3f0`
- end: `0x2f7be`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::TryReadDateTime`
- size: `974`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x2ece0`

## callees

- `0x16f10`
- `0x178e0`
- `0x17b50`
- `0x2ec80`
- `0x2f3f0`
- `0x2fc90`
- `0x30530`
- `0x306e0`
- `0x30700`

## string_xrefs

- `0x2f53d`: `JsonNotWellFormated`
- `0x2f5a4`: `JsonNotWellFormated`
- `0x2f5e1`: `JsonNotWellFormated`
- `0x2f61a`: `JsonNotWellFormated`
- `0x2f64b`: `JsonNotWellFormated`
- `0x2f798`: `JsonNotWellFormated`

## pseudocode

```c

```

## disassembly

```asm
0x2f3f0  ldnull
0x2f3f1  stloc.0
0x2f3f2  ldc.i4.0
0x2f3f3  stloc.2
0x2f3f4  br.s     loc_2F3FA
0x2f3f6  ldloc.2
0x2f3f7  ldc.i4.1
0x2f3f8  add
0x2f3f9  stloc.2
0x2f3fa  ldloc.2
0x2f3fb  ldsfld   int32 Microsoft.SharePoint.Client.ServerRuntime.JsonReader::DateTimePrefixLength
0x2f400  bge.s    loc_2F41B
0x2f402  ldarg.0
0x2f403  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2f408  ldloc.2
0x2f409  callvirt instance int32 Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader::Peek(int32 position)
0x2f40e  ldstr    aDate// "\"\\/Date("
0x2f413  ldloc.2
0x2f414  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x2f419  beq.s    loc_2F3F6
0x2f41b  ldloc.2
0x2f41c  ldsfld   int32 Microsoft.SharePoint.Client.ServerRuntime.JsonReader::DateTimePrefixLength
0x2f421  bne.un   loc_2F7BC
0x2f426  ldc.i4.s 9
0x2f428  ldarg.1
0x2f429  newobj   instance void Token::.ctor(valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType tokenType, int32 position)
0x2f42e  stloc.0
0x2f42f  ldarg.0
0x2f430  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2f435  ldsfld   int32 Microsoft.SharePoint.Client.ServerRuntime.JsonReader::DateTimePrefixLength
0x2f43a  callvirt instance int32 Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader::Skip(int32 count)
0x2f43f  pop
0x2f440  ldc.i4.0
0x2f441  stloc.s  4
0x2f443  ldc.i4.0
0x2f444  stloc.s  5
0x2f446  ldc.i4.0
0x2f447  stloc.s  6
0x2f449  ldc.i4.0
0x2f44a  stloc.s  7
0x2f44c  ldc.i4.0
0x2f44d  stloc.3
0x2f44e  br.s     loc_2F467
0x2f450  ldarg.0
0x2f451  ldfld    int64[] Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_dateTimeComponents
0x2f456  ldloc.3
0x2f457  ldc.i4.0
0x2f458  conv.i8
0x2f459  stelem.i8
0x2f45a  ldarg.0
0x2f45b  ldfld    char[] Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_dateTimeSigns
0x2f460  ldloc.3
0x2f461  ldc.i4.0
0x2f462  stelem.i2
0x2f463  ldloc.3
0x2f464  ldc.i4.1
0x2f465  add
0x2f466  stloc.3
0x2f467  ldloc.3
0x2f468  ldarg.0
0x2f469  ldfld    int64[] Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_dateTimeComponents
0x2f46e  ldlen
0x2f46f  conv.i4
0x2f470  blt.s    loc_2F450
0x2f472  ldc.i4.0
0x2f473  stloc.s  5
0x2f475  br.s     loc_2F487
0x2f477  ldarg.0
0x2f478  ldfld    char[] Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_dateTimeHhmm
0x2f47d  ldloc.s  5
0x2f47f  ldc.i4.0
0x2f480  stelem.i2
0x2f481  ldloc.s  5
0x2f483  ldc.i4.1
0x2f484  add
0x2f485  stloc.s  5
0x2f487  ldloc.s  5
0x2f489  ldarg.0
0x2f48a  ldfld    char[] Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_dateTimeHhmm
0x2f48f  ldlen
0x2f490  conv.i4
0x2f491  blt.s    loc_2F477
0x2f493  ldc.i4.0
0x2f494  stloc.3
0x2f495  ldc.i4.0
0x2f496  stloc.s  5
0x2f498  ldc.i4.0
0x2f499  stloc.s  8
0x2f49b  br       loc_2F66F
0x2f4a0  ldloc.1
0x2f4a1  stloc.s  0xB
0x2f4a3  ldloc.s  0xB
0x2f4a5  ldc.i4.s 0x20
0x2f4a7  sub
0x2f4a8  switch   loc_2F63E, loc_2F64B, loc_2F64B, loc_2F64B, loc_2F64B, loc_2F64B, loc_2F64B, loc_2F64B, loc_2F64B, loc_2F646, loc_2F64B, loc_2F58E, loc_2F605, loc_2F58E, loc_2F64B, loc_2F64B, loc_2F51A, loc_2F51A, loc_2F51A, loc_2F51A, loc_2F51A, loc_2F51A, loc_2F51A, loc_2F51A, loc_2F51A, loc_2F51A
0x2f515  br       loc_2F64B
0x2f51a  ldloc.s  6
0x2f51c  brfalse.s loc_2F561
0x2f51e  ldloc.s  5
0x2f520  ldarg.0
0x2f521  ldfld    char[] Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_dateTimeHhmm
0x2f526  ldlen
0x2f527  conv.i4
0x2f528  bge.s    loc_2F53D
0x2f52a  ldarg.0
0x2f52b  ldfld    char[] Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_dateTimeHhmm
0x2f530  ldloc.s  5
0x2f532  ldloc.1
0x2f533  conv.u2
0x2f534  stelem.i2
0x2f535  ldloc.s  5
0x2f537  ldc.i4.1
0x2f538  add
0x2f539  stloc.s  5
0x2f53b  br.s     loc_2F568
0x2f53d  ldstr    aJsonnotwellfor// "JsonNotWellFormated"
0x2f542  ldc.i4.1
0x2f543  newarr   [mscorlib]System.Object
0x2f548  stloc.s  0xC
0x2f54a  ldloc.s  0xC
0x2f54c  ldc.i4.0
0x2f54d  ldarg.1
0x2f54e  box      [mscorlib]System.Int32
0x2f553  stelem.ref
0x2f554  ldloc.s  0xC
0x2f556  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2f55b  newobj   instance void [mscorlib]System.FormatException::.ctor(string)
0x2f560  throw
0x2f561  ldloc.s  7
0x2f563  brtrue.s loc_2F568
0x2f565  ldc.i4.1
0x2f566  stloc.s  7
0x2f568  ldloc.s  7
0x2f56a  brfalse  loc_2F66F
0x2f56f  ldarg.0
0x2f570  ldfld    int64[] Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_dateTimeComponents
0x2f575  ldloc.3
0x2f576  ldarg.0
0x2f577  ldfld    int64[] Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_dateTimeComponents
0x2f57c  ldloc.3
0x2f57d  ldelem.i8
0x2f57e  ldc.i4.s 0xA
0x2f580  conv.i8
0x2f581  mul
0x2f582  ldloc.1
0x2f583  ldc.i4.s 0x30
0x2f585  sub
0x2f586  conv.i8
0x2f587  add
0x2f588  stelem.i8
0x2f589  br       loc_2F66F
0x2f58e  ldloc.s  7
0x2f590  brfalse.s loc_2F5C8
0x2f592  ldloc.3
0x2f593  brtrue.s loc_2F5A4
0x2f595  ldloc.1
0x2f596  conv.u2
0x2f597  stloc.s  4
0x2f599  ldc.i4.1
0x2f59a  stloc.s  6
0x2f59c  ldc.i4.0
0x2f59d  stloc.s  7
0x2f59f  br       loc_2F66F
0x2f5a4  ldstr    aJsonnotwellfor// "JsonNotWellFormated"
0x2f5a9  ldc.i4.1
0x2f5aa  newarr   [mscorlib]System.Object
0x2f5af  stloc.s  0xD
0x2f5b1  ldloc.s  0xD
0x2f5b3  ldc.i4.0
0x2f5b4  ldarg.1
0x2f5b5  box      [mscorlib]System.Int32
0x2f5ba  stelem.ref
0x2f5bb  ldloc.s  0xD
0x2f5bd  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2f5c2  newobj   instance void [mscorlib]System.FormatException::.ctor(string)
0x2f5c7  throw
0x2f5c8  ldarg.0
0x2f5c9  ldfld    char[] Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_dateTimeSigns
0x2f5ce  ldloc.3
0x2f5cf  ldelem.u2
0x2f5d0  brtrue.s loc_2F5E1
0x2f5d2  ldarg.0
0x2f5d3  ldfld    char[] Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_dateTimeSigns
0x2f5d8  ldloc.3
0x2f5d9  ldloc.1
0x2f5da  conv.u2
0x2f5db  stelem.i2
0x2f5dc  br       loc_2F66F
0x2f5e1  ldstr    aJsonnotwellfor// "JsonNotWellFormated"
0x2f5e6  ldc.i4.1
0x2f5e7  newarr   [mscorlib]System.Object
0x2f5ec  stloc.s  0xE
0x2f5ee  ldloc.s  0xE
0x2f5f0  ldc.i4.0
0x2f5f1  ldarg.1
0x2f5f2  box      [mscorlib]System.Int32
0x2f5f7  stelem.ref
0x2f5f8  ldloc.s  0xE
0x2f5fa  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2f5ff  newobj   instance void [mscorlib]System.FormatException::.ctor(string)
0x2f604  throw
0x2f605  ldc.i4.0
0x2f606  stloc.s  7
0x2f608  ldc.i4.0
0x2f609  stloc.s  6
0x2f60b  ldloc.3
0x2f60c  ldc.i4.1
0x2f60d  add
0x2f60e  stloc.3
0x2f60f  ldloc.3
0x2f610  ldarg.0
0x2f611  ldfld    int64[] Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_dateTimeComponents
0x2f616  ldlen
0x2f617  conv.i4
0x2f618  blt.s    loc_2F66F
0x2f61a  ldstr    aJsonnotwellfor// "JsonNotWellFormated"
0x2f61f  ldc.i4.1
0x2f620  newarr   [mscorlib]System.Object
0x2f625  stloc.s  0xF
0x2f627  ldloc.s  0xF
0x2f629  ldc.i4.0
0x2f62a  ldarg.1
0x2f62b  box      [mscorlib]System.Int32
0x2f630  stelem.ref
0x2f631  ldloc.s  0xF
0x2f633  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2f638  newobj   instance void [mscorlib]System.FormatException::.ctor(string)
0x2f63d  throw
0x2f63e  ldc.i4.0
0x2f63f  stloc.s  7
0x2f641  ldc.i4.0
0x2f642  stloc.s  6
0x2f644  br.s     loc_2F66F
0x2f646  ldc.i4.1
0x2f647  stloc.s  8
0x2f649  br.s     loc_2F66F
0x2f64b  ldstr    aJsonnotwellfor// "JsonNotWellFormated"
0x2f650  ldc.i4.1
0x2f651  newarr   [mscorlib]System.Object
0x2f656  stloc.s  0x10
0x2f658  ldloc.s  0x10
0x2f65a  ldc.i4.0
0x2f65b  ldarg.1
0x2f65c  box      [mscorlib]System.Int32
0x2f661  stelem.ref
0x2f662  ldloc.s  0x10
0x2f664  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2f669  newobj   instance void [mscorlib]System.FormatException::.ctor(string)
0x2f66e  throw
0x2f66f  ldloc.s  8
0x2f671  brtrue.s loc_2F686
0x2f673  ldarg.0
0x2f674  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2f679  callvirt instance int32 [mscorlib]System.IO.TextReader::Read()
0x2f67e  dup
0x2f67f  stloc.1
0x2f680  ldc.i4.m1
0x2f681  bne.un   loc_2F4A0
0x2f686  ldloc.s  8
0x2f688  brfalse  loc_2F798
0x2f68d  ldarg.0
0x2f68e  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2f693  callvirt instance int32 [mscorlib]System.IO.TextReader::Read()
0x2f698  ldc.i4.s 0x5C
0x2f69a  bne.un   loc_2F798
0x2f69f  ldarg.0
0x2f6a0  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2f6a5  callvirt instance int32 [mscorlib]System.IO.TextReader::Read()
0x2f6aa  ldc.i4.s 0x2F
0x2f6ac  bne.un   loc_2F798
0x2f6b1  ldarg.0
0x2f6b2  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2f6b7  callvirt instance int32 [mscorlib]System.IO.TextReader::Read()
0x2f6bc  ldc.i4.s 0x22
0x2f6be  bne.un   loc_2F798
0x2f6c3  ldc.i4.0
0x2f6c4  stloc.s  9
0x2f6c6  br.s     loc_2F6EE
0x2f6c8  ldarg.0
0x2f6c9  ldfld    char[] Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_dateTimeSigns
0x2f6ce  ldloc.s  9
0x2f6d0  ldelem.u2
0x2f6d1  ldc.i4.s 0x2D
0x2f6d3  bne.un.s loc_2F6E8
0x2f6d5  ldarg.0
0x2f6d6  ldfld    int64[] Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_dateTimeComponents
0x2f6db  ldloc.s  9
0x2f6dd  ldarg.0
0x2f6de  ldfld    int64[] Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_dateTimeComponents
0x2f6e3  ldloc.s  9
0x2f6e5  ldelem.i8
0x2f6e6  neg
0x2f6e7  stelem.i8
0x2f6e8  ldloc.s  9
0x2f6ea  ldc.i4.1
0x2f6eb  add
0x2f6ec  stloc.s  9
0x2f6ee  ldloc.s  9
0x2f6f0  ldarg.0
0x2f6f1  ldfld    int64[] Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_dateTimeComponents
  ... truncated ...
```
