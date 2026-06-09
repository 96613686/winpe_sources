# System.Windows.Threading.DispatcherOperation::Wait_0

- ea: `0x3d7b0`
- end: `0x3d850`
- name: `System.Windows.Threading.DispatcherOperation::Wait_0`
- size: `160`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `installer_update`

## callers

- `0x3d790`

## callees

- `0x2c100`
- `0x3b170`
- `0x3b2f0`
- `0x3d770`
- `0x3d7b0`
- `0x59340`
- `0x59450`
- `0x59530`

## string_xrefs

- `0x3d7ee`: `ThreadMayNotWaitOnOperationsAlreadyExecutingOnTheSameThread`

## pseudocode

```c

```

## disassembly

```asm
0x3d7b0  ldarg.0
0x3d7b1  ldfld    valuetype System.Windows.Threading.DispatcherOperationStatus System.Windows.Threading.DispatcherOperation::_status
0x3d7b6  brfalse.s loc_3D7C1
0x3d7b8  ldarg.0
0x3d7b9  ldfld    valuetype System.Windows.Threading.DispatcherOperationStatus System.Windows.Threading.DispatcherOperation::_status
0x3d7be  ldc.i4.3
0x3d7bf  bne.un.s loc_3D81C
0x3d7c1  ldarga.s 1
0x3d7c3  call     instance float64 [mscorlib]System.TimeSpan::get_TotalMilliseconds()
0x3d7c8  ldc.r8   0.0
0x3d7d1  beq.s    loc_3D81C
0x3d7d3  ldarg.0
0x3d7d4  ldfld    class System.Windows.Threading.Dispatcher System.Windows.Threading.DispatcherOperation::_dispatcher
0x3d7d9  callvirt instance class [mscorlib]System.Threading.Thread System.Windows.Threading.Dispatcher::get_Thread()
0x3d7de  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x3d7e3  bne.un.s loc_3D80E
0x3d7e5  ldarg.0
0x3d7e6  ldfld    valuetype System.Windows.Threading.DispatcherOperationStatus System.Windows.Threading.DispatcherOperation::_status
0x3d7eb  ldc.i4.3
0x3d7ec  bne.un.s loc_3D7FE
0x3d7ee  ldstr    aThreadmaynotwa// "ThreadMayNotWaitOnOperationsAlreadyExec"...
0x3d7f3  call     string MS.Internal.WindowsBase.SR::Get(string id)
0x3d7f8  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x3d7fd  throw
0x3d7fe  ldarg.0
0x3d7ff  ldarg.1
0x3d800  newobj   instance void DispatcherOperationFrame::.ctor(class System.Windows.Threading.DispatcherOperation op, valuetype [mscorlib]System.TimeSpan timeout)
0x3d805  stloc.0
0x3d806  ldloc.0
0x3d807  call     void System.Windows.Threading.Dispatcher::PushFrame(class System.Windows.Threading.DispatcherFrame frame)
0x3d80c  br.s     loc_3D81C
0x3d80e  ldarg.0
0x3d80f  ldarg.1
0x3d810  newobj   instance void DispatcherOperationEvent::.ctor(class System.Windows.Threading.DispatcherOperation op, valuetype [mscorlib]System.TimeSpan timeout)
0x3d815  stloc.1
0x3d816  ldloc.1
0x3d817  callvirt instance void DispatcherOperationEvent::WaitOne()
0x3d81c  ldarg.0
0x3d81d  ldfld    bool System.Windows.Threading.DispatcherOperation::_useAsyncSemantics
0x3d822  brfalse.s loc_3D849
0x3d824  ldarg.0
0x3d825  ldfld    valuetype System.Windows.Threading.DispatcherOperationStatus System.Windows.Threading.DispatcherOperation::_status
0x3d82a  ldc.i4.2
0x3d82b  beq.s    loc_3D836
0x3d82d  ldarg.0
0x3d82e  ldfld    valuetype System.Windows.Threading.DispatcherOperationStatus System.Windows.Threading.DispatcherOperation::_status
0x3d833  ldc.i4.1
0x3d834  bne.un.s loc_3D849
0x3d836  ldarg.0
0x3d837  call     instance class [mscorlib]System.Threading.Tasks.Task System.Windows.Threading.DispatcherOperation::get_Task()
0x3d83c  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x3d841  stloc.2
0x3d842  ldloca.s 2
0x3d844  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x3d849  ldarg.0
0x3d84a  ldfld    valuetype System.Windows.Threading.DispatcherOperationStatus System.Windows.Threading.DispatcherOperation::_status
0x3d84f  ret
```
