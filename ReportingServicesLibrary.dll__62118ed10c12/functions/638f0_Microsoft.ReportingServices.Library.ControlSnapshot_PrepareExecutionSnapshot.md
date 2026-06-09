# Microsoft.ReportingServices.Library.ControlSnapshot::PrepareExecutionSnapshot

- ea: `0x638f0`
- end: `0x639c0`
- name: `Microsoft.ReportingServices.Library.ControlSnapshot::PrepareExecutionSnapshot`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x638f0`
- `0x63c50`
- `0x63c60`
- `0x63c70`
- `0x8c110`
- `0x8c170`

## string_xrefs

- `0x63903`: `CompiledDefinition`
- `0x6394b`: `CompiledDefinition`

## pseudocode

```c

```

## disassembly

```asm
0x638f0  ldarg.1
0x638f1  castclass Microsoft.ReportingServices.Library.ControlSnapshot
0x638f6  stloc.0
0x638f7  ldc.i4.1
0x638f8  call     valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ReportProcessing/ReportChunkTypes [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ReportProcessing::GetImageChunkTypeToCopy(valuetype [Microsoft.ReportingServices.ProcessingCore]Microsoft.ReportingServices.ReportProcessing.ReportProcessingFlags)
0x638fd  stloc.1
0x638fe  ldarg.2
0x638ff  stloc.2
0x63900  ldloc.2
0x63901  brtrue.s loc_63909
0x63903  ldstr    aCompileddefini_2// "CompiledDefinition"
0x63908  stloc.2
0x63909  ldarg.0
0x6390a  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Chunk> Microsoft.ReportingServices.Library.ControlSnapshot::m_allChunks
0x6390f  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class Chunk>::GetEnumerator()
0x63914  stloc.3
0x63915  br       loc_639A8
0x6391a  ldloc.3
0x6391b  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Chunk>::get_Current()
0x63920  stloc.s  4
0x63922  ldloc.s  4
0x63924  callvirt instance class Microsoft.ReportingServices.Library.ChunkHeader Chunk::get_Header()
0x63929  stloc.s  5
0x6392b  ldloc.s  5
0x6392d  callvirt instance int32 Microsoft.ReportingServices.Library.ChunkHeader::get_ChunkType()
0x63932  ldloc.1
0x63933  bne.un.s loc_63944
0x63935  ldloc.0
0x63936  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Chunk> Microsoft.ReportingServices.Library.ControlSnapshot::m_allChunks
0x6393b  ldloc.s  4
0x6393d  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Chunk>::Add(var<u1>)
0x63942  br.s     loc_639A8
0x63944  ldloc.s  5
0x63946  callvirt instance string Microsoft.ReportingServices.Library.ChunkHeader::get_ChunkName()
0x6394b  ldstr    aCompileddefini_2// "CompiledDefinition"
0x63950  ldc.i4.4
0x63951  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x63956  brfalse.s loc_6397D
0x63958  ldloc.s  4
0x6395a  newobj   instance void Chunk::.ctor(class Chunk baseChunk)
0x6395f  stloc.s  6
0x63961  ldloc.s  6
0x63963  callvirt instance class Microsoft.ReportingServices.Library.ChunkHeader Chunk::get_Header()
0x63968  ldloc.2
0x63969  callvirt instance void Microsoft.ReportingServices.Library.ChunkHeader::set_ChunkName(string value)
0x6396e  ldloc.0
0x6396f  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Chunk> Microsoft.ReportingServices.Library.ControlSnapshot::m_allChunks
0x63974  ldloc.s  6
0x63976  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Chunk>::Add(var<u1>)
0x6397b  br.s     loc_639A8
0x6397d  ldloc.s  5
0x6397f  callvirt instance int32 Microsoft.ReportingServices.Library.ChunkHeader::get_ChunkType()
0x63984  ldc.i4.5
0x63985  beq.s    loc_63992
0x63987  ldloc.s  5
0x63989  callvirt instance int32 Microsoft.ReportingServices.Library.ChunkHeader::get_ChunkType()
0x6398e  ldc.i4.s 9
0x63990  bne.un.s loc_639A8
0x63992  ldloc.s  4
0x63994  newobj   instance void Chunk::.ctor(class Chunk baseChunk)
0x63999  stloc.s  7
0x6399b  ldloc.0
0x6399c  ldfld    class [mscorlib]System.Collections.Generic.IList`1<class Chunk> Microsoft.ReportingServices.Library.ControlSnapshot::m_allChunks
0x639a1  ldloc.s  7
0x639a3  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class Chunk>::Add(var<u1>)
0x639a8  ldloc.3
0x639a9  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x639ae  brtrue   loc_6391A
0x639b3  leave.s  loc_639BF
0x639b5  ldloc.3
0x639b6  brfalse.s loc_639BE
0x639b8  ldloc.3
0x639b9  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x639be  endfinally
0x639bf  ret
```
