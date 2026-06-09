# NGenTask.TaskExecutive::Stop

- ea: `0xec0`
- end: `0xf12`
- name: `NGenTask.TaskExecutive::Stop`
- size: `82`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x19d0`

## callees

- `0xec0`
- `0x10b0`
- `0x2c30`

## string_xrefs

- `0xec1`: `Task was interrupted by task scheduler`

## pseudocode

```c

```

## disassembly

```asm
0xec0  ldc.i4.m1
0xec1  ldstr    aTaskWasInterru// "Task was interrupted by task scheduler"
0xec6  ldc.i4.0
0xec7  newarr   [mscorlib]System.Object
0xecc  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0xed1  ldarg.0
0xed2  ldfld    object NGenTask.TaskExecutive::m_stopLock
0xed7  stloc.0
0xed8  ldc.i4.0
0xed9  stloc.1
0xeda  ldloc.0
0xedb  ldloca.s 1
0xedd  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0xee2  ldarg.0
0xee3  ldc.i4.1
0xee4  volatile.
0xee6  stfld    modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) bool NGenTask.TaskExecutive::m_stopRequested
0xeeb  ldarg.0
0xeec  call     instance void NGenTask.TaskExecutive::StopWorker()
0xef1  leave.s  loc_EFD
0xef3  ldloc.1
0xef4  brfalse.s loc_EFC
0xef6  ldloc.0
0xef7  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0xefc  endfinally
0xefd  ldarg.0
0xefe  ldfld    class [mscorlib]System.Threading.AutoResetEvent NGenTask.TaskExecutive::m_ngenInterruptFinishedEvent
0xf03  brfalse.s loc_F11
0xf05  ldarg.0
0xf06  ldfld    class [mscorlib]System.Threading.AutoResetEvent NGenTask.TaskExecutive::m_ngenInterruptFinishedEvent
0xf0b  callvirt instance bool [mscorlib]System.Threading.EventWaitHandle::Set()
0xf10  pop
0xf11  ret
```
