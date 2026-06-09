# NGenTask.TaskExecutive::RunInternal

- ea: `0x310`
- end: `0xeb4`
- name: `NGenTask.TaskExecutive::RunInternal`
- size: `2980`
- prototype: ``
- caller_count: `1`
- callee_count: `45`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x2c0`

## callees

- `0x10`
- `0x160`
- `0x310`
- `0xf20`
- `0x1120`
- `0x11c0`
- `0x12d0`
- `0x1380`
- `0x1400`
- `0x1560`
- `0x1ad0`
- `0x1cf0`
- `0x1d30`
- `0x1d80`
- `0x1db0`
- `0x1e00`
- `0x1e30`
- `0x1f20`
- `0x1f90`
- `0x2020`
- `0x2050`
- `0x20d0`
- `0x20e0`
- `0x2220`
- `0x2240`
- `0x24f0`
- `0x2540`
- `0x25a0`
- `0x25c0`
- `0x2790`
- `0x2c30`
- `0x2c60`
- `0x2ce0`
- `0x2df0`
- `0x2ec0`
- `0x31c0`
- `0x32e0`
- `0x34a0`
- `0x35d0`
- `0x3760`
- `0x3d90`
- `0x3dc0`
- `0x3e00`
- `0x3ed0`
- `0x3f80`

## string_xrefs

- `0x4b9`: `/CriticalTaskTimeLimit:`
- `0x586`: `Unrecognized command line option {0}`
- `0x788`: `GetSystemWindowsDirectory failed`
- `0x7fb`: `RemoveTaskDelayStartTrigger`
- `0x856`: `Deleted HKLM\{0}`
- `0x884`: `Failed to delete HKLM\{0}`
- `0x8fa`: `Deleted {0}`
- `0x91f`: `Failed to delete {0}`
- `0x96a`: `Unable to get user profile directory location`
- `0x995`: `Running pending update`
- `0x9a7`: `Update /queue`
- `0xa36`: `Critical idle task executing high-priority queued items`
- `0xa92`: `Critical idle task execution time limit reached`
- `0xaed`: `High-priority NGen task completed successfully`
- `0xb9a`: `Automatic NGen disabled in registry`
- `0xc64`: `System.Core, Version=4.0.0.0, Culture=neutral, PublicKeyToken=b77a5c561934e089`
- `0xe88`: `NGen task completed successfully`

## pseudocode

```c

```

## disassembly

```asm
0x310  ldarg.0
0x311  volatile.
0x313  ldfld    modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) bool NGenTask.TaskExecutive::m_stopRequested
0x318  brfalse.s loc_31C
0x31a  ldc.i4.0
0x31b  ret
0x31c  ldnull
0x31d  stloc.0
0x31e  ldnull
0x31f  stloc.1
0x320  ldnull
0x321  stloc.2
0x322  ldnull
0x323  stloc.3
0x324  ldc.r8   -1.0
0x32d  stloc.s  4
0x32f  ldc.r8   -1.0
0x338  stloc.s  5
0x33a  ldc.r8   300.0
0x343  stloc.s  6
0x345  ldc.i4.0
0x346  stloc.s  7
0x348  ldc.i4.0
0x349  stloc.s  8
0x34b  ldc.i4.0
0x34c  stloc.s  9
0x34e  ldnull
0x34f  newobj   instance void NGenTask.ContainerRootDirectoryInfo::.ctor(class [mscorlib]System.IO.DirectoryInfo logDir)
0x354  stloc.s  0xA
0x356  ldnull
0x357  stloc.s  0xB
0x359  ldnull
0x35a  stloc.s  0xC
0x35c  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x361  stloc.s  0xD
0x363  ldarg.1
0x364  stloc.s  0xE
0x366  ldc.i4.0
0x367  stloc.s  0xF
0x369  br       loc_5A1
0x36e  ldloc.s  0xE
0x370  ldloc.s  0xF
0x372  ldelem.ref
0x373  stloc.s  0x10
0x375  ldloc.s  0x10
0x377  ldstr    aNic// "/NIC:"
0x37c  ldc.i4.5
0x37d  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x382  brfalse.s loc_39E
0x384  ldloc.s  0xA
0x386  ldloc.s  0x10
0x388  ldc.i4.5
0x389  callvirt instance string [mscorlib]System.String::Substring(int32)
0x38e  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x393  newobj   instance void NGenTask.ContainerDirectoryInfo::.ctor(class NGenTask.ContainerDirectoryInfo template, class [mscorlib]System.IO.DirectoryInfo logDir)
0x398  stloc.0
0x399  br       loc_59B
0x39e  ldloc.s  0x10
0x3a0  ldstr    aUsagelog// "/UsageLog:"
0x3a5  ldc.i4.5
0x3a6  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x3ab  brfalse.s loc_3C8
0x3ad  ldloc.s  0xA
0x3af  ldloc.s  0x10
0x3b1  ldc.i4.s 0xA
0x3b3  callvirt instance string [mscorlib]System.String::Substring(int32)
0x3b8  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x3bd  newobj   instance void NGenTask.ContainerDirectoryInfo::.ctor(class NGenTask.ContainerDirectoryInfo template, class [mscorlib]System.IO.DirectoryInfo logDir)
0x3c2  stloc.2
0x3c3  br       loc_59B
0x3c8  ldloc.s  0x10
0x3ca  ldstr    aLocalappdata_0// "/LocalAppData:"
0x3cf  ldc.i4.5
0x3d0  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x3d5  brfalse.s loc_3F1
0x3d7  ldloc.s  0xA
0x3d9  ldloc.s  0x10
0x3db  ldc.i4.s 0xE
0x3dd  callvirt instance string [mscorlib]System.String::Substring(int32)
0x3e2  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x3e7  callvirt instance void NGenTask.ContainerDirectoryInfo::SetDirectory(class [mscorlib]System.IO.DirectoryInfo dir)
0x3ec  br       loc_59B
0x3f1  ldloc.s  0x10
0x3f3  ldstr    aNgen// "/NGen:"
0x3f8  ldc.i4.5
0x3f9  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x3fe  brfalse.s loc_41F
0x400  ldloc.s  0x10
0x402  ldc.i4.6
0x403  callvirt instance string [mscorlib]System.String::Substring(int32)
0x408  stloc.3
0x409  ldloc.s  0xD
0x40b  ldc.i4.s 0x20
0x40d  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x412  ldloc.s  0x10
0x414  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x419  pop
0x41a  br       loc_59B
0x41f  ldloc.s  0x10
0x421  ldstr    aMaxlogage// "/MaxLogAge:"
0x426  ldc.i4.5
0x427  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x42c  brfalse.s loc_454
0x42e  ldloc.s  0x10
0x430  ldc.i4.s 0xB
0x432  callvirt instance string [mscorlib]System.String::Substring(int32)
0x437  call     float64 NGenTask.TaskExecutive::TryParseDouble(string value)
0x43c  stloc.s  4
0x43e  ldloc.s  0xD
0x440  ldc.i4.s 0x20
0x442  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x447  ldloc.s  0x10
0x449  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x44e  pop
0x44f  br       loc_59B
0x454  ldloc.s  0x10
0x456  ldstr    aMaxniage// "/MaxNIAge:"
0x45b  ldc.i4.5
0x45c  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x461  brfalse.s loc_489
0x463  ldloc.s  0x10
0x465  ldc.i4.s 0xA
0x467  callvirt instance string [mscorlib]System.String::Substring(int32)
0x46c  call     float64 NGenTask.TaskExecutive::TryParseDouble(string value)
0x471  stloc.s  5
0x473  ldloc.s  0xD
0x475  ldc.i4.s 0x20
0x477  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x47c  ldloc.s  0x10
0x47e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x483  pop
0x484  br       loc_59B
0x489  ldloc.s  0x10
0x48b  ldstr    aRuntimewide// "/RuntimeWide"
0x490  ldc.i4.5
0x491  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x496  brfalse.s loc_4A0
0x498  ldc.i4.1
0x499  stloc.s  8
0x49b  br       loc_59B
0x4a0  ldloc.s  0x10
0x4a2  ldstr    aCritical// "/Critical"
0x4a7  ldc.i4.5
0x4a8  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x4ad  brfalse.s loc_4B7
0x4af  ldc.i4.1
0x4b0  stloc.s  9
0x4b2  br       loc_59B
0x4b7  ldloc.s  0x10
0x4b9  ldstr    aCriticaltaskti// "/CriticalTaskTimeLimit:"
0x4be  ldc.i4.5
0x4bf  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x4c4  brfalse.s loc_4DB
0x4c6  ldloc.s  0x10
0x4c8  ldc.i4.s 0x17
0x4ca  callvirt instance string [mscorlib]System.String::Substring(int32)
0x4cf  call     float64 NGenTask.TaskExecutive::TryParseDouble(string value)
0x4d4  stloc.s  6
0x4d6  br       loc_59B
0x4db  ldloc.s  0x10
0x4dd  ldstr    aStopevent// "/StopEvent:"
0x4e2  ldc.i4.5
0x4e3  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x4e8  brfalse.s loc_53E
0x4ea  ldarg.0
0x4eb  ldc.i4.0
0x4ec  newobj   instance void [mscorlib]System.Threading.ManualResetEvent::.ctor(bool)
0x4f1  stfld    class [mscorlib]System.Threading.ManualResetEvent NGenTask.TaskExecutive::m_parentStopEvent
0x4f6  ldarg.0
0x4f7  ldfld    class [mscorlib]System.Threading.ManualResetEvent NGenTask.TaskExecutive::m_parentStopEvent
0x4fc  ldloc.s  0x10
0x4fe  ldc.i4.s 0xB
0x500  callvirt instance string [mscorlib]System.String::Substring(int32)
0x505  call     int32 [mscorlib]System.Int32::Parse(string)
0x50a  call     native int [mscorlib]System.IntPtr::op_Explicit(int32)
0x50f  ldc.i4.1
0x510  newobj   instance void [mscorlib]Microsoft.Win32.SafeHandles.SafeWaitHandle::.ctor(native int, bool)
0x515  callvirt instance void [mscorlib]System.Threading.WaitHandle::set_SafeWaitHandle(class [mscorlib]Microsoft.Win32.SafeHandles.SafeWaitHandle)
0x51a  ldarg.0
0x51b  ldftn    instance void NGenTask.TaskExecutive::ParentStopEventListener()
0x521  newobj   instance void [mscorlib]System.Threading.ThreadStart::.ctor(object, native int)
0x526  newobj   instance void [mscorlib]System.Threading.Thread::.ctor(class [mscorlib]System.Threading.ThreadStart)
0x52b  stloc.s  0x11
0x52d  ldloc.s  0x11
0x52f  ldc.i4.1
0x530  callvirt instance void [mscorlib]System.Threading.Thread::set_IsBackground(bool)
0x535  ldloc.s  0x11
0x537  callvirt instance void [mscorlib]System.Threading.Thread::Start()
0x53c  br.s     loc_59B
0x53e  ldloc.s  0x10
0x540  ldstr    aVerbose// "/Verbose"
0x545  ldc.i4.5
0x546  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x54b  brfalse.s loc_562
0x54d  ldc.i4.3
0x54e  call     void NGenTask.Logger::set_MaxLogLevel(valuetype LogLevel value)
0x553  ldloc.s  0xD
0x555  ldstr    aVerbose_0// " /Verbose"
0x55a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x55f  pop
0x560  br.s     loc_59B
0x562  ldloc.s  0x10
0x564  ldstr    aSilent// "/Silent"
0x569  ldc.i4.5
0x56a  callvirt instance bool [mscorlib]System.String::Equals(string, valuetype [mscorlib]System.StringComparison)
0x56f  brfalse.s loc_586
0x571  ldc.i4.1
0x572  call     void NGenTask.Logger::set_MaxLogLevel(valuetype LogLevel value)
0x577  ldloc.s  0xD
0x579  ldstr    aSilent_0// " /Silent"
0x57e  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x583  pop
0x584  br.s     loc_59B
0x586  ldstr    aUnrecognizedCo// "Unrecognized command line option {0}"
0x58b  ldc.i4.1
0x58c  newarr   [mscorlib]System.Object
0x591  dup
0x592  ldc.i4.0
0x593  ldloc.s  0x10
0x595  stelem.ref
0x596  call     void NGenTask.TaskExecutive::UsageError(string format, object[] args)
0x59b  ldloc.s  0xF
0x59d  ldc.i4.1
0x59e  add
0x59f  stloc.s  0xF
0x5a1  ldloc.s  0xF
0x5a3  ldloc.s  0xE
0x5a5  ldlen
0x5a6  conv.i4
0x5a7  blt      loc_36E
0x5ac  ldloc.s  9
0x5ae  brfalse.s loc_5C7
0x5b0  ldloc.s  8
0x5b2  brtrue.s loc_5C7
0x5b4  ldc.i4.0
0x5b5  ldstr    aCriticalCanOnl// "/Critical can only be used with /Runtim"...
0x5ba  ldc.i4.0
0x5bb  newarr   [mscorlib]System.Object
0x5c0  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x5c5  ldc.i4.m1
0x5c6  ret
0x5c7  ldarg.0
0x5c8  ldloc.s  8
0x5ca  ldloc.s  9
0x5cc  call     instance class NGenTask.FileLock NGenTask.TaskExecutive::GetTaskLock(bool runtimeWide, bool critical)
0x5d1  stloc.s  0x12
0x5d3  ldloc.s  0x12
0x5d5  brtrue.s loc_5DE
0x5d7  ldloc.s  9
0x5d9  ldc.i4.0
0x5da  ceq
0x5dc  br.s     loc_5DF
0x5de  ldc.i4.0
0x5df  ldloc.s  8
0x5e1  and
0x5e2  brfalse.s loc_5EC
0x5e4  ldc.i4.m1
0x5e5  stloc.s  0x19
0x5e7  leave    loc_EB1
0x5ec  ldloc.0
0x5ed  brtrue.s loc_607
0x5ef  ldloc.2
0x5f0  brtrue.s loc_607
0x5f2  ldarg.0
0x5f3  call     instance bool NGenTask.TaskExecutive::IsUsingPrivateStore()
0x5f8  brtrue.s loc_607
0x5fa  ldstr    aV20// "v2.0"
0x5ff  ldc.i4.0
0x600  call     bool NGenTask.TaskExecutive::OptimizeUsedBinaries(string version, bool defaultValue)
0x605  br.s     loc_608
0x607  ldc.i4.0
0x608  stloc.s  0x13
0x60a  ldloc.s  4
0x60c  ldc.r8   -1.0
0x615  beq.s    loc_624
0x617  ldloc.s  5
0x619  ldc.r8   -1.0
0x622  bne.un.s loc_6A0
0x624  call     valuetype [mscorlib]System.Nullable`1<float64> NGenTask.TaskExecutive::MinDaysInDisuse()
0x629  stloc.s  0x1B
0x62b  ldloca.s 0x1B
0x62d  call     instance bool valuetype [mscorlib]System.Nullable`1<float64>::get_HasValue()
0x632  brtrue.s loc_63F
0x634  ldc.r8   30.0
0x63d  br.s     loc_646
0x63f  ldloca.s 0x1B
0x641  call     instance var<u1> valuetype [mscorlib]System.Nullable`1<float64>::GetValueOrDefault()
0x646  stloc.s  0x1A
0x648  ldloc.s  4
0x64a  ldc.r8   -1.0
0x653  bne.un.s loc_674
0x655  ldloc.s  0x1A
0x657  stloc.s  4
0x659  ldc.i4.3
0x65a  ldstr    aLogScavengeAft// "Log scavenge after {0} days"
0x65f  ldc.i4.1
0x660  newarr   [mscorlib]System.Object
0x665  dup
0x666  ldc.i4.0
0x667  ldloc.s  4
  ... truncated ...
```
