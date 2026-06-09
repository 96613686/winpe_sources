# Microsoft.ReportingServices.Diagnostics.ThreadWorkItem::MonitoredThreadPoolCallback

- ea: `0xe500`
- end: `0xe536`
- name: `Microsoft.ReportingServices.Diagnostics.ThreadWorkItem::MonitoredThreadPoolCallback`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callees

- `0x9910`
- `0xb0d0`
- `0xb0e0`
- `0xe500`
- `0x10230`
- `0x10260`

## pseudocode

```c

```

## disassembly

```asm
0xe500  call     int32 Microsoft.ReportingServices.Diagnostics.ReportServerThreadPool::IncrementCurrentReportThreads()
0xe505  pop
0xe506  ldarg.0
0xe507  ldfld    class Microsoft.ReportingServices.Diagnostics.IServiceInstanceContext Microsoft.ReportingServices.Diagnostics.ThreadWorkItem::m_serviceInstanceContext
0xe50c  newobj   instance void Microsoft.ReportingServices.Diagnostics.BackgroundRequestContext::.ctor(class Microsoft.ReportingServices.Diagnostics.IServiceInstanceContext serviceInstanceContext)
0xe511  call     void Microsoft.ReportingServices.Diagnostics.ProcessingContext::InitializeRequestContext(class Microsoft.ReportingServices.Diagnostics.RequestContext context)
0xe516  ldarg.0
0xe517  ldfld    class [mscorlib]System.Threading.WaitCallback Microsoft.ReportingServices.Diagnostics.ThreadWorkItem::m_callback
0xe51c  ldarg.0
0xe51d  ldfld    object Microsoft.ReportingServices.Diagnostics.ThreadWorkItem::m_state
0xe522  callvirt instance void [mscorlib]System.Threading.WaitCallback::Invoke(object)
0xe527  leave.s  loc_E535
0xe529  call     void Microsoft.ReportingServices.Diagnostics.ProcessingContext::EndRequestContext()
0xe52e  call     int32 Microsoft.ReportingServices.Diagnostics.ReportServerThreadPool::DecrementCurrentReportThreads()
0xe533  pop
0xe534  endfinally
0xe535  ret
```
