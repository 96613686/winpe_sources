# NGenTask.TaskExecutive::GetTaskLock

- ea: `0xf20`
- end: `0x1080`
- name: `NGenTask.TaskExecutive::GetTaskLock`
- size: `352`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `service_task`

## callers

- `0x310`

## callees

- `0xf20`
- `0x2020`
- `0x2c30`
- `0x2c60`
- `0x2ed0`
- `0x2f10`
- `0x2f20`
- `0x2f80`

## string_xrefs

- `0xf2c`: `ngentasklock.dat`
- `0xf3b`: `Attempting to acquire task lock.`
- `0xf54`: `Acquired task lock.`
- `0xf85`: `Critical task unable to acquire task lock. Attempting to stop non-critical task.`
- `0xfc7`: `Critical task unable to stop non-critical task. Attempting to kill non-critical task.`
- `0xfd7`: `NGenTask`
- `0x104e`: `Critical task unable to acquire task lock. Continuing without lock.`
- `0x1068`: `Error acquiring task lock`

## pseudocode

```c

```

## disassembly

```asm
0xf20  ldarg.1
0xf21  brtrue.s loc_F25
0xf23  ldnull
0xf24  ret
0xf25  nop
0xf26  ldarg.0
0xf27  call     instance string NGenTask.TaskExecutive::GetFrameworkPath()
0xf2c  ldstr    aNgentasklockDa// "ngentasklock.dat"
0xf31  call     string [mscorlib]System.IO.Path::Combine(string, string)
0xf36  stloc.0
0xf37  ldarg.2
0xf38  brtrue.s loc_F6D
0xf3a  ldc.i4.2
0xf3b  ldstr    aAttemptingToAc// "Attempting to acquire task lock."
0xf40  ldc.i4.0
0xf41  newarr   [mscorlib]System.Object
0xf46  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0xf4b  ldloc.0
0xf4c  newobj   instance void NGenTask.FileLock::.ctor(string lockName)
0xf51  stloc.s  4
0xf53  ldc.i4.2
0xf54  ldstr    aAcquiredTaskLo// "Acquired task lock."
0xf59  ldc.i4.0
0xf5a  newarr   [mscorlib]System.Object
0xf5f  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0xf64  ldloc.s  4
0xf66  stloc.s  5
0xf68  leave    loc_107D
0xf6d  newobj   instance void NGenTask.FileLock::.ctor()
0xf72  stloc.1
0xf73  ldloc.1
0xf74  ldloc.0
0xf75  callvirt instance bool NGenTask.FileLock::TryGetLock(string lockName)
0xf7a  brfalse.s loc_F84
0xf7c  ldloc.1
0xf7d  stloc.s  5
0xf7f  leave    loc_107D
0xf84  ldc.i4.2
0xf85  ldstr    aCriticalTaskUn// "Critical task unable to acquire task lo"...
0xf8a  ldc.i4.0
0xf8b  newarr   [mscorlib]System.Object
0xf90  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0xf95  call     int32 NGenTask.TaskHelper::CorStopNonCriticalTask()
0xf9a  ldc.i4.0
0xf9b  blt.s    loc_FC6
0xf9d  ldc.i4.0
0xf9e  stloc.s  6
0xfa0  br.s     loc_FC0
0xfa2  ldloc.1
0xfa3  ldloc.0
0xfa4  callvirt instance bool NGenTask.FileLock::TryGetLock(string lockName)
0xfa9  brfalse.s loc_FB3
0xfab  ldloc.1
0xfac  stloc.s  5
0xfae  leave    loc_107D
0xfb3  ldc.i4.s 0x64
0xfb5  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0xfba  ldloc.s  6
0xfbc  ldc.i4.1
0xfbd  add
0xfbe  stloc.s  6
0xfc0  ldloc.s  6
0xfc2  ldc.i4.s 0x14
0xfc4  blt.s    loc_FA2
0xfc6  ldc.i4.2
0xfc7  ldstr    aCriticalTaskUn_0// "Critical task unable to stop non-critic"...
0xfcc  ldc.i4.0
0xfcd  newarr   [mscorlib]System.Object
0xfd2  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0xfd7  ldstr    aNgentask// "NGenTask"
0xfdc  call     class [System]System.Diagnostics.Process[] [System]System.Diagnostics.Process::GetProcessesByName(string)
0xfe1  stloc.2
0xfe2  call     class [System]System.Diagnostics.Process [System]System.Diagnostics.Process::GetCurrentProcess()
0xfe7  stloc.3
0xfe8  ldloc.2
0xfe9  stloc.s  7
0xfeb  ldc.i4.0
0xfec  stloc.s  8
0xfee  br.s     loc_1032
0xff0  ldloc.s  7
0xff2  ldloc.s  8
0xff4  ldelem.ref
0xff5  stloc.s  9
0xff7  ldloc.s  9
0xff9  callvirt instance int32 [System]System.Diagnostics.Process::get_Id()
0xffe  ldloc.3
0xfff  callvirt instance int32 [System]System.Diagnostics.Process::get_Id()
0x1004  beq.s    loc_102C
0x1006  ldloc.s  9
0x1008  callvirt instance class [System]System.Diagnostics.ProcessModule [System]System.Diagnostics.Process::get_MainModule()
0x100d  callvirt instance string [System]System.Diagnostics.ProcessModule::get_FileName()
0x1012  ldloc.3
0x1013  callvirt instance class [System]System.Diagnostics.ProcessModule [System]System.Diagnostics.Process::get_MainModule()
0x1018  callvirt instance string [System]System.Diagnostics.ProcessModule::get_FileName()
0x101d  ldc.i4.5
0x101e  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x1023  brfalse.s loc_102C
0x1025  ldloc.s  9
0x1027  callvirt instance void [System]System.Diagnostics.Process::Kill()
0x102c  ldloc.s  8
0x102e  ldc.i4.1
0x102f  add
0x1030  stloc.s  8
0x1032  ldloc.s  8
0x1034  ldloc.s  7
0x1036  ldlen
0x1037  conv.i4
0x1038  blt.s    loc_FF0
0x103a  ldc.i4   0x3E8
0x103f  call     void [mscorlib]System.Threading.Thread::Sleep(int32)
0x1044  ldloc.1
0x1045  ldloc.0
0x1046  callvirt instance bool NGenTask.FileLock::TryGetLock(string lockName)
0x104b  brtrue.s loc_105E
0x104d  ldc.i4.1
0x104e  ldstr    aCriticalTaskUn_1// "Critical task unable to acquire task lo"...
0x1053  ldc.i4.0
0x1054  newarr   [mscorlib]System.Object
0x1059  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x105e  ldloc.1
0x105f  stloc.s  5
0x1061  leave.s  loc_107D
0x1063  stloc.s  0xA
0x1065  ldc.i4.0
0x1066  ldloc.s  0xA
0x1068  ldstr    aErrorAcquiring// "Error acquiring task lock"
0x106d  ldc.i4.0
0x106e  newarr   [mscorlib]System.Object
0x1073  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x1078  ldnull
0x1079  stloc.s  5
0x107b  leave.s  loc_107D
0x107d  ldloc.s  5
0x107f  ret
```
