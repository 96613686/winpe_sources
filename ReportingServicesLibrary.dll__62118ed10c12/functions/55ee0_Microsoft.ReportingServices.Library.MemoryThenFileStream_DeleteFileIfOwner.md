# Microsoft.ReportingServices.Library.MemoryThenFileStream::DeleteFileIfOwner

- ea: `0x55ee0`
- end: `0x55f79`
- name: `Microsoft.ReportingServices.Library.MemoryThenFileStream::DeleteFileIfOwner`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x55e40`

## callees

- `0x15e60`
- `0x55cc0`
- `0x55d00`
- `0x55ee0`

## string_xrefs

- `0x55f06`: `File '{0}' is not owned by this stream and will not be deleted.`
- `0x55f35`: `Attempting deletion of file '{0}'`

## pseudocode

```c

```

## disassembly

```asm
0x55ee0  ldarg.0
0x55ee1  ldfld    bool Microsoft.ReportingServices.Library.MemoryUntilThresholdStream::m_thresholdReached
0x55ee6  brtrue.s loc_55EE9
0x55ee8  ret
0x55ee9  ldarg.0
0x55eea  call     instance bool Microsoft.ReportingServices.Library.MemoryThenFileStream::get_OwnsFile()
0x55eef  brtrue.s loc_55F20
0x55ef1  ldarg.1
0x55ef2  brfalse.s loc_55F1F
0x55ef4  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x55ef9  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x55efe  brfalse.s loc_55F1F
0x55f00  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x55f05  ldc.i4.4
0x55f06  ldstr    aFile0IsNotOwne// "File '{0}' is not owned by this stream "...
0x55f0b  ldc.i4.1
0x55f0c  newarr   [mscorlib]System.Object
0x55f11  dup
0x55f12  ldc.i4.0
0x55f13  ldarg.0
0x55f14  call     instance string Microsoft.ReportingServices.Library.MemoryThenFileStream::get_FileName()
0x55f19  stelem.ref
0x55f1a  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x55f1f  ret
0x55f20  ldarg.1
0x55f21  brfalse.s loc_55F4E
0x55f23  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x55f28  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceVerbose()
0x55f2d  brfalse.s loc_55F4E
0x55f2f  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x55f34  ldc.i4.4
0x55f35  ldstr    aAttemptingDele// "Attempting deletion of file '{0}'"
0x55f3a  ldc.i4.1
0x55f3b  newarr   [mscorlib]System.Object
0x55f40  dup
0x55f41  ldc.i4.0
0x55f42  ldarg.0
0x55f43  call     instance string Microsoft.ReportingServices.Library.MemoryThenFileStream::get_FileName()
0x55f48  stelem.ref
0x55f49  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0x55f4e  ldarg.0
0x55f4f  ldfld    class [mscorlib]System.IO.Stream Microsoft.ReportingServices.Library.MemoryUntilThresholdStream::m_bufferStream
0x55f54  brfalse.s loc_55F78
0x55f56  ldarg.0
0x55f57  ldfld    class [mscorlib]System.IO.Stream Microsoft.ReportingServices.Library.MemoryUntilThresholdStream::m_bufferStream
0x55f5c  callvirt instance void [mscorlib]System.IO.Stream::Close()
0x55f61  ldarg.0
0x55f62  ldfld    class Microsoft.ReportingServices.Library.PartitionManager Microsoft.ReportingServices.Library.MemoryThenFileStream::m_partitionManager
0x55f67  ldarg.0
0x55f68  ldfld    class [mscorlib]System.IO.Stream Microsoft.ReportingServices.Library.MemoryUntilThresholdStream::m_bufferStream
0x55f6d  castclass Microsoft.ReportingServices.Library.PartitionFileStream
0x55f72  callvirt instance bool Microsoft.ReportingServices.Library.PartitionManager::DeleteFile(class Microsoft.ReportingServices.Library.PartitionFileStream stream)
0x55f77  pop
0x55f78  ret
```
