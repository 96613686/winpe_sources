# Microsoft.ReportingServices.Library.MultithreadedConnectionManager::AcquireLock

- ea: `0x3bf0`
- end: `0x3cbc`
- name: `Microsoft.ReportingServices.Library.MultithreadedConnectionManager::AcquireLock`
- size: `204`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x9300`

## callees

- `0x3bf0`
- `0x3d20`

## pseudocode

```c

```

## disassembly

```asm
0x3bf0  ldarg.0
0x3bf1  ldfld    valuetype LockState Microsoft.ReportingServices.Library.MultithreadedConnectionManager::_lockState
0x3bf6  brtrue   loc_3C91
0x3bfb  call     int32 Microsoft.ReportingServices.Library.MultithreadedConnectionManager::get_LockTimeoutSeconds()
0x3c00  dup
0x3c01  conv.r8
0x3c02  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0x3c07  stloc.0
0x3c08  ldc.i4.0
0x3c09  bgt.s    loc_3C1C
0x3c0b  ldc.r8   -1.0
0x3c14  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromMilliseconds(float64)
0x3c19  stloc.0
0x3c1a  br.s     loc_3C32
0x3c1c  ldloca.s 0
0x3c1e  ldc.r8   30.0
0x3c27  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::FromSeconds(float64)
0x3c2c  call     instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeSpan::Add(valuetype [mscorlib]System.TimeSpan)
0x3c31  pop
0x3c32  ldc.i4.0
0x3c33  stloc.1
0x3c34  call     class [System]System.Diagnostics.Stopwatch [System]System.Diagnostics.Stopwatch::StartNew()
0x3c39  stloc.2
0x3c3a  br.s     loc_3C8E
0x3c3c  ldarg.0
0x3c3d  ldfld    valuetype LockState Microsoft.ReportingServices.Library.MultithreadedConnectionManager::_lockState
0x3c42  stloc.3
0x3c43  ldloc.3
0x3c44  ldc.i4.1
0x3c45  sub
0x3c46  ldc.i4.1
0x3c47  pop
0x3c48  pop
0x3c49  ldarg.0
0x3c4a  ldfld    object Microsoft.ReportingServices.Library.MultithreadedConnectionManager::_connectionSync
0x3c4f  ldloc.0
0x3c50  call     bool [mscorlib]System.Threading.Monitor::TryEnter(object, valuetype [mscorlib]System.TimeSpan)
0x3c55  dup
0x3c56  stloc.1
0x3c57  brfalse.s loc_3C79
0x3c59  ldarg.0
0x3c5a  ldarg.0
0x3c5b  ldfld    int32 Microsoft.ReportingServices.Library.MultithreadedConnectionManager::_lockDepth
0x3c60  ldc.i4.1
0x3c61  add
0x3c62  stfld    int32 Microsoft.ReportingServices.Library.MultithreadedConnectionManager::_lockDepth
0x3c67  ldarg.0
0x3c68  call     class [mscorlib]System.Threading.Thread [mscorlib]System.Threading.Thread::get_CurrentThread()
0x3c6d  callvirt instance int32 [mscorlib]System.Threading.Thread::get_ManagedThreadId()
0x3c72  stfld    int32 Microsoft.ReportingServices.Library.MultithreadedConnectionManager::_lockedThreadId
0x3c77  br.s     loc_3C8E
0x3c79  ldloc.2
0x3c7a  callvirt instance valuetype [mscorlib]System.TimeSpan [System]System.Diagnostics.Stopwatch::get_Elapsed()
0x3c7f  ldloc.0
0x3c80  call     bool [mscorlib]System.TimeSpan::op_GreaterThan(valuetype [mscorlib]System.TimeSpan, valuetype [mscorlib]System.TimeSpan)
0x3c85  brfalse.s loc_3C8E
0x3c87  ldarg.0
0x3c88  ldc.i4.1
0x3c89  stfld    valuetype LockState Microsoft.ReportingServices.Library.MultithreadedConnectionManager::_lockState
0x3c8e  ldloc.1
0x3c8f  brfalse.s loc_3C3C
0x3c91  ldarg.0
0x3c92  ldfld    valuetype LockState Microsoft.ReportingServices.Library.MultithreadedConnectionManager::_lockState
0x3c97  brfalse.s loc_3CBB
0x3c99  ldnull
0x3c9a  ldstr    aUnableToAcquir// "Unable to acquire connection monitor, r"...
0x3c9f  ldarg.0
0x3ca0  ldflda   valuetype LockState Microsoft.ReportingServices.Library.MultithreadedConnectionManager::_lockState
0x3ca5  constrained. LockState
0x3cab  callvirt instance string [mscorlib]System.Object::ToString()
0x3cb0  call     string [mscorlib]System.String::Concat(string, string)
0x3cb5  newobj   instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.ReportServerStorageException::.ctor(class [mscorlib]System.Exception, string)
0x3cba  throw
0x3cbb  ret
```
