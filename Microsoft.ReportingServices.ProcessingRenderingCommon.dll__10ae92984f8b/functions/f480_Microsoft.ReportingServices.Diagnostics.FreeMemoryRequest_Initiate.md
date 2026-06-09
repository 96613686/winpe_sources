# Microsoft.ReportingServices.Diagnostics.FreeMemoryRequest::Initiate

- ea: `0xf480`
- end: `0xf4c6`
- name: `Microsoft.ReportingServices.Diagnostics.FreeMemoryRequest::Initiate`
- size: `70`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0xee00`
- `0xf480`
- `0xf510`
- `0xf520`
- `0xf540`
- `0x10150`

## pseudocode

```c

```

## disassembly

```asm
0xf480  ldc.i4.0
0xf481  conv.i8
0xf482  stloc.0
0xf483  ldarg.0
0xf484  ldfld    class Microsoft.ReportingServices.Diagnostics.FreeMemoryRequestContext Microsoft.ReportingServices.Diagnostics.FreeMemoryRequest::m_requestContext
0xf489  callvirt instance int64 Microsoft.ReportingServices.Diagnostics.FreeMemoryRequestContext::get_KBytesToFree()
0xf48e  stloc.1
0xf48f  ldarg.0
0xf490  ldfld    class Microsoft.ReportingServices.Diagnostics.FreeMemoryRequestContext Microsoft.ReportingServices.Diagnostics.FreeMemoryRequest::m_requestContext
0xf495  callvirt instance bool Microsoft.ReportingServices.Diagnostics.FreeMemoryRequestContext::get_NotifyAllConsumers()
0xf49a  stloc.2
0xf49b  ldc.i4.0
0xf49c  stloc.3
0xf49d  ldc.i4.0
0xf49e  conv.i8
0xf49f  stloc.s  4
0xf4a1  call     class Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_Configuration()
0xf4a6  brtrue.s loc_F4A9
0xf4a8  ret
0xf4a9  ldloc.1
0xf4aa  ldloc.2
0xf4ab  ldc.i4.2
0xf4ac  ldloca.s 4
0xf4ae  ldloca.s 0
0xf4b0  call     bool Microsoft.ReportingServices.Diagnostics.MemoryAuditCollection::InitiateMemoryShrink(int64 kBytes, bool notifyAllConsumers, valuetype Microsoft.ReportingServices.Diagnostics.MemoryGroupType groupType, [out] int64& estimatedKBytesFreed, [out] int64& totalAuditedMemoryKb)
0xf4b5  stloc.3
0xf4b6  ldarg.0
0xf4b7  ldfld    class Microsoft.ReportingServices.Diagnostics.FreeMemoryRequestContext Microsoft.ReportingServices.Diagnostics.FreeMemoryRequest::m_requestContext
0xf4bc  ldloc.3
0xf4bd  ldloc.s  4
0xf4bf  ldloc.0
0xf4c0  callvirt instance void Microsoft.ReportingServices.Diagnostics.FreeMemoryRequestContext::SetShrinkResults(bool shrinkAttempted, int64 estimatedKBytesFreed, int64 totalAuditedKBytes)
0xf4c5  ret
```
