# Microsoft.ReportingServices.Diagnostics.ReportServerThreadPool::TryQueueWorkItem

- ea: `0xb030`
- end: `0xb0ab`
- name: `Microsoft.ReportingServices.Diagnostics.ReportServerThreadPool::TryQueueWorkItem`
- size: `123`
- prototype: ``
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, broker_com_uri`

## callers

- `0xe540`

## callees

- `0xa240`
- `0xb030`
- `0xb100`
- `0xb2a0`
- `0xe480`
- `0xe4b0`
- `0xe4c0`
- `0xe4d0`
- `0xe4e0`
- `0xe4f0`
- `0x101c0`
- `0x10310`
- `0x15ef0`

## string_xrefs

- `0xb03d`: `Thread pool pressure. Using current thread for a work item.`
- `0xb065`: `Spawning new thread for a work item.`

## pseudocode

```c

```

## disassembly

```asm
0xb030  call     bool Microsoft.ReportingServices.Diagnostics.ReportServerThreadPool::IsThreadPoolPressure()
0xb035  brfalse.s loc_B05F
0xb037  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer()
0xb03c  ldc.i4.4
0xb03d  ldstr    aThreadPoolPres// "Thread pool pressure. Using current thr"...
0xb042  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xb047  ldarg.0
0xb048  callvirt instance class [mscorlib]System.Threading.WaitCallback Microsoft.ReportingServices.Diagnostics.ThreadWorkItem::get_OriginalCallback()
0xb04d  ldarg.0
0xb04e  callvirt instance object Microsoft.ReportingServices.Diagnostics.ThreadWorkItem::get_State()
0xb053  callvirt instance void [mscorlib]System.Threading.WaitCallback::Invoke(object)
0xb058  ldarg.0
0xb059  callvirt instance void Microsoft.ReportingServices.Diagnostics.ThreadWorkItem::Close()
0xb05e  ret
0xb05f  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobsTracer()
0xb064  ldc.i4.4
0xb065  ldstr    aSpawningNewThr// "Spawning new thread for a work item."
0xb06a  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0xb06f  ldarg.0
0xb070  callvirt instance class Microsoft.ReportingServices.Diagnostics.PreQueueDelegate Microsoft.ReportingServices.Diagnostics.ThreadWorkItem::get_PreQueue()
0xb075  brfalse.s loc_B088
0xb077  ldarg.0
0xb078  callvirt instance class Microsoft.ReportingServices.Diagnostics.PreQueueDelegate Microsoft.ReportingServices.Diagnostics.ThreadWorkItem::get_PreQueue()
0xb07d  ldarg.0
0xb07e  callvirt instance object Microsoft.ReportingServices.Diagnostics.ThreadWorkItem::get_PreQueueState()
0xb083  callvirt instance void Microsoft.ReportingServices.Diagnostics.PreQueueDelegate::Invoke(object args)
0xb088  call     class Microsoft.ReportingServices.Diagnostics.RunningJobContext Microsoft.ReportingServices.Diagnostics.ProcessingContext::get_JobContext()
0xb08d  stloc.0
0xb08e  ldarg.0
0xb08f  callvirt instance class [mscorlib]System.Threading.WaitCallback Microsoft.ReportingServices.Diagnostics.ThreadWorkItem::get_FullCallback()
0xb094  ldloc.0
0xb095  call     class Microsoft.ReportingServices.Diagnostics.RequestCache Microsoft.ReportingServices.Diagnostics.RequestCache::GetCurrentAndAddReference()
0xb09a  newobj   instance void WorkItemParameters::.ctor(class Microsoft.ReportingServices.Diagnostics.RunningJobContext ctx, class Microsoft.ReportingServices.Diagnostics.RequestCache requestCache)
0xb09f  box      WorkItemParameters
0xb0a4  call     bool [mscorlib]System.Threading.ThreadPool::QueueUserWorkItem(class [mscorlib]System.Threading.WaitCallback, object)
0xb0a9  pop
0xb0aa  ret
```
