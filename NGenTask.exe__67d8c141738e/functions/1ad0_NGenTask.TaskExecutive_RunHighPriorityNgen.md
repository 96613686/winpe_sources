# NGenTask.TaskExecutive::RunHighPriorityNgen

- ea: `0x1ad0`
- end: `0x1ce4`
- name: `NGenTask.TaskExecutive::RunHighPriorityNgen`
- size: `532`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `service_task`

## callers

- `0x310`

## callees

- `0x1ad0`
- `0x1d30`
- `0x2020`
- `0x2150`
- `0x2170`
- `0x2190`
- `0x21b0`
- `0x24f0`
- `0x2790`
- `0x2c30`
- `0x2eb0`
- `0x2f20`

## string_xrefs

- `0x1ad8`: `ngentasknewworklock.dat`
- `0x1b7a`: `Executing normal maintenance tasks`
- `0x1c98`: `RemoveTaskBootTrigger`

## pseudocode

```c

```

## disassembly

```asm
0x1ad0  ldnull
0x1ad1  stloc.0
0x1ad2  ldarg.0
0x1ad3  call     instance string NGenTask.TaskExecutive::GetFrameworkPath()
0x1ad8  ldstr    aNgentasknewwor// "ngentasknewworklock.dat"
0x1add  call     string [mscorlib]System.IO.Path::Combine(string, string)
0x1ae2  stloc.1
0x1ae3  ldc.i4.0
0x1ae4  stloc.2
0x1ae5  ldloc.1
0x1ae6  newobj   instance void NGenTask.FileLock::.ctor(string lockName)
0x1aeb  dup
0x1aec  stloc.0
0x1aed  stloc.3
0x1aee  ldarg.0
0x1aef  call     instance bool NGenTask.TaskExecutive::IsRootStoreDirty()
0x1af4  stloc.2
0x1af5  ldloc.2
0x1af6  brfalse.s loc_1B05
0x1af8  ldarg.0
0x1af9  ldc.i4.1
0x1afa  call     instance void NGenTask.TaskExecutive::SetHighPriorityFlag(bool state)
0x1aff  ldarg.0
0x1b00  call     instance void NGenTask.TaskExecutive::SetRootStoreClean()
0x1b05  leave.s  loc_1B11
0x1b07  ldloc.3
0x1b08  brfalse.s loc_1B10
0x1b0a  ldloc.3
0x1b0b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1b10  endfinally
0x1b11  ldloc.2
0x1b12  brfalse.s loc_1B57
0x1b14  ldc.i4.3
0x1b15  ldstr    aRootstoreDirty// "Rootstore dirty.  Waiting another 5 sec"...
0x1b1a  ldc.i4.0
0x1b1b  newarr   [mscorlib]System.Object
0x1b20  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x1b25  ldc.i4   0x1388
0x1b2a  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0x1b2f  ldloc.1
0x1b30  newobj   instance void NGenTask.FileLock::.ctor(string lockName)
0x1b35  dup
0x1b36  stloc.0
0x1b37  stloc.s  4
0x1b39  ldarg.0
0x1b3a  call     instance bool NGenTask.TaskExecutive::IsRootStoreDirty()
0x1b3f  brfalse.s loc_1B49
0x1b41  ldarg.0
0x1b42  call     instance void NGenTask.TaskExecutive::SetRootStoreClean()
0x1b47  leave.s  loc_1B14
0x1b49  leave.s  loc_1B57
0x1b4b  ldloc.s  4
0x1b4d  brfalse.s loc_1B56
0x1b4f  ldloc.s  4
0x1b51  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1b56  endfinally
0x1b57  ldarg.0
0x1b58  ldarg.0
0x1b59  call     instance bool NGenTask.TaskExecutive::IsHighPriorityFlagSet()
0x1b5e  stfld    bool NGenTask.TaskExecutive::m_highPriorityMode
0x1b63  ldarg.0
0x1b64  ldarg.0
0x1b65  ldfld    bool NGenTask.TaskExecutive::m_highPriorityMode
0x1b6a  ldarg.2
0x1b6b  ldc.i4.0
0x1b6c  call     instance void NGenTask.TaskExecutive::RuntimeWideTaskStarted(bool isHighPriorityMode, bool isAfterServicing, bool critical)
0x1b71  ldarg.0
0x1b72  ldfld    bool NGenTask.TaskExecutive::m_highPriorityMode
0x1b77  brtrue.s loc_1B8C
0x1b79  ldc.i4.2
0x1b7a  ldstr    aExecutingNorma// "Executing normal maintenance tasks"
0x1b7f  ldc.i4.0
0x1b80  newarr   [mscorlib]System.Object
0x1b85  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x1b8a  ldc.i4.0
0x1b8b  ret
0x1b8c  ldc.i4.2
0x1b8d  ldstr    aExecutingHighP// "Executing high priority queued items"
0x1b92  ldc.i4.0
0x1b93  newarr   [mscorlib]System.Object
0x1b98  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x1b9d  ldarg.0
0x1b9e  ldc.i4.0
0x1b9f  stfld    bool NGenTask.TaskExecutive::m_ngenClientInterrupt
0x1ba4  ldarg.0
0x1ba5  call     instance bool NGenTask.TaskExecutive::IsWorkForbidden()
0x1baa  brfalse.s loc_1BAE
0x1bac  ldc.i4.1
0x1bad  ret
0x1bae  ldarg.0
0x1baf  ldarg.1
0x1bb0  call     valuetype Policy NGenTask.TaskHelper::CorGetNGenPolicy()
0x1bb5  ldc.i4.1
0x1bb6  beq.s    loc_1BBF
0x1bb8  ldstr    aExecutequeuedi// "ExecuteQueuedItems 2"
0x1bbd  br.s     loc_1BC4
0x1bbf  ldstr    aExecutequeuedi_0// "ExecuteQueuedItems"
0x1bc4  ldnull
0x1bc5  call     instance int32 NGenTask.TaskExecutive::RunNGenCommandNoRetry(string ngenCommand, string arguments, string container)
0x1bca  pop
0x1bcb  ldarg.0
0x1bcc  ldfld    object NGenTask.TaskExecutive::m_stopLock
0x1bd1  stloc.s  5
0x1bd3  ldc.i4.0
0x1bd4  stloc.s  6
0x1bd6  ldloc.s  5
0x1bd8  ldloca.s 6
0x1bda  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x1bdf  ldarg.0
0x1be0  volatile.
0x1be2  ldfld    modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) bool NGenTask.TaskExecutive::m_stopRequested
0x1be7  brfalse.s loc_1BF1
0x1be9  ldc.i4.1
0x1bea  stloc.s  7
0x1bec  leave    loc_1CE1
0x1bf1  leave.s  loc_1BFF
0x1bf3  ldloc.s  6
0x1bf5  brfalse.s loc_1BFE
0x1bf7  ldloc.s  5
0x1bf9  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x1bfe  endfinally
0x1bff  ldarg.0
0x1c00  ldfld    bool NGenTask.TaskExecutive::m_ngenClientInterrupt
0x1c05  brfalse.s loc_1C4A
0x1c07  ldarg.0
0x1c08  ldfld    class [mscorlib]System.Threading.AutoResetEvent NGenTask.TaskExecutive::m_ngenInterruptFinishedEvent
0x1c0d  callvirt instance bool [mscorlib]System.Threading.WaitHandle::WaitOne()
0x1c12  pop
0x1c13  ldarg.0
0x1c14  ldfld    object NGenTask.TaskExecutive::m_stopLock
0x1c19  stloc.s  8
0x1c1b  ldc.i4.0
0x1c1c  stloc.s  9
0x1c1e  ldloc.s  8
0x1c20  ldloca.s 9
0x1c22  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x1c27  ldarg.0
0x1c28  volatile.
0x1c2a  ldfld    modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) bool NGenTask.TaskExecutive::m_stopRequested
0x1c2f  brfalse.s loc_1C39
0x1c31  ldc.i4.1
0x1c32  stloc.s  7
0x1c34  leave    loc_1CE1
0x1c39  leave    loc_1CD2
0x1c3e  ldloc.s  9
0x1c40  brfalse.s loc_1C49
0x1c42  ldloc.s  8
0x1c44  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x1c49  endfinally
0x1c4a  ldc.i4.2
0x1c4b  ldstr    aFinishedHighPr// "Finished high priority work.  Checking "...
0x1c50  ldc.i4.0
0x1c51  newarr   [mscorlib]System.Object
0x1c56  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x1c5b  ldc.i4.0
0x1c5c  stloc.2
0x1c5d  ldloc.1
0x1c5e  newobj   instance void NGenTask.FileLock::.ctor(string lockName)
0x1c63  dup
0x1c64  stloc.0
0x1c65  stloc.s  0xA
0x1c67  ldarg.0
0x1c68  call     instance bool NGenTask.TaskExecutive::IsRootStoreDirty()
0x1c6d  brfalse.s loc_1C79
0x1c6f  ldc.i4.1
0x1c70  stloc.2
0x1c71  ldarg.0
0x1c72  call     instance void NGenTask.TaskExecutive::SetRootStoreClean()
0x1c77  leave.s  loc_1CB5
0x1c79  ldloc.2
0x1c7a  brfalse.s loc_1C7E
0x1c7c  leave.s  loc_1CD2
0x1c7e  ldc.i4.3
0x1c7f  ldstr    aFinishedAllHig// "Finished all high priority queued items"...
0x1c84  ldc.i4.0
0x1c85  newarr   [mscorlib]System.Object
0x1c8a  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x1c8f  ldarg.0
0x1c90  ldc.i4.0
0x1c91  call     instance void NGenTask.TaskExecutive::SetHighPriorityFlag(bool state)
0x1c96  ldarg.0
0x1c97  ldarg.1
0x1c98  ldstr    aRemovetaskboot// "RemoveTaskBootTrigger"
0x1c9d  ldnull
0x1c9e  call     instance int32 NGenTask.TaskExecutive::RunNGenCommandNoRetry(string ngenCommand, string arguments, string container)
0x1ca3  pop
0x1ca4  ldc.i4.1
0x1ca5  stloc.s  7
0x1ca7  leave.s  loc_1CE1
0x1ca9  ldloc.s  0xA
0x1cab  brfalse.s loc_1CB4
0x1cad  ldloc.s  0xA
0x1caf  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x1cb4  endfinally
0x1cb5  ldc.i4.3
0x1cb6  ldstr    aRootstoreDirty// "Rootstore dirty.  Waiting another 5 sec"...
0x1cbb  ldc.i4.0
0x1cbc  newarr   [mscorlib]System.Object
0x1cc1  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x1cc6  ldc.i4   0x1388
0x1ccb  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0x1cd0  br.s     loc_1C5D
0x1cd2  ldarg.0
0x1cd3  ldfld    bool NGenTask.TaskExecutive::m_ngenClientInterrupt
0x1cd8  ldloc.2
0x1cd9  or
0x1cda  brtrue   loc_1B9D
0x1cdf  ldc.i4.1
0x1ce0  ret
0x1ce1  ldloc.s  7
0x1ce3  ret
```
