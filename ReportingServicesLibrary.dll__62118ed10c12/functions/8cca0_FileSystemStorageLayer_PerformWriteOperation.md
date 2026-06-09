# FileSystemStorageLayer::PerformWriteOperation

- ea: `0x8cca0`
- end: `0x8cdb9`
- name: `FileSystemStorageLayer::PerformWriteOperation`
- size: `281`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x8cb70`
- `0x8cbb0`

## callees

- `0x8cca0`
- `0x8f170`

## string_xrefs

- `0x8ccca`: `writeOperation`
- `0x8cd1a`: `asyncWriteResult`
- `0x8cd44`: `Error while performing async file write operation: `
- `0x8cd75`: `asyncWriteResult.IsCompleted`
- `0x8cd99`: `Async write operation on chunk '{0}' completed synchronously`

## pseudocode

```c

```

## disassembly

```asm
0x8cca0  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x8cca5  ldarg.2
0x8cca6  ldfld    valuetype [mscorlib]System.Guid ReadWriteParameters::ChunkId
0x8ccab  ldarg.0
0x8ccac  ldfld    valuetype [mscorlib]System.Guid FileSystemStorageLayer::m_chunkId
0x8ccb1  call     bool [mscorlib]System.Guid::op_Equality(valuetype [mscorlib]System.Guid, valuetype [mscorlib]System.Guid)
0x8ccb6  ldstr    aParametersChun// "parameters.ChunkId"
0x8ccbb  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x8ccc0  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x8ccc5  ldarg.s  4
0x8ccc7  ldnull
0x8ccc8  cgt.un
0x8ccca  ldstr    aWriteoperation// "writeOperation"
0x8cccf  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x8ccd4  ldnull
0x8ccd5  stloc.0
0x8ccd6  ldarg.0
0x8ccd7  ldfld    class [mscorlib]System.IO.Stream FileSystemStorageLayer::m_fileStream
0x8ccdc  brfalse.s loc_8CD24
0x8ccde  ldarg.0
0x8ccdf  ldfld    class [mscorlib]System.IO.Stream FileSystemStorageLayer::m_fileStream
0x8cce4  ldarg.2
0x8cce5  ldfld    int64 ReadWriteParameters::AbsolutePosition
0x8ccea  ldc.i4.0
0x8cceb  callvirt instance int64 [mscorlib]System.IO.Stream::Seek(int64, valuetype [mscorlib]System.IO.SeekOrigin)
0x8ccf0  pop
0x8ccf1  ldarg.0
0x8ccf2  ldfld    class [mscorlib]System.IO.Stream FileSystemStorageLayer::m_fileStream
0x8ccf7  ldarg.2
0x8ccf8  ldfld    unsigned int8[] ReadWriteParameters::Buffer
0x8ccfd  ldarg.2
0x8ccfe  ldfld    int32 ReadWriteParameters::Offset
0x8cd03  ldarg.2
0x8cd04  ldfld    int32 ReadWriteParameters::Length
0x8cd09  ldnull
0x8cd0a  ldnull
0x8cd0b  callvirt instance class [mscorlib]System.IAsyncResult [mscorlib]System.IO.Stream::BeginWrite(unsigned int8[], int32, int32, class [mscorlib]System.AsyncCallback, object)
0x8cd10  stloc.0
0x8cd11  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x8cd16  ldloc.0
0x8cd17  ldnull
0x8cd18  cgt.un
0x8cd1a  ldstr    aAsyncwriteresu// "asyncWriteResult"
0x8cd1f  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x8cd24  ldarg.s  4
0x8cd26  ldarg.3
0x8cd27  callvirt instance void WriteOperation::Invoke(valuetype ReadWriteStatistics& statistics)
0x8cd2c  leave    loc_8CDB8
0x8cd31  stloc.1
0x8cd32  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x8cd37  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceError()
0x8cd3c  brfalse.s loc_8CD59
0x8cd3e  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x8cd43  ldc.i4.1
0x8cd44  ldstr    aErrorWhilePerf// "Error while performing async file write"...
0x8cd49  ldloc.1
0x8cd4a  callvirt instance string [mscorlib]System.Object::ToString()
0x8cd4f  call     string [mscorlib]System.String::Concat(string, string)
0x8cd54  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::TraceException(valuetype [System]System.Diagnostics.TraceLevel, string)
0x8cd59  rethrow
0x8cd5b  ldloc.0
0x8cd5c  brfalse.s loc_8CDB7
0x8cd5e  ldarg.0
0x8cd5f  ldfld    class [mscorlib]System.IO.Stream FileSystemStorageLayer::m_fileStream
0x8cd64  ldloc.0
0x8cd65  callvirt instance void [mscorlib]System.IO.Stream::EndWrite(class [mscorlib]System.IAsyncResult)
0x8cd6a  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x8cd6f  ldloc.0
0x8cd70  callvirt instance bool [mscorlib]System.IAsyncResult::get_IsCompleted()
0x8cd75  ldstr    aAsyncwriteresu_0// "asyncWriteResult.IsCompleted"
0x8cd7a  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x8cd7f  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x8cd84  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceWarning()
0x8cd89  brfalse.s loc_8CDB7
0x8cd8b  ldloc.0
0x8cd8c  callvirt instance bool [mscorlib]System.IAsyncResult::get_CompletedSynchronously()
0x8cd91  brfalse.s loc_8CDB7
0x8cd93  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ChunkTracer()
0x8cd98  ldc.i4.2
0x8cd99  ldstr    aAsyncWriteOper// "Async write operation on chunk '{0}' co"...
0x8cd9e  ldc.i4.1
0x8cd9f  newarr   [mscorlib]System.Object
0x8cda4  dup
0x8cda5  ldc.i4.0
0x8cda6  ldarg.2
0x8cda7  ldfld    valuetype [mscorlib]System.Guid ReadWriteParameters::ChunkId
0x8cdac  box      [mscorlib]System.Guid
0x8cdb1  stelem.ref
0x8cdb2  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x8cdb7  endfinally
0x8cdb8  ret
```
