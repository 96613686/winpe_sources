# Microsoft.ReportingServices.Library.MemoryThenFileStream::ReopenFileReadOnly

- ea: `0x55d20`
- end: `0x55dbe`
- name: `Microsoft.ReportingServices.Library.MemoryThenFileStream::ReopenFileReadOnly`
- size: `158`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x5a070`

## callees

- `0xf200`
- `0x15a50`
- `0x15a60`
- `0x15f60`
- `0x55d20`

## string_xrefs

- `0x55d58`: `!fileStream.IsDeleteOnClose`
- `0x55db3`: `!m_bufferStream.CanWrite`

## pseudocode

```c

```

## disassembly

```asm
0x55d20  ldarg.0
0x55d21  ldfld    bool Microsoft.ReportingServices.Library.MemoryUntilThresholdStream::m_thresholdReached
0x55d26  brfalse  loc_55DBD
0x55d2b  ldarg.0
0x55d2c  ldfld    class [mscorlib]System.IO.Stream Microsoft.ReportingServices.Library.MemoryUntilThresholdStream::m_bufferStream
0x55d31  isinst   Microsoft.ReportingServices.Library.PartitionFileStream
0x55d36  stloc.0
0x55d37  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x55d3c  ldloc.0
0x55d3d  ldnull
0x55d3e  cgt.un
0x55d40  ldstr    aFilestream// "fileStream"
0x55d45  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x55d4a  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x55d4f  ldloc.0
0x55d50  callvirt instance bool Microsoft.ReportingServices.Library.PartitionFileStream::get_IsDeleteOnClose()
0x55d55  ldc.i4.0
0x55d56  ceq
0x55d58  ldstr    aFilestreamIsde// "!fileStream.IsDeleteOnClose"
0x55d5d  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x55d62  ldloc.0
0x55d63  callvirt instance bool [mscorlib]System.IO.Stream::get_CanWrite()
0x55d68  brfalse.s loc_55DBD
0x55d6a  ldloc.0
0x55d6b  callvirt instance string Microsoft.ReportingServices.Library.PartitionFileStream::get_FileName()
0x55d70  stloc.1
0x55d71  ldloc.0
0x55d72  callvirt instance void [mscorlib]System.IO.Stream::Close()
0x55d77  ldarg.0
0x55d78  call     class Microsoft.ReportingServices.Library.PartitionManager Microsoft.ReportingServices.Library.Global::get_PartitionManager()
0x55d7d  ldloc.1
0x55d7e  callvirt instance class Microsoft.ReportingServices.Library.PartitionFileStream Microsoft.ReportingServices.Library.PartitionManager::GetFile(string fileName)
0x55d83  stfld    class [mscorlib]System.IO.Stream Microsoft.ReportingServices.Library.MemoryUntilThresholdStream::m_bufferStream
0x55d88  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x55d8d  ldarg.0
0x55d8e  ldfld    class [mscorlib]System.IO.Stream Microsoft.ReportingServices.Library.MemoryUntilThresholdStream::m_bufferStream
0x55d93  ldnull
0x55d94  cgt.un
0x55d96  ldstr    aMBufferstream// "m_bufferStream"
0x55d9b  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x55da0  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x55da5  ldarg.0
0x55da6  ldfld    class [mscorlib]System.IO.Stream Microsoft.ReportingServices.Library.MemoryUntilThresholdStream::m_bufferStream
0x55dab  callvirt instance bool [mscorlib]System.IO.Stream::get_CanWrite()
0x55db0  ldc.i4.0
0x55db1  ceq
0x55db3  ldstr    aMBufferstreamC// "!m_bufferStream.CanWrite"
0x55db8  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x55dbd  ret
```
