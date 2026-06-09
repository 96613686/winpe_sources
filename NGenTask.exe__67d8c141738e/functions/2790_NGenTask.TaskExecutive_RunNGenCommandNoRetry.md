# NGenTask.TaskExecutive::RunNGenCommandNoRetry

- ea: `0x2790`
- end: `0x290c`
- name: `NGenTask.TaskExecutive::RunNGenCommandNoRetry`
- size: `380`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: `service_task, broker_com_uri`

## callers

- `0x310`
- `0x1ad0`
- `0x25c0`

## callees

- `0x2790`
- `0x2c30`
- `0x2c60`
- `0x2cd0`
- `0x2ea0`
- `0x3070`
- `0x30a0`
- `0x30c0`
- `0x30f0`
- `0x3190`

## string_xrefs

- `0x27a1`: ` /LegacyServiceBehavior`
- `0x28f5`: `Error running NGen command`

## pseudocode

```c

```

## disassembly

```asm
0x2790  ldarg.0
0x2791  volatile.
0x2793  ldfld    modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) bool NGenTask.TaskExecutive::m_stopRequested
0x2798  brfalse.s loc_279D
0x279a  ldc.i4.s 0xFE
0x279c  ret
0x279d  ldc.i4.s 0xFE
0x279f  stloc.0
0x27a0  ldarg.2
0x27a1  ldstr    aLegacyserviceb// " /LegacyServiceBehavior"
0x27a6  call     string [mscorlib]System.String::Concat(string, string)
0x27ab  starg.s  2
0x27ad  call     valuetype LogLevel NGenTask.Logger::get_MaxLogLevel()
0x27b2  ldc.i4.1
0x27b3  bgt.s    loc_27C2
0x27b5  ldarg.2
0x27b6  ldstr    aSilent_0// " /Silent"
0x27bb  call     string [mscorlib]System.String::Concat(string, string)
0x27c0  starg.s  2
0x27c2  nop
0x27c3  ldarg.3
0x27c4  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x27c9  brfalse.s loc_27E6
0x27cb  ldc.i4.3
0x27cc  ldstr    aExecuting01// "Executing: {0} {1}"
0x27d1  ldc.i4.2
0x27d2  newarr   [mscorlib]System.Object
0x27d7  dup
0x27d8  ldc.i4.0
0x27d9  ldarg.1
0x27da  stelem.ref
0x27db  dup
0x27dc  ldc.i4.1
0x27dd  ldarg.2
0x27de  stelem.ref
0x27df  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x27e4  br.s     loc_2803
0x27e6  ldc.i4.3
0x27e7  ldstr    aExecuting01InC// "Executing: {0} {1} in container {2}"
0x27ec  ldc.i4.3
0x27ed  newarr   [mscorlib]System.Object
0x27f2  dup
0x27f3  ldc.i4.0
0x27f4  ldarg.1
0x27f5  stelem.ref
0x27f6  dup
0x27f7  ldc.i4.1
0x27f8  ldarg.2
0x27f9  stelem.ref
0x27fa  dup
0x27fb  ldc.i4.2
0x27fc  ldarg.3
0x27fd  stelem.ref
0x27fe  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x2803  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x2808  stloc.1
0x2809  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x280e  stloc.2
0x280f  ldc.i4.0
0x2810  stloc.3
0x2811  ldnull
0x2812  ldstr    asc_89E8// "\""
0x2817  ldarg.1
0x2818  ldstr    asc_89EC// "\" "
0x281d  ldarg.2
0x281e  call     string [mscorlib]System.String::Concat(string, string, string, string)
0x2823  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x2828  ldarg.3
0x2829  ldloca.s 1
0x282b  ldloca.s 2
0x282d  ldloca.s 3
0x282f  call     bool NGenTask.TaskHelper::CorCreateNGenProcess(string command, class [mscorlib]System.Text.StringBuilder arguments, string moniker, [out] native int& hProcessHandle, [out] native int& hThreadHandle, [out] int32& pid)
0x2834  brfalse  loc_28D7
0x2839  ldarg.0
0x283a  ldfld    object NGenTask.TaskExecutive::m_stopLock
0x283f  stloc.s  4
0x2841  ldc.i4.0
0x2842  stloc.s  5
0x2844  ldloc.s  4
0x2846  ldloca.s 5
0x2848  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x284d  ldarg.0
0x284e  ldfld    class NGenTask.ChildProcess NGenTask.TaskExecutive::m_childProcess
0x2853  brfalse.s loc_2867
0x2855  ldarg.0
0x2856  ldfld    class NGenTask.ChildProcess NGenTask.TaskExecutive::m_childProcess
0x285b  callvirt instance void [mscorlib]System.Runtime.InteropServices.SafeHandle::Dispose()
0x2860  ldarg.0
0x2861  ldnull
0x2862  stfld    class NGenTask.ChildProcess NGenTask.TaskExecutive::m_childProcess
0x2867  ldarg.0
0x2868  ldloc.1
0x2869  ldc.i4.0
0x286a  newobj   instance void NGenTask.ChildProcess::.ctor(native int handle, valuetype ProcessType type)
0x286f  stfld    class NGenTask.ChildProcess NGenTask.TaskExecutive::m_childProcess
0x2874  ldarg.0
0x2875  volatile.
0x2877  ldfld    modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) bool NGenTask.TaskExecutive::m_stopRequested
0x287c  brfalse.s loc_28A8
0x287e  ldarg.0
0x287f  ldfld    class NGenTask.ChildProcess NGenTask.TaskExecutive::m_childProcess
0x2884  callvirt instance void NGenTask.ChildProcess::Kill()
0x2889  leave.s  loc_28A2
0x288b  stloc.s  6
0x288d  ldc.i4.0
0x288e  ldloc.s  6
0x2890  ldstr    aErrorStoppingN// "Error stopping NGen process"
0x2895  ldc.i4.0
0x2896  newarr   [mscorlib]System.Object
0x289b  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x28a0  leave.s  loc_28A2
0x28a2  ldc.i4.s 0xFE
0x28a4  stloc.s  7
0x28a6  leave.s  loc_2909
0x28a8  leave.s  loc_28B6
0x28aa  ldloc.s  5
0x28ac  brfalse.s loc_28B5
0x28ae  ldloc.s  4
0x28b0  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x28b5  endfinally
0x28b6  ldarg.0
0x28b7  ldfld    class NGenTask.ChildProcess NGenTask.TaskExecutive::m_childProcess
0x28bc  brfalse.s loc_28D7
0x28be  ldarg.0
0x28bf  ldfld    class NGenTask.ChildProcess NGenTask.TaskExecutive::m_childProcess
0x28c4  callvirt instance bool NGenTask.ChildProcess::WaitForExit()
0x28c9  brfalse.s loc_28D7
0x28cb  ldarg.0
0x28cc  ldfld    class NGenTask.ChildProcess NGenTask.TaskExecutive::m_childProcess
0x28d1  callvirt instance int32 NGenTask.ChildProcess::get_ExitCode()
0x28d6  stloc.0
0x28d7  leave.s  loc_28EE
0x28d9  ldloc.2
0x28da  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x28df  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x28e4  brfalse.s loc_28ED
0x28e6  ldloc.2
0x28e7  call     bool NGenTask.Win32Native::CloseHandle(native int handle)
0x28ec  pop
0x28ed  endfinally
0x28ee  leave.s  loc_2907
0x28f0  stloc.s  8
0x28f2  ldc.i4.0
0x28f3  ldloc.s  8
0x28f5  ldstr    aErrorRunningNg// "Error running NGen command"
0x28fa  ldc.i4.0
0x28fb  newarr   [mscorlib]System.Object
0x2900  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x2905  leave.s  loc_2907
0x2907  ldloc.0
0x2908  ret
0x2909  ldloc.s  7
0x290b  ret
```
