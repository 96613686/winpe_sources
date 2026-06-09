# System.Windows.Input.PenThreadWorker::WorkerAddPenContext

- ea: `0x4c090`
- end: `0x4c10b`
- name: `System.Windows.Input.PenThreadWorker::WorkerAddPenContext`
- size: `123`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task`

## callers

- `0x4bdd0`

## callees

- `0x4c090`
- `0x1058d0`
- `0x146e40`
- `0x1495a0`
- `0x149a00`
- `0x149a20`

## string_xrefs

- `0x4c09b`: `Penservice_Disposed`

## pseudocode

```c

```

## disassembly

```asm
0x4c090  ldarg.0
0x4c091  volatile.
0x4c093  ldfld    modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) bool System.Windows.Input.PenThreadWorker::__disposed
0x4c098  brfalse.s loc_4C0AB
0x4c09a  ldnull
0x4c09b  ldstr    aPenserviceDisp// "Penservice_Disposed"
0x4c0a0  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x4c0a5  newobj   instance void [mscorlib]System.ObjectDisposedException::.ctor(string, string)
0x4c0aa  throw
0x4c0ab  ldarg.1
0x4c0ac  ldarg.0
0x4c0ad  newobj   instance void WorkerOperationAddContext::.ctor(class System.Windows.Input.PenContext penContext, class System.Windows.Input.PenThreadWorker penThreadWorker)
0x4c0b2  stloc.0
0x4c0b3  ldarg.0
0x4c0b4  ldfld    object System.Windows.Input.PenThreadWorker::_workerOperationLock
0x4c0b9  stloc.1
0x4c0ba  ldc.i4.0
0x4c0bb  stloc.2
0x4c0bc  ldloc.1
0x4c0bd  ldloca.s 2
0x4c0bf  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x4c0c4  ldarg.0
0x4c0c5  ldfld    class [mscorlib]System.Collections.Generic.List`1<class WorkerOperation> System.Windows.Input.PenThreadWorker::_workerOperation
0x4c0ca  ldloc.0
0x4c0cb  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class WorkerOperation>::Add(var<u1>)
0x4c0d0  leave.s  loc_4C0DC
0x4c0d2  ldloc.2
0x4c0d3  brfalse.s loc_4C0DB
0x4c0d5  ldloc.1
0x4c0d6  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x4c0db  endfinally
0x4c0dc  ldarg.0
0x4c0dd  ldflda   valuetype [WindowsBase]MS.Internal.SecurityCriticalData`1<native int> System.Windows.Input.PenThreadWorker::_pimcResetHandle
0x4c0e2  call     instance var<u1> valuetype [WindowsBase]MS.Internal.SecurityCriticalData`1<native int>::get_Value()
0x4c0e7  call     bool MS.Win32.Penimc.UnsafeNativeMethods::RaiseResetEvent([hasfieldmarshal] native int)
0x4c0ec  pop
0x4c0ed  ldloc.0
0x4c0ee  callvirt instance class [mscorlib]System.Threading.AutoResetEvent WorkerOperation::get_DoneEvent()
0x4c0f3  callvirt instance bool [mscorlib]System.Threading.WaitHandle::WaitOne()
0x4c0f8  pop
0x4c0f9  ldloc.0
0x4c0fa  callvirt instance class [mscorlib]System.Threading.AutoResetEvent WorkerOperation::get_DoneEvent()
0x4c0ff  callvirt instance void [mscorlib]System.Threading.WaitHandle::Close()
0x4c104  ldloc.0
0x4c105  callvirt instance bool WorkerOperationAddContext::get_Result()
0x4c10a  ret
```
