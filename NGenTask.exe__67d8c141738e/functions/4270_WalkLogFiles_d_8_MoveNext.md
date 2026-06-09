# <WalkLogFiles>d__8::MoveNext

- ea: `0x4270`
- end: `0x44ea`
- name: `<WalkLogFiles>d__8::MoveNext`
- size: `634`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: ``

## callees

- `0x2c30`
- `0x2c60`
- `0x3d20`
- `0x3e00`
- `0x3f10`
- `0x3f20`
- `0x4250`
- `0x4270`
- `0x44f0`

## pseudocode

```c

```

## disassembly

```asm
0x4270  ldarg.0
0x4271  ldfld    int32 <WalkLogFiles>d__8::<>1__state
0x4276  stloc.1
0x4277  ldarg.0
0x4278  ldfld    class NGenTask.LogWalker <WalkLogFiles>d__8::<>4__this
0x427d  stloc.2
0x427e  ldloc.1
0x427f  brfalse.s loc_428F
0x4281  ldloc.1
0x4282  ldc.i4.1
0x4283  beq      loc_4410
0x4288  ldc.i4.0
0x4289  stloc.0
0x428a  leave    loc_44E8
0x428f  ldarg.0
0x4290  ldc.i4.m1
0x4291  stfld    int32 <WalkLogFiles>d__8::<>1__state
0x4296  ldarg.0
0x4297  ldc.i4.0
0x4298  stfld    int32 <WalkLogFiles>d__8::<logFileCount>5__2
0x429d  ldarg.0
0x429e  ldstr    aLog// "*.log"
0x42a3  stfld    string <WalkLogFiles>d__8::<filterPattern>5__3
0x42a8  ldarg.0
0x42a9  ldloc.2
0x42aa  call     instance class [mscorlib]System.Collections.Generic.IEnumerable`1<class NGenTask.ContainerDirectoryInfo> NGenTask.LogWalker::WalkLogDirectories()
0x42af  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<class NGenTask.ContainerDirectoryInfo>::GetEnumerator()
0x42b4  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class NGenTask.ContainerDirectoryInfo> <WalkLogFiles>d__8::<>7__wrap3
0x42b9  ldarg.0
0x42ba  ldc.i4.s 0xFD
0x42bc  stfld    int32 <WalkLogFiles>d__8::<>1__state
0x42c1  br       loc_44B6
0x42c6  ldarg.0
0x42c7  ldarg.0
0x42c8  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class NGenTask.ContainerDirectoryInfo> <WalkLogFiles>d__8::<>7__wrap3
0x42cd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class NGenTask.ContainerDirectoryInfo>::get_Current()
0x42d2  stfld    class NGenTask.ContainerDirectoryInfo <WalkLogFiles>d__8::<actualLogDirectory>5__5
0x42d7  ldarg.0
0x42d8  ldfld    class NGenTask.ContainerDirectoryInfo <WalkLogFiles>d__8::<actualLogDirectory>5__5
0x42dd  callvirt instance class [mscorlib]System.IO.DirectoryInfo NGenTask.ContainerDirectoryInfo::get_Directory()
0x42e2  callvirt instance valuetype [mscorlib]System.IO.FileAttributes [mscorlib]System.IO.FileSystemInfo::get_Attributes()
0x42e7  ldc.i4   0x400
0x42ec  and
0x42ed  brtrue   loc_44B6
0x42f2  ldarg.0
0x42f3  ldarg.0
0x42f4  ldfld    class NGenTask.ContainerDirectoryInfo <WalkLogFiles>d__8::<actualLogDirectory>5__5
0x42f9  callvirt instance class [mscorlib]System.IO.DirectoryInfo NGenTask.ContainerDirectoryInfo::get_Directory()
0x42fe  ldarg.0
0x42ff  ldfld    string <WalkLogFiles>d__8::<filterPattern>5__3
0x4304  callvirt instance class [mscorlib]System.IO.FileInfo[] [mscorlib]System.IO.DirectoryInfo::GetFiles(string)
0x4309  stfld    class [mscorlib]System.IO.FileInfo[] <WalkLogFiles>d__8::<>7__wrap5
0x430e  ldarg.0
0x430f  ldc.i4.0
0x4310  stfld    int32 <WalkLogFiles>d__8::<>7__wrap6
0x4315  br       loc_4495
0x431a  ldarg.0
0x431b  ldarg.0
0x431c  ldfld    class [mscorlib]System.IO.FileInfo[] <WalkLogFiles>d__8::<>7__wrap5
0x4321  ldarg.0
0x4322  ldfld    int32 <WalkLogFiles>d__8::<>7__wrap6
0x4327  ldelem.ref
0x4328  stfld    class [mscorlib]System.IO.FileInfo <WalkLogFiles>d__8::<logFile>5__8
0x432d  ldarg.0
0x432e  ldfld    bool <WalkLogFiles>d__8::fOldLogs
0x4333  ldc.i4.0
0x4334  ceq
0x4336  stloc.3
0x4337  ldarg.0
0x4338  ldc.i4.0
0x4339  stfld    bool <WalkLogFiles>d__8::<fLogAgeRejected>5__9
0x433e  ldarg.0
0x433f  ldflda   valuetype [mscorlib]System.TimeSpan <WalkLogFiles>d__8::<timeSinceWritten>5__10
0x4344  initobj  [mscorlib]System.TimeSpan
0x434a  ldarg.0
0x434b  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_UtcNow()
0x4350  ldarg.0
0x4351  ldfld    class [mscorlib]System.IO.FileInfo <WalkLogFiles>d__8::<logFile>5__8
0x4356  callvirt instance valuetype [mscorlib]System.DateTime [mscorlib]System.IO.FileSystemInfo::get_LastWriteTimeUtc()
0x435b  call     valuetype [mscorlib]System.TimeSpan [mscorlib]System.DateTime::op_Subtraction(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0x4360  stfld    valuetype [mscorlib]System.TimeSpan <WalkLogFiles>d__8::<timeSinceWritten>5__10
0x4365  ldarg.0
0x4366  ldflda   valuetype [mscorlib]System.TimeSpan <WalkLogFiles>d__8::<timeSinceWritten>5__10
0x436b  call     instance float64 [mscorlib]System.TimeSpan::get_TotalDays()
0x4370  ldloc.2
0x4371  ldfld    float64 NGenTask.LogWalker::m_logsScavengeThreshold
0x4376  ble.un.s loc_4386
0x4378  ldarg.0
0x4379  ldfld    bool <WalkLogFiles>d__8::fOldLogs
0x437e  stloc.3
0x437f  ldarg.0
0x4380  ldc.i4.1
0x4381  stfld    bool <WalkLogFiles>d__8::<fLogAgeRejected>5__9
0x4386  leave.s  loc_43BA
0x4388  stloc.s  4
0x438a  ldc.i4.0
0x438b  ldloc.s  4
0x438d  ldstr    aErrorWhileScan// "Error while scanning logs"
0x4392  ldc.i4.0
0x4393  newarr   [mscorlib]System.Object
0x4398  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x439d  ldc.i4.0
0x439e  stloc.3
0x439f  leave.s  loc_43BA
0x43a1  stloc.s  5
0x43a3  ldc.i4.0
0x43a4  ldloc.s  5
0x43a6  ldstr    aErrorWhileScan// "Error while scanning logs"
0x43ab  ldc.i4.0
0x43ac  newarr   [mscorlib]System.Object
0x43b1  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x43b6  ldc.i4.0
0x43b7  stloc.3
0x43b8  leave.s  loc_43BA
0x43ba  ldloc.3
0x43bb  brfalse.s loc_443A
0x43bd  ldloc.2
0x43be  call     instance bool NGenTask.LogWalker::IsStopRequested()
0x43c3  brfalse.s loc_43CC
0x43c5  ldc.i4.0
0x43c6  stloc.0
0x43c7  br       loc_44CE
0x43cc  ldc.i4.3
0x43cd  ldstr    aFoundLog0// "Found log {0}."
0x43d2  ldc.i4.1
0x43d3  newarr   [mscorlib]System.Object
0x43d8  dup
0x43d9  ldc.i4.0
0x43da  ldarg.0
0x43db  ldfld    class [mscorlib]System.IO.FileInfo <WalkLogFiles>d__8::<logFile>5__8
0x43e0  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x43e5  stelem.ref
0x43e6  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x43eb  ldarg.0
0x43ec  ldarg.0
0x43ed  ldfld    class NGenTask.ContainerDirectoryInfo <WalkLogFiles>d__8::<actualLogDirectory>5__5
0x43f2  ldarg.0
0x43f3  ldfld    class [mscorlib]System.IO.FileInfo <WalkLogFiles>d__8::<logFile>5__8
0x43f8  newobj   instance void NGenTask.ContainerFileInfo::.ctor(class NGenTask.ContainerDirectoryInfo template, class [mscorlib]System.IO.FileInfo logFile)
0x43fd  stfld    class NGenTask.ContainerFileInfo <WalkLogFiles>d__8::<>2__current
0x4402  ldarg.0
0x4403  ldc.i4.1
0x4404  stfld    int32 <WalkLogFiles>d__8::<>1__state
0x4409  ldc.i4.1
0x440a  stloc.0
0x440b  leave    loc_44E8
0x4410  ldarg.0
0x4411  ldc.i4.s 0xFD
0x4413  stfld    int32 <WalkLogFiles>d__8::<>1__state
0x4418  ldarg.0
0x4419  ldfld    int32 <WalkLogFiles>d__8::<logFileCount>5__2
0x441e  ldc.i4.1
0x441f  add
0x4420  stloc.s  6
0x4422  ldarg.0
0x4423  ldloc.s  6
0x4425  stfld    int32 <WalkLogFiles>d__8::<logFileCount>5__2
0x442a  ldloc.s  6
0x442c  ldc.i4   0x3E8
0x4431  blt.s    loc_443A
0x4433  ldc.i4.0
0x4434  stloc.0
0x4435  br       loc_44CE
0x443a  ldarg.0
0x443b  ldfld    bool <WalkLogFiles>d__8::<fLogAgeRejected>5__9
0x4440  brfalse.s loc_4474
0x4442  ldc.i4.3
0x4443  ldstr    aSkipping0DueTo// "Skipping {0} due to log age. : Age {1}"
0x4448  ldc.i4.2
0x4449  newarr   [mscorlib]System.Object
0x444e  dup
0x444f  ldc.i4.0
0x4450  ldarg.0
0x4451  ldfld    class [mscorlib]System.IO.FileInfo <WalkLogFiles>d__8::<logFile>5__8
0x4456  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x445b  stelem.ref
0x445c  dup
0x445d  ldc.i4.1
0x445e  ldarg.0
0x445f  ldflda   valuetype [mscorlib]System.TimeSpan <WalkLogFiles>d__8::<timeSinceWritten>5__10
0x4464  call     instance float64 [mscorlib]System.TimeSpan::get_TotalDays()
0x4469  box      [mscorlib]System.Double
0x446e  stelem.ref
0x446f  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x4474  ldarg.0
0x4475  ldflda   valuetype [mscorlib]System.TimeSpan <WalkLogFiles>d__8::<timeSinceWritten>5__10
0x447a  initobj  [mscorlib]System.TimeSpan
0x4480  ldarg.0
0x4481  ldnull
0x4482  stfld    class [mscorlib]System.IO.FileInfo <WalkLogFiles>d__8::<logFile>5__8
0x4487  ldarg.0
0x4488  ldarg.0
0x4489  ldfld    int32 <WalkLogFiles>d__8::<>7__wrap6
0x448e  ldc.i4.1
0x448f  add
0x4490  stfld    int32 <WalkLogFiles>d__8::<>7__wrap6
0x4495  ldarg.0
0x4496  ldfld    int32 <WalkLogFiles>d__8::<>7__wrap6
0x449b  ldarg.0
0x449c  ldfld    class [mscorlib]System.IO.FileInfo[] <WalkLogFiles>d__8::<>7__wrap5
0x44a1  ldlen
0x44a2  conv.i4
0x44a3  blt      loc_431A
0x44a8  ldarg.0
0x44a9  ldnull
0x44aa  stfld    class [mscorlib]System.IO.FileInfo[] <WalkLogFiles>d__8::<>7__wrap5
0x44af  ldarg.0
0x44b0  ldnull
0x44b1  stfld    class NGenTask.ContainerDirectoryInfo <WalkLogFiles>d__8::<actualLogDirectory>5__5
0x44b6  ldarg.0
0x44b7  ldfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class NGenTask.ContainerDirectoryInfo> <WalkLogFiles>d__8::<>7__wrap3
0x44bc  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x44c1  brtrue   loc_42C6
0x44c6  ldarg.0
0x44c7  call     instance void <WalkLogFiles>d__8::<>m__Finally1()
0x44cc  br.s     loc_44D6
0x44ce  ldarg.0
0x44cf  call     instance void <WalkLogFiles>d__8::<>m__Finally1()
0x44d4  leave.s  loc_44E8
0x44d6  ldarg.0
0x44d7  ldnull
0x44d8  stfld    class [mscorlib]System.Collections.Generic.IEnumerator`1<class NGenTask.ContainerDirectoryInfo> <WalkLogFiles>d__8::<>7__wrap3
0x44dd  ldc.i4.0
0x44de  stloc.0
0x44df  leave.s  loc_44E8
0x44e1  ldarg.0
0x44e2  call     instance void <WalkLogFiles>d__8::System.IDisposable.Dispose()
0x44e7  endfinally
0x44e8  ldloc.0
0x44e9  ret
```
