# Microsoft.ReportingServices.Diagnostics.CancelablePhaseBase::ExecuteWrapper

- ea: `0x9b60`
- end: `0x9c12`
- name: `Microsoft.ReportingServices.Diagnostics.CancelablePhaseBase::ExecuteWrapper`
- size: `178`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0xe540`

## callees

- `0x9b50`
- `0x9b60`
- `0x9c20`
- `0xaea0`
- `0xd700`
- `0xdfa0`
- `0xe120`
- `0xe140`
- `0xe160`
- `0x15b50`

## pseudocode

```c

```

## disassembly

```asm
0x9b60  ldarg.0
0x9b61  call     instance class Microsoft.ReportingServices.Diagnostics.ThreadJobContext Microsoft.ReportingServices.Diagnostics.CancelablePhaseBase::get_ThreadContext()
0x9b66  brtrue.s loc_9B91
0x9b68  ldarg.0
0x9b69  ldfld    class [mscorlib]System.Threading.WaitCallback Microsoft.ReportingServices.Diagnostics.CancelablePhaseBase::m_waitCallback
0x9b6e  brfalse.s loc_9B86
0x9b70  ldarg.0
0x9b71  ldfld    class [mscorlib]System.Threading.WaitCallback Microsoft.ReportingServices.Diagnostics.CancelablePhaseBase::m_waitCallback
0x9b76  ldarg.0
0x9b77  ldfld    object Microsoft.ReportingServices.Diagnostics.CancelablePhaseBase::m_callbackState
0x9b7c  callvirt instance void [mscorlib]System.Threading.WaitCallback::Invoke(object)
0x9b81  leave    loc_9C11
0x9b86  ldarg.0
0x9b87  callvirt instance void Microsoft.ReportingServices.Diagnostics.CancelablePhaseBase::Execute()
0x9b8c  leave    loc_9C11
0x9b91  nop
0x9b92  ldarg.0
0x9b93  call     instance class Microsoft.ReportingServices.Diagnostics.ThreadJobContext Microsoft.ReportingServices.Diagnostics.CancelablePhaseBase::get_ThreadContext()
0x9b98  callvirt instance void Microsoft.ReportingServices.Diagnostics.ThreadJobContext::BeginCancelableState()
0x9b9d  ldarg.0
0x9b9e  ldfld    class [mscorlib]System.Threading.WaitCallback Microsoft.ReportingServices.Diagnostics.CancelablePhaseBase::m_waitCallback
0x9ba3  brfalse.s loc_9BB8
0x9ba5  ldarg.0
0x9ba6  ldfld    class [mscorlib]System.Threading.WaitCallback Microsoft.ReportingServices.Diagnostics.CancelablePhaseBase::m_waitCallback
0x9bab  ldarg.0
0x9bac  ldfld    object Microsoft.ReportingServices.Diagnostics.CancelablePhaseBase::m_callbackState
0x9bb1  callvirt instance void [mscorlib]System.Threading.WaitCallback::Invoke(object)
0x9bb6  br.s     loc_9BBE
0x9bb8  ldarg.0
0x9bb9  callvirt instance void Microsoft.ReportingServices.Diagnostics.CancelablePhaseBase::Execute()
0x9bbe  leave.s  loc_9BCC
0x9bc0  ldarg.0
0x9bc1  call     instance class Microsoft.ReportingServices.Diagnostics.ThreadJobContext Microsoft.ReportingServices.Diagnostics.CancelablePhaseBase::get_ThreadContext()
0x9bc6  callvirt instance void Microsoft.ReportingServices.Diagnostics.ThreadJobContext::EndCancelableState()
0x9bcb  endfinally
0x9bcc  ldarg.0
0x9bcd  call     instance class Microsoft.ReportingServices.Diagnostics.ThreadJobContext Microsoft.ReportingServices.Diagnostics.CancelablePhaseBase::get_ThreadContext()
0x9bd2  callvirt instance void Microsoft.ReportingServices.Diagnostics.ThreadJobContext::WaitForCancelException()
0x9bd7  leave.s  loc_9C11
0x9bd9  stloc.0
0x9bda  ldarg.0
0x9bdb  call     instance class Microsoft.ReportingServices.Diagnostics.ThreadJobContext Microsoft.ReportingServices.Diagnostics.CancelablePhaseBase::get_ThreadContext()
0x9be0  callvirt instance class Microsoft.ReportingServices.Diagnostics.RunningJobContext Microsoft.ReportingServices.Diagnostics.ThreadJobContext::get_RunningJobContext()
0x9be5  callvirt instance class Microsoft.ReportingServices.Diagnostics.ReportExecutionInfo Microsoft.ReportingServices.Diagnostics.RunningJobContext::get_ExecutionInfo()
0x9bea  ldloc.0
0x9beb  callvirt instance class [mscorlib]System.Exception Microsoft.ReportingServices.Diagnostics.ReportExecutionInfo::SetStatusFromException(class [mscorlib]System.Exception e)
0x9bf0  stloc.1
0x9bf1  ldloc.1
0x9bf2  brfalse.s loc_9BF6
0x9bf4  ldloc.1
0x9bf5  throw
0x9bf6  rethrow
0x9bf8  ldsfld   class JobEventHandler Microsoft.ReportingServices.Diagnostics.CancelablePhaseBase::JobEnd
0x9bfd  brfalse.s loc_9C10
0x9bff  ldsfld   class JobEventHandler Microsoft.ReportingServices.Diagnostics.CancelablePhaseBase::JobEnd
0x9c04  ldarg.0
0x9c05  ldarg.0
0x9c06  ldfld    class Microsoft.ReportingServices.Diagnostics.RunningJobContext Microsoft.ReportingServices.Diagnostics.CancelablePhaseBase::m_jobCtx
0x9c0b  callvirt instance void JobEventHandler::Invoke(class Microsoft.ReportingServices.Diagnostics.CancelablePhaseBase sender, class Microsoft.ReportingServices.Diagnostics.RunningJobContext context)
0x9c10  endfinally
0x9c11  ret
```
