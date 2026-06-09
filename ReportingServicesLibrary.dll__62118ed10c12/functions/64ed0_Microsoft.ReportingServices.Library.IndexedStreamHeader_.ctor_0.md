# Microsoft.ReportingServices.Library.IndexedStreamHeader::.ctor_0

- ea: `0x64ed0`
- end: `0x64ff7`
- name: `Microsoft.ReportingServices.Library.IndexedStreamHeader::.ctor_0`
- size: `295`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x64800`

## callees

- `0x64ed0`
- `0x65000`
- `0x65020`

## string_xrefs

- `0x64ef9`: `Expected stream with Read capabilities`
- `0x64f36`: `Reading header\n`
- `0x64f42`: `compressesIndexes:\n`
- `0x64f94`: `uncompressesIndexes:\n`

## pseudocode

```c

```

## disassembly

```asm
0x64ed0  ldarg.0
0x64ed1  ldc.i4.2
0x64ed2  conv.i8
0x64ed3  stfld    int64 Microsoft.ReportingServices.Library.IndexedStreamHeader::m_version
0x64ed8  ldarg.0
0x64ed9  call     instance void [mscorlib]System.Object::.ctor()
0x64ede  ldarg.1
0x64edf  callvirt instance bool [mscorlib]System.IO.Stream::get_CanSeek()
0x64ee4  brtrue.s loc_64EF1
0x64ee6  ldstr    aExpectedStream// "Expected stream with Seek capabilities"
0x64eeb  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x64ef0  throw
0x64ef1  ldarg.1
0x64ef2  callvirt instance bool [mscorlib]System.IO.Stream::get_CanRead()
0x64ef7  brtrue.s loc_64F04
0x64ef9  ldstr    aExpectedStream_0// "Expected stream with Read capabilities"
0x64efe  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.InternalCatalogException::.ctor(string)
0x64f03  throw
0x64f04  ldarg.0
0x64f05  ldarg.0
0x64f06  ldarg.1
0x64f07  call     instance int64 Microsoft.ReportingServices.Library.IndexedStreamHeader::ReadHeaderOffset(class [mscorlib]System.IO.Stream store)
0x64f0c  stfld    int64 Microsoft.ReportingServices.Library.IndexedStreamHeader::m_headerIndex
0x64f11  ldarg.0
0x64f12  ldarg.1
0x64f13  call     instance void Microsoft.ReportingServices.Library.IndexedStreamHeader::ReadHeader(class [mscorlib]System.IO.Stream store)
0x64f18  ldarg.0
0x64f19  ldarg.2
0x64f1a  conv.i8
0x64f1b  stfld    int64 Microsoft.ReportingServices.Library.IndexedStreamHeader::m_version
0x64f20  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x64f25  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x64f2a  brfalse  loc_64FF6
0x64f2f  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x64f34  stloc.0
0x64f35  ldloc.0
0x64f36  ldstr    aReadingHeader// "Reading header\r\n"
0x64f3b  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x64f40  pop
0x64f41  ldloc.0
0x64f42  ldstr    aCompressesinde// "compressesIndexes:\r\n"
0x64f47  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x64f4c  pop
0x64f4d  ldarg.0
0x64f4e  ldfld    class [mscorlib]System.Collections.Generic.List`1<int64> Microsoft.ReportingServices.Library.IndexedStreamHeader::m_compressedIndex
0x64f53  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<int64>::GetEnumerator()
0x64f58  stloc.1
0x64f59  br.s     loc_64F7A
0x64f5b  ldloca.s 1
0x64f5d  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<int64>::get_Current()
0x64f62  stloc.2
0x64f63  ldloc.0
0x64f64  ldloc.2
0x64f65  box      [mscorlib]System.Int64
0x64f6a  ldstr    asc_B72EA// "\r\n"
0x64f6f  call     string [mscorlib]System.String::Concat(object, object)
0x64f74  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x64f79  pop
0x64f7a  ldloca.s 1
0x64f7c  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<int64>::MoveNext()
0x64f81  brtrue.s loc_64F5B
0x64f83  leave.s  loc_64F93
0x64f85  ldloca.s 1
0x64f87  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<int64>
0x64f8d  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x64f92  endfinally
0x64f93  ldloc.0
0x64f94  ldstr    aUncompressesin// "uncompressesIndexes:\r\n"
0x64f99  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x64f9e  pop
0x64f9f  ldarg.0
0x64fa0  ldfld    class [mscorlib]System.Collections.Generic.List`1<int64> Microsoft.ReportingServices.Library.IndexedStreamHeader::m_uncompressedIndex
0x64fa5  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<int64>::GetEnumerator()
0x64faa  stloc.1
0x64fab  br.s     loc_64FCC
0x64fad  ldloca.s 1
0x64faf  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<int64>::get_Current()
0x64fb4  stloc.3
0x64fb5  ldloc.0
0x64fb6  ldloc.3
0x64fb7  box      [mscorlib]System.Int64
0x64fbc  ldstr    asc_B72EA// "\r\n"
0x64fc1  call     string [mscorlib]System.String::Concat(object, object)
0x64fc6  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x64fcb  pop
0x64fcc  ldloca.s 1
0x64fce  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<int64>::MoveNext()
0x64fd3  brtrue.s loc_64FAD
0x64fd5  leave.s  loc_64FE5
0x64fd7  ldloca.s 1
0x64fd9  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<int64>
0x64fdf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x64fe4  endfinally
0x64fe5  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x64fea  ldc.i4.4
0x64feb  ldloc.0
0x64fec  callvirt instance string [mscorlib]System.Object::ToString()
0x64ff1  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x64ff6  ret
```
