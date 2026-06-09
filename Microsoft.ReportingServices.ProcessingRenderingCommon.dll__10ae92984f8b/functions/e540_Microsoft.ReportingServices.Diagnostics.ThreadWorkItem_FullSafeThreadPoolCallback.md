# Microsoft.ReportingServices.Diagnostics.ThreadWorkItem::FullSafeThreadPoolCallback

- ea: `0xe540`
- end: `0xe66f`
- name: `Microsoft.ReportingServices.Diagnostics.ThreadWorkItem::FullSafeThreadPoolCallback`
- size: `303`
- prototype: ``
- caller_count: `0`
- callee_count: `16`
- tags: `service_task, broker_com_uri`

## callees

- `0x9910`
- `0x9b60`
- `0xb030`
- `0xb0d0`
- `0xb0e0`
- `0xb1b0`
- `0xb1f0`
- `0xb200`
- `0xe540`
- `0xe6b0`
- `0x101d0`
- `0x10230`
- `0x10260`
- `0x10310`
- `0x15b90`
- `0x15bb0`

## string_xrefs

- `0xe59c`: `Re-queuing on a threadpool thread`
- `0xe63f`: `error in thread function: {0}`

## pseudocode

```c

```

## disassembly

```asm
0xe540  ldnull
0xe541  stloc.0
0xe542  call     int32 Microsoft.ReportingServices.Diagnostics.ReportServerThreadPool::IncrementCurrentReportThreads()
0xe547  pop
0xe548  ldarg.0
0xe549  ldfld    class Microsoft.ReportingServices.Diagnostics.IServiceInstanceContext Microsoft.ReportingServices.Diagnostics.ThreadWorkItem::m_serviceInstanceContext
0xe54e  newobj   instance void Microsoft.ReportingServices.Diagnostics.BackgroundRequestContext::.ctor(class Microsoft.ReportingServices.Diagnostics.IServiceInstanceContext serviceInstanceContext)
0xe553  call     void Microsoft.ReportingServices.Diagnostics.ProcessingContext::InitializeRequestContext(class Microsoft.ReportingServices.Diagnostics.RequestContext context)
0xe558  ldarg.1
0xe559  unbox    WorkItemParameters
0xe55e  ldfld    class Microsoft.ReportingServices.Diagnostics.RunningJobContext WorkItemParameters::ctx
0xe563  stloc.1
0xe564  ldnull
0xe565  call     class Microsoft.ReportingServices.Diagnostics.RequestCache Microsoft.ReportingServices.Diagnostics.RequestCache::BindToThread(class Microsoft.ReportingServices.Diagnostics.RequestCache cache)
0xe56a  stloc.0
0xe56b  call     void Microsoft.ReportingServices.Diagnostics.RequestCache::InitializeForRequest()
0xe570  ldloca.s 2
0xe572  initobj  PreservedContext
0xe578  ldloca.s 2
0xe57a  call     instance void PreservedContext::Capture()
0xe57f  ldnull
0xe580  stloc.3
0xe581  ldc.i4.0
0xe582  stloc.s  4
0xe584  ldloc.1
0xe585  call     void Microsoft.ReportingServices.Diagnostics.ProcessingContext::set_JobContext(class Microsoft.ReportingServices.Diagnostics.RunningJobContext value)
0xe58a  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0xe58f  callvirt instance bool [mscorlib]System.Threading.Thread::get_IsThreadPoolThread()
0xe594  brtrue.s loc_E5B1
0xe596  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer()
0xe59b  ldc.i4.3
0xe59c  ldstr    aReQueuingOnATh// "Re-queuing on a threadpool thread"
0xe5a1  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xe5a6  ldarg.0
0xe5a7  call     void Microsoft.ReportingServices.Diagnostics.ReportServerThreadPool::TryQueueWorkItem(class Microsoft.ReportingServices.Diagnostics.ThreadWorkItem wkItem)
0xe5ac  ldc.i4.1
0xe5ad  stloc.s  4
0xe5af  br.s     loc_E604
0xe5b1  ldarg.0
0xe5b2  ldfld    class [mscorlib]System.Security.Principal.WindowsIdentity Microsoft.ReportingServices.Diagnostics.ThreadWorkItem::m_origThreadUser
0xe5b7  brfalse.s loc_E5C5
0xe5b9  ldarg.0
0xe5ba  ldfld    class [mscorlib]System.Security.Principal.WindowsIdentity Microsoft.ReportingServices.Diagnostics.ThreadWorkItem::m_origThreadUser
0xe5bf  callvirt instance class [mscorlib]System.Security.Principal.WindowsImpersonationContext [mscorlib]System.Security.Principal.WindowsIdentity::Impersonate()
0xe5c4  stloc.3
0xe5c5  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer()
0xe5ca  ldc.i4.4
0xe5cb  ldstr    aExecutingUserC// "Executing user callback"
0xe5d0  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xe5d5  ldloc.1
0xe5d6  ldarg.0
0xe5d7  ldfld    class [mscorlib]System.Threading.WaitCallback Microsoft.ReportingServices.Diagnostics.ThreadWorkItem::m_callback
0xe5dc  ldarg.0
0xe5dd  ldfld    object Microsoft.ReportingServices.Diagnostics.ThreadWorkItem::m_state
0xe5e2  ldarg.0
0xe5e3  ldfld    bool Microsoft.ReportingServices.Diagnostics.ThreadWorkItem::m_allowCancel
0xe5e8  newobj   instance void Microsoft.ReportingServices.Diagnostics.ThreadWorkItemCancelableStep::.ctor(class Microsoft.ReportingServices.Diagnostics.RunningJobContext jobCtx, class [mscorlib]System.Threading.WaitCallback callback, object callbackState, bool allowCancel)
0xe5ed  stloc.s  5
0xe5ef  ldloc.s  5
0xe5f1  callvirt instance void Microsoft.ReportingServices.Diagnostics.CancelablePhaseBase::ExecuteWrapper()
0xe5f6  leave.s  loc_E604
0xe5f8  ldloc.s  5
0xe5fa  brfalse.s loc_E603
0xe5fc  ldloc.s  5
0xe5fe  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xe603  endfinally
0xe604  leave.s  loc_E635
0xe606  ldloca.s 2
0xe608  call     instance void PreservedContext::Restore()
0xe60d  ldloc.s  4
0xe60f  brtrue.s loc_E62B
0xe611  ldarg.0
0xe612  ldfld    class [mscorlib]System.Security.Principal.WindowsIdentity Microsoft.ReportingServices.Diagnostics.ThreadWorkItem::m_origThreadUser
0xe617  brfalse.s loc_E62B
0xe619  ldarg.0
0xe61a  ldfld    class [mscorlib]System.Security.Principal.WindowsIdentity Microsoft.ReportingServices.Diagnostics.ThreadWorkItem::m_origThreadUser
0xe61f  callvirt instance void [mscorlib]System.Security.Principal.WindowsIdentity::Dispose()
0xe624  ldarg.0
0xe625  ldnull
0xe626  stfld    class [mscorlib]System.Security.Principal.WindowsIdentity Microsoft.ReportingServices.Diagnostics.ThreadWorkItem::m_origThreadUser
0xe62b  ldloc.3
0xe62c  brfalse.s loc_E634
0xe62e  ldloc.3
0xe62f  callvirt instance void [mscorlib]System.Security.Principal.WindowsImpersonationContext::Undo()
0xe634  endfinally
0xe635  leave.s  loc_E66E
0xe637  stloc.s  6
0xe639  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer()
0xe63e  ldc.i4.1
0xe63f  ldstr    aErrorInThreadF// "error in thread function: {0}"
0xe644  ldc.i4.1
0xe645  newarr   [mscorlib]System.Object
0xe64a  dup
0xe64b  ldc.i4.0
0xe64c  ldloc.s  6
0xe64e  stelem.ref
0xe64f  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string, object[])
0xe654  leave.s  loc_E66E
0xe656  call     void Microsoft.ReportingServices.Diagnostics.RequestCache::ReleaseReferenceAndDetach()
0xe65b  ldloc.0
0xe65c  call     class Microsoft.ReportingServices.Diagnostics.RequestCache Microsoft.ReportingServices.Diagnostics.RequestCache::BindToThread(class Microsoft.ReportingServices.Diagnostics.RequestCache cache)
0xe661  pop
0xe662  call     void Microsoft.ReportingServices.Diagnostics.ProcessingContext::EndRequestContext()
0xe667  call     int32 Microsoft.ReportingServices.Diagnostics.ReportServerThreadPool::DecrementCurrentReportThreads()
0xe66c  pop
0xe66d  endfinally
0xe66e  ret
```
