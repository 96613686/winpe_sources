# Microsoft.ReportingServices.Diagnostics.RequestCache::InitializeForRequest

- ea: `0xb1b0`
- end: `0xb1d8`
- name: `Microsoft.ReportingServices.Diagnostics.RequestCache::InitializeForRequest`
- size: `40`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0xe540`
- `0x10230`

## callees

- `0x6280`
- `0xb180`
- `0xb1b0`
- `0x10150`

## pseudocode

```c

```

## disassembly

```asm
0xb1b0  ldsfld   class Microsoft.ReportingServices.Diagnostics.RequestCache Microsoft.ReportingServices.Diagnostics.RequestCache::m_tlc
0xb1b5  brtrue.s loc_B1D7
0xb1b7  ldc.i4.s 0x10
0xb1b9  stloc.0
0xb1ba  call     class Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_Configuration()
0xb1bf  brfalse.s loc_B1CC
0xb1c1  call     class Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_Configuration()
0xb1c6  callvirt instance int32 Microsoft.ReportingServices.Diagnostics.IProcessRenderingConfiguration::get_RequestCacheSlots()
0xb1cb  stloc.0
0xb1cc  ldloc.0
0xb1cd  newobj   instance void Microsoft.ReportingServices.Diagnostics.RequestCache::.ctor(int32 cacheSlots)
0xb1d2  stsfld   class Microsoft.ReportingServices.Diagnostics.RequestCache Microsoft.ReportingServices.Diagnostics.RequestCache::m_tlc
0xb1d7  ret
```
