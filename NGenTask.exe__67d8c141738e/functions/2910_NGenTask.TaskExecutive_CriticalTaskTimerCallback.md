# NGenTask.TaskExecutive::CriticalTaskTimerCallback

- ea: `0x2910`
- end: `0x2955`
- name: `NGenTask.TaskExecutive::CriticalTaskTimerCallback`
- size: `69`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `service_task`

## callees

- `0x10b0`
- `0x2910`
- `0x2c30`
- `0x2ec0`

## string_xrefs

- `0x2911`: `Critical idle task execution time limit reached`

## pseudocode

```c

```

## disassembly

```asm
0x2910  ldc.i4.2
0x2911  ldstr    aCriticalIdleTa_0// "Critical idle task execution time limit"...
0x2916  ldc.i4.0
0x2917  newarr   [mscorlib]System.Object
0x291c  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x2921  ldc.i4.0
0x2922  call     int32 NGenTask.TaskHelper::CorSetCriticalTaskState(bool bEnabled)
0x2927  pop
0x2928  ldarg.0
0x2929  ldfld    object NGenTask.TaskExecutive::m_stopLock
0x292e  stloc.0
0x292f  ldc.i4.0
0x2930  stloc.1
0x2931  ldloc.0
0x2932  ldloca.s 1
0x2934  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x2939  ldarg.0
0x293a  ldc.i4.1
0x293b  volatile.
0x293d  stfld    modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) bool NGenTask.TaskExecutive::m_stopRequested
0x2942  ldarg.0
0x2943  call     instance void NGenTask.TaskExecutive::StopWorker()
0x2948  leave.s  loc_2954
0x294a  ldloc.1
0x294b  brfalse.s loc_2953
0x294d  ldloc.0
0x294e  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x2953  endfinally
0x2954  ret
```
