# Microsoft.SharePoint.Client.ServerRuntime.JsonReader::TryReadGuid

- ea: `0x2f7c0`
- end: `0x2fa62`
- name: `Microsoft.SharePoint.Client.ServerRuntime.JsonReader::TryReadGuid`
- size: `674`
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
- `0x2f7c0`
- `0x2fc90`
- `0x30530`
- `0x30740`

## string_xrefs

- `0x2f97a`: `JsonNotWellFormated`
- `0x2fa3c`: `JsonNotWellFormated`

## pseudocode

```c

```

## disassembly

```asm
0x2f7c0  ldnull
0x2f7c1  stloc.1
0x2f7c2  ldc.i4.0
0x2f7c3  stloc.2
0x2f7c4  br.s     loc_2F7CA
0x2f7c6  ldloc.2
0x2f7c7  ldc.i4.1
0x2f7c8  add
0x2f7c9  stloc.2
0x2f7ca  ldloc.2
0x2f7cb  ldsfld   int32 Microsoft.SharePoint.Client.ServerRuntime.JsonReader::GuidPrefixLength
0x2f7d0  bge.s    loc_2F7EB
0x2f7d2  ldarg.0
0x2f7d3  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2f7d8  ldloc.2
0x2f7d9  callvirt instance int32 Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader::Peek(int32 position)
0x2f7de  ldstr    aGuid_0// "\"\\/Guid("
0x2f7e3  ldloc.2
0x2f7e4  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x2f7e9  beq.s    loc_2F7C6
0x2f7eb  ldloc.2
0x2f7ec  ldsfld   int32 Microsoft.SharePoint.Client.ServerRuntime.JsonReader::GuidPrefixLength
0x2f7f1  bne.un   loc_2FA60
0x2f7f6  ldc.i4.s 0xA
0x2f7f8  ldarg.1
0x2f7f9  newobj   instance void Token::.ctor(valuetype Microsoft.SharePoint.Client.ServerRuntime.JsonTokenType tokenType, int32 position)
0x2f7fe  stloc.1
0x2f7ff  ldarg.0
0x2f800  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2f805  ldstr    aGuid_0// "\"\\/Guid("
0x2f80a  callvirt instance int32 [mscorlib]System.String::get_Length()
0x2f80f  callvirt instance int32 Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader::Skip(int32 count)
0x2f814  pop
0x2f815  ldc.i4.0
0x2f816  stloc.3
0x2f817  br.s     loc_2F826
0x2f819  ldarg.0
0x2f81a  ldfld    unsigned int8[] Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_tryReadGuidByteBuf
0x2f81f  ldloc.3
0x2f820  ldc.i4.0
0x2f821  stelem.i1
0x2f822  ldloc.3
0x2f823  ldc.i4.1
0x2f824  add
0x2f825  stloc.3
0x2f826  ldloc.3
0x2f827  ldarg.0
0x2f828  ldfld    unsigned int8[] Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_tryReadGuidByteBuf
0x2f82d  ldlen
0x2f82e  conv.i4
0x2f82f  blt.s    loc_2F819
0x2f831  ldc.i4.0
0x2f832  stloc.s  4
0x2f834  br.s     loc_2F847
0x2f836  ldarg.0
0x2f837  ldfld    int64[] Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_tryReadGuidIntBuf
0x2f83c  ldloc.s  4
0x2f83e  ldc.i4.0
0x2f83f  conv.i8
0x2f840  stelem.i8
0x2f841  ldloc.s  4
0x2f843  ldc.i4.1
0x2f844  add
0x2f845  stloc.s  4
0x2f847  ldloc.s  4
0x2f849  ldarg.0
0x2f84a  ldfld    int64[] Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_tryReadGuidIntBuf
0x2f84f  ldlen
0x2f850  conv.i4
0x2f851  blt.s    loc_2F836
0x2f853  ldc.i4.0
0x2f854  stloc.3
0x2f855  ldc.i4.0
0x2f856  stloc.s  4
0x2f858  ldc.i4.0
0x2f859  stloc.s  5
0x2f85b  br       loc_2F9A4
0x2f860  ldloc.0
0x2f861  ldc.i4.s 0x30
0x2f863  blt.s    loc_2F8B7
0x2f865  ldloc.0
0x2f866  ldc.i4.s 0x39
0x2f868  bgt.s    loc_2F8B7
0x2f86a  ldloc.s  4
0x2f86c  ldc.i4.3
0x2f86d  bge.s    loc_2F891
0x2f86f  ldarg.0
0x2f870  ldfld    int64[] Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_tryReadGuidIntBuf
0x2f875  ldloc.s  4
0x2f877  ldarg.0
0x2f878  ldfld    int64[] Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_tryReadGuidIntBuf
0x2f87d  ldloc.s  4
0x2f87f  ldelem.i8
0x2f880  ldc.i4.s 0x10
0x2f882  conv.i8
0x2f883  mul
0x2f884  ldloc.0
0x2f885  conv.i8
0x2f886  add
0x2f887  ldc.i4.s 0x30
0x2f889  conv.i8
0x2f88a  sub
0x2f88b  stelem.i8
0x2f88c  br       loc_2F99E
0x2f891  ldarg.0
0x2f892  ldfld    unsigned int8[] Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_tryReadGuidByteBuf
0x2f897  ldloc.3
0x2f898  ldc.i4.2
0x2f899  div
0x2f89a  ldarg.0
0x2f89b  ldfld    unsigned int8[] Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_tryReadGuidByteBuf
0x2f8a0  ldloc.3
0x2f8a1  ldc.i4.2
0x2f8a2  div
0x2f8a3  ldelem.u1
0x2f8a4  ldc.i4.s 0x10
0x2f8a6  mul
0x2f8a7  ldloc.0
0x2f8a8  add
0x2f8a9  ldc.i4.s 0x30
0x2f8ab  sub
0x2f8ac  conv.u1
0x2f8ad  stelem.i1
0x2f8ae  ldloc.3
0x2f8af  ldc.i4.1
0x2f8b0  add
0x2f8b1  stloc.3
0x2f8b2  br       loc_2F99E
0x2f8b7  ldloc.0
0x2f8b8  ldc.i4.s 0x41
0x2f8ba  blt.s    loc_2F915
0x2f8bc  ldloc.0
0x2f8bd  ldc.i4.s 0x46
0x2f8bf  bgt.s    loc_2F915
0x2f8c1  ldloc.s  4
0x2f8c3  ldc.i4.3
0x2f8c4  bge.s    loc_2F8EC
0x2f8c6  ldarg.0
0x2f8c7  ldfld    int64[] Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_tryReadGuidIntBuf
0x2f8cc  ldloc.s  4
0x2f8ce  ldarg.0
0x2f8cf  ldfld    int64[] Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_tryReadGuidIntBuf
0x2f8d4  ldloc.s  4
0x2f8d6  ldelem.i8
0x2f8d7  ldc.i4.s 0x10
0x2f8d9  conv.i8
0x2f8da  mul
0x2f8db  ldloc.0
0x2f8dc  conv.i8
0x2f8dd  add
0x2f8de  ldc.i4.s 0x41
0x2f8e0  conv.i8
0x2f8e1  sub
0x2f8e2  ldc.i4.s 0xA
0x2f8e4  conv.i8
0x2f8e5  add
0x2f8e6  stelem.i8
0x2f8e7  br       loc_2F99E
0x2f8ec  ldarg.0
0x2f8ed  ldfld    unsigned int8[] Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_tryReadGuidByteBuf
0x2f8f2  ldloc.3
0x2f8f3  ldc.i4.2
0x2f8f4  div
0x2f8f5  ldarg.0
0x2f8f6  ldfld    unsigned int8[] Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_tryReadGuidByteBuf
0x2f8fb  ldloc.3
0x2f8fc  ldc.i4.2
0x2f8fd  div
0x2f8fe  ldelem.u1
0x2f8ff  ldc.i4.s 0x10
0x2f901  mul
0x2f902  ldloc.0
0x2f903  add
0x2f904  ldc.i4.s 0x41
0x2f906  sub
0x2f907  ldc.i4.s 0xA
0x2f909  add
0x2f90a  conv.u1
0x2f90b  stelem.i1
0x2f90c  ldloc.3
0x2f90d  ldc.i4.1
0x2f90e  add
0x2f90f  stloc.3
0x2f910  br       loc_2F99E
0x2f915  ldloc.0
0x2f916  ldc.i4.s 0x61
0x2f918  blt.s    loc_2F96D
0x2f91a  ldloc.0
0x2f91b  ldc.i4.s 0x66
0x2f91d  bgt.s    loc_2F96D
0x2f91f  ldloc.s  4
0x2f921  ldc.i4.3
0x2f922  bge.s    loc_2F947
0x2f924  ldarg.0
0x2f925  ldfld    int64[] Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_tryReadGuidIntBuf
0x2f92a  ldloc.s  4
0x2f92c  ldarg.0
0x2f92d  ldfld    int64[] Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_tryReadGuidIntBuf
0x2f932  ldloc.s  4
0x2f934  ldelem.i8
0x2f935  ldc.i4.s 0x10
0x2f937  conv.i8
0x2f938  mul
0x2f939  ldloc.0
0x2f93a  conv.i8
0x2f93b  add
0x2f93c  ldc.i4.s 0x61
0x2f93e  conv.i8
0x2f93f  sub
0x2f940  ldc.i4.s 0xA
0x2f942  conv.i8
0x2f943  add
0x2f944  stelem.i8
0x2f945  br.s     loc_2F99E
0x2f947  ldarg.0
0x2f948  ldfld    unsigned int8[] Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_tryReadGuidByteBuf
0x2f94d  ldloc.3
0x2f94e  ldc.i4.2
0x2f94f  div
0x2f950  ldarg.0
0x2f951  ldfld    unsigned int8[] Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_tryReadGuidByteBuf
0x2f956  ldloc.3
0x2f957  ldc.i4.2
0x2f958  div
0x2f959  ldelem.u1
0x2f95a  ldc.i4.s 0x10
0x2f95c  mul
0x2f95d  ldloc.0
0x2f95e  add
0x2f95f  ldc.i4.s 0x61
0x2f961  sub
0x2f962  ldc.i4.s 0xA
0x2f964  add
0x2f965  conv.u1
0x2f966  stelem.i1
0x2f967  ldloc.3
0x2f968  ldc.i4.1
0x2f969  add
0x2f96a  stloc.3
0x2f96b  br.s     loc_2F99E
0x2f96d  ldloc.0
0x2f96e  ldc.i4.s 0x2D
0x2f970  bne.un.s loc_2F97A
0x2f972  ldloc.s  4
0x2f974  ldc.i4.1
0x2f975  add
0x2f976  stloc.s  4
0x2f978  br.s     loc_2F99E
0x2f97a  ldstr    aJsonnotwellfor// "JsonNotWellFormated"
0x2f97f  ldc.i4.1
0x2f980  newarr   [mscorlib]System.Object
0x2f985  stloc.s  7
0x2f987  ldloc.s  7
0x2f989  ldc.i4.0
0x2f98a  ldarg.1
0x2f98b  box      [mscorlib]System.Int32
0x2f990  stelem.ref
0x2f991  ldloc.s  7
0x2f993  call     string Microsoft.SharePoint.Client.Resources::GetString(string resourceId, object[] args)
0x2f998  newobj   instance void [mscorlib]System.FormatException::.ctor(string)
0x2f99d  throw
0x2f99e  ldloc.s  5
0x2f9a0  ldc.i4.1
0x2f9a1  add
0x2f9a2  stloc.s  5
0x2f9a4  ldarg.0
0x2f9a5  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2f9aa  callvirt instance int32 [mscorlib]System.IO.TextReader::Read()
0x2f9af  dup
0x2f9b0  stloc.0
0x2f9b1  ldc.i4.m1
0x2f9b2  beq.s    loc_2F9BC
0x2f9b4  ldloc.0
0x2f9b5  ldc.i4.s 0x29
0x2f9b7  bne.un   loc_2F860
0x2f9bc  ldloc.s  5
0x2f9be  ldc.i4.s 0x24
0x2f9c0  bne.un.s loc_2FA3C
0x2f9c2  ldloc.s  4
0x2f9c4  ldc.i4.4
0x2f9c5  bne.un.s loc_2FA3C
0x2f9c7  ldloc.3
0x2f9c8  ldc.i4.s 0x10
0x2f9ca  bne.un.s loc_2FA3C
0x2f9cc  ldloc.0
0x2f9cd  ldc.i4.s 0x29
0x2f9cf  bne.un.s loc_2FA3C
0x2f9d1  ldarg.0
0x2f9d2  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2f9d7  callvirt instance int32 [mscorlib]System.IO.TextReader::Read()
0x2f9dc  ldc.i4.s 0x5C
0x2f9de  bne.un.s loc_2FA3C
0x2f9e0  ldarg.0
0x2f9e1  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2f9e6  callvirt instance int32 [mscorlib]System.IO.TextReader::Read()
0x2f9eb  ldc.i4.s 0x2F
0x2f9ed  bne.un.s loc_2FA3C
0x2f9ef  ldarg.0
0x2f9f0  ldfld    class Microsoft.SharePoint.Client.ServerRuntime.TextPeekReader Microsoft.SharePoint.Client.ServerRuntime.JsonReader::m_reader
0x2f9f5  callvirt instance int32 [mscorlib]System.IO.TextReader::Read()
  ... truncated ...
```
