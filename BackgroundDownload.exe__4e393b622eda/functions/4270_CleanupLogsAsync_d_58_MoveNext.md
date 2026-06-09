# <CleanupLogsAsync>d__58::MoveNext

- ea: `0x4270`
- end: `0x4601`
- name: `<CleanupLogsAsync>d__58::MoveNext`
- size: `913`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: ``

## callees

- `0x18d0`
- `0x18e0`
- `0x1a60`
- `0x40b0`
- `0x40e0`
- `0x40f0`
- `0x4230`
- `0x4270`

## pseudocode

```c

```

## disassembly

```asm
0x4270  ldarg.0
0x4271  ldfld    int32 <CleanupLogsAsync>d__58::<>1__state
0x4276  stloc.0
0x4277  ldarg.0
0x4278  ldfld    class Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase <CleanupLogsAsync>d__58::<>4__this
0x427d  stloc.1
0x427e  ldloc.0
0x427f  brfalse.s loc_42C1
0x4281  ldloc.1
0x4282  ldarg.0
0x4283  ldfld    valuetype [mscorlib]System.Threading.CancellationToken <CleanupLogsAsync>d__58::cancellationToken
0x4288  callvirt instance class [mscorlib]System.Threading.Tasks.Task Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::InitializeAsync(valuetype [mscorlib]System.Threading.CancellationToken cancellationToken)
0x428d  callvirt instance valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter [mscorlib]System.Threading.Tasks.Task::GetAwaiter()
0x4292  stloc.s  8
0x4294  ldloca.s 8
0x4296  call     instance bool [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::get_IsCompleted()
0x429b  brtrue.s loc_42DE
0x429d  ldarg.0
0x429e  ldc.i4.0
0x429f  dup
0x42a0  stloc.0
0x42a1  stfld    int32 <CleanupLogsAsync>d__58::<>1__state
0x42a6  ldarg.0
0x42a7  ldloc.s  8
0x42a9  stfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <CleanupLogsAsync>d__58::<>u__1
0x42ae  ldarg.0
0x42af  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <CleanupLogsAsync>d__58::<>t__builder
0x42b4  ldloca.s 8
0x42b6  ldarg.0
0x42b7  call     T0x2B00004A
0x42bc  leave    loc_4600
0x42c1  ldarg.0
0x42c2  ldfld    valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <CleanupLogsAsync>d__58::<>u__1
0x42c7  stloc.s  8
0x42c9  ldarg.0
0x42ca  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.TaskAwaiter <CleanupLogsAsync>d__58::<>u__1
0x42cf  initobj  [mscorlib]System.Runtime.CompilerServices.TaskAwaiter
0x42d5  ldarg.0
0x42d6  ldc.i4.m1
0x42d7  dup
0x42d8  stloc.0
0x42d9  stfld    int32 <CleanupLogsAsync>d__58::<>1__state
0x42de  ldloca.s 8
0x42e0  call     instance void [mscorlib]System.Runtime.CompilerServices.TaskAwaiter::GetResult()
0x42e5  ldloc.1
0x42e6  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_FileSystem()
0x42eb  ldloc.1
0x42ec  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_FileSystem()
0x42f1  callvirt instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::get_TemporaryDirectory()
0x42f6  ldsfld   string Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::GeneralBGDownloadLogPrefix
0x42fb  ldstr    asc_8466// "*"
0x4300  call     string [mscorlib]System.String::Concat(string, string)
0x4305  ldc.i4.0
0x4306  callvirt instance string[] [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.IFileSystem::GetFiles(string, string, bool)
0x430b  stloc.2
0x430c  ldloc.2
0x430d  ldsfld   class [mscorlib]System.Func`2<string, bool> <>c::<>9__58_0
0x4312  dup
0x4313  brtrue.s loc_432C
0x4315  pop
0x4316  ldsfld   class <>c <>c::<>9
0x431b  ldftn    instance bool <>c::<CleanupLogsAsync>b__58_0(string x)
0x4321  newobj   instance void class [mscorlib]System.Func`2<string, bool>::.ctor(object, native int)
0x4326  dup
0x4327  stsfld   class [mscorlib]System.Func`2<string, bool> <>c::<>9__58_0
0x432c  call     T0x2B00004B
0x4331  ldsfld   class [mscorlib]System.Func`2<string, bool> <>c::<>9__58_1
0x4336  dup
0x4337  brtrue.s loc_4350
0x4339  pop
0x433a  ldsfld   class <>c <>c::<>9
0x433f  ldftn    instance bool <>c::<CleanupLogsAsync>b__58_1(string x)
0x4345  newobj   instance void class [mscorlib]System.Func`2<string, bool>::.ctor(object, native int)
0x434a  dup
0x434b  stsfld   class [mscorlib]System.Func`2<string, bool> <>c::<>9__58_1
0x4350  call     T0x2B00004B
0x4355  ldsfld   class [mscorlib]System.Func`2<string, string> <>c::<>9__58_2
0x435a  dup
0x435b  brtrue.s loc_4374
0x435d  pop
0x435e  ldsfld   class <>c <>c::<>9
0x4363  ldftn    instance string <>c::<CleanupLogsAsync>b__58_2(string x)
0x4369  newobj   instance void class [mscorlib]System.Func`2<string, string>::.ctor(object, native int)
0x436e  dup
0x436f  stsfld   class [mscorlib]System.Func`2<string, string> <>c::<>9__58_2
0x4374  call     class [mscorlib]System.StringComparer [mscorlib]System.StringComparer::get_InvariantCultureIgnoreCase()
0x4379  call     T0x2B00004C
0x437e  ldloc.1
0x437f  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_Services()
0x4384  ldloc.1
0x4385  ldfld    int32 Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::successLogLimit
0x438a  newobj   instance void LogFileQueue::.ctor(class [mscorlib]System.IServiceProvider services, int32 capacity)
0x438f  stloc.3
0x4390  ldloc.1
0x4391  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_Services()
0x4396  ldloc.1
0x4397  ldfld    int32 Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::errorLogLimit
0x439c  newobj   instance void LogFileQueue::.ctor(class [mscorlib]System.IServiceProvider services, int32 capacity)
0x43a1  stloc.s  4
0x43a3  ldloc.1
0x43a4  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_Services()
0x43a9  ldloc.1
0x43aa  ldfld    int32 Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::cancelLogLimit
0x43af  newobj   instance void LogFileQueue::.ctor(class [mscorlib]System.IServiceProvider services, int32 capacity)
0x43b4  stloc.s  5
0x43b6  ldloc.1
0x43b7  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_Services()
0x43bc  ldloc.1
0x43bd  ldfld    int32 Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::precheckFailureLogLimit
0x43c2  newobj   instance void LogFileQueue::.ctor(class [mscorlib]System.IServiceProvider services, int32 capacity)
0x43c7  stloc.s  6
0x43c9  ldloc.1
0x43ca  call     instance class [mscorlib]System.IServiceProvider Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::get_Services()
0x43cf  ldloc.1
0x43d0  ldfld    int32 Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::updateCheckOnlyFailureLogLimit
0x43d5  newobj   instance void LogFileQueue::.ctor(class [mscorlib]System.IServiceProvider services, int32 capacity)
0x43da  stloc.s  7
0x43dc  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class [mscorlib]System.Collections.Generic.IEnumerable`1<string>::GetEnumerator()
0x43e1  stloc.s  9
0x43e3  br       loc_4592
0x43e8  ldloc.s  9
0x43ea  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<string>::get_Current()
0x43ef  stloc.s  0xA
0x43f1  newobj   instance void <>c__DisplayClass58_0::.ctor()
0x43f6  stloc.s  0xB
0x43f8  ldloc.s  0xB
0x43fa  ldloc.s  0xA
0x43fc  call     string [mscorlib]System.IO.Path::GetFileNameWithoutExtension(string)
0x4401  stfld    string <>c__DisplayClass58_0::prefix
0x4406  ldloc.2
0x4407  ldloc.s  0xB
0x4409  ldftn    instance bool <>c__DisplayClass58_0::<CleanupLogsAsync>b__3(string x)
0x440f  newobj   instance void class [mscorlib]System.Func`2<string, bool>::.ctor(object, native int)
0x4414  call     T0x2B00004B
0x4419  stloc.s  0xC
0x441b  ldloc.s  0xC
0x441d  ldsfld   class [mscorlib]System.Func`2<string, class <>f__AnonymousType0`2<string, string>> <>c::<>9__58_4
0x4422  dup
0x4423  brtrue.s loc_443C
0x4425  pop
0x4426  ldsfld   class <>c <>c::<>9
0x442b  ldftn    instance class <>f__AnonymousType0`2<string, string> <>c::<CleanupLogsAsync>b__58_4(string file)
0x4431  newobj   instance void class [mscorlib]System.Func`2<string, class <>f__AnonymousType0`2<string, string>>::.ctor(object, native int)
0x4436  dup
0x4437  stsfld   class [mscorlib]System.Func`2<string, class <>f__AnonymousType0`2<string, string>> <>c::<>9__58_4
0x443c  call     T0x2B00004D
0x4441  ldsfld   class [mscorlib]System.Func`2<class <>f__AnonymousType0`2<string, string>, bool> <>c::<>9__58_5
0x4446  dup
0x4447  brtrue.s loc_4460
0x4449  pop
0x444a  ldsfld   class <>c <>c::<>9
0x444f  ldftn    instance bool <>c::<CleanupLogsAsync>b__58_5(class <>f__AnonymousType0`2<string, string> <>h__TransparentIdentifier0)
0x4455  newobj   instance void class [mscorlib]System.Func`2<class <>f__AnonymousType0`2<string, string>, bool>::.ctor(object, native int)
0x445a  dup
0x445b  stsfld   class [mscorlib]System.Func`2<class <>f__AnonymousType0`2<string, string>, bool> <>c::<>9__58_5
0x4460  call     T0x2B00004E
0x4465  ldsfld   class [mscorlib]System.Func`2<class <>f__AnonymousType0`2<string, string>, string> <>c::<>9__58_6
0x446a  dup
0x446b  brtrue.s loc_4484
0x446d  pop
0x446e  ldsfld   class <>c <>c::<>9
0x4473  ldftn    instance string <>c::<CleanupLogsAsync>b__58_6(class <>f__AnonymousType0`2<string, string> <>h__TransparentIdentifier0)
0x4479  newobj   instance void class [mscorlib]System.Func`2<class <>f__AnonymousType0`2<string, string>, string>::.ctor(object, native int)
0x447e  dup
0x447f  stsfld   class [mscorlib]System.Func`2<class <>f__AnonymousType0`2<string, string>, string> <>c::<>9__58_6
0x4484  call     T0x2B00004F
0x4489  call     T0x2B000050
0x448e  stloc.s  0xD
0x4490  ldloc.s  0xC
0x4492  ldsfld   class [mscorlib]System.Func`2<string, bool> <>c::<>9__58_7
0x4497  dup
0x4498  brtrue.s loc_44B1
0x449a  pop
0x449b  ldsfld   class <>c <>c::<>9
0x44a0  ldftn    instance bool <>c::<CleanupLogsAsync>b__58_7(string x)
0x44a6  newobj   instance void class [mscorlib]System.Func`2<string, bool>::.ctor(object, native int)
0x44ab  dup
0x44ac  stsfld   class [mscorlib]System.Func`2<string, bool> <>c::<>9__58_7
0x44b1  call     T0x2B00004B
0x44b6  stloc.s  0xE
0x44b8  ldloc.s  0xD
0x44ba  brfalse.s loc_44D6
0x44bc  ldloc.s  0xD
0x44be  ldstr    aResult0Log// "_result_{0}.log"
0x44c3  ldc.i4.2
0x44c4  box      Microsoft.VisualStudio.Setup.OperationResult
0x44c9  call     string [mscorlib]System.String::Format(string, object)
0x44ce  ldc.i4.5
0x44cf  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x44d4  brfalse.s loc_44E4
0x44d6  ldloc.s  5
0x44d8  ldloc.s  0xC
0x44da  callvirt instance void LogFileQueue::Enqueue(class [mscorlib]System.Collections.Generic.IEnumerable`1<string> obj)
0x44df  br       loc_4592
0x44e4  ldloc.s  0xD
0x44e6  ldstr    aResult0Log// "_result_{0}.log"
0x44eb  ldc.i4.3
0x44ec  box      Microsoft.VisualStudio.Setup.OperationResult
0x44f1  call     string [mscorlib]System.String::Format(string, object)
0x44f6  ldc.i4.5
0x44f7  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x44fc  brfalse.s loc_450C
0x44fe  ldloc.s  6
0x4500  ldloc.s  0xC
0x4502  callvirt instance void LogFileQueue::Enqueue(class [mscorlib]System.Collections.Generic.IEnumerable`1<string> obj)
0x4507  br       loc_4592
0x450c  ldloc.s  0xD
0x450e  ldstr    aResult0Log// "_result_{0}.log"
0x4513  ldc.i4.1
0x4514  box      Microsoft.VisualStudio.Setup.OperationResult
0x4519  call     string [mscorlib]System.String::Format(string, object)
0x451e  ldc.i4.5
0x451f  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x4524  brtrue.s loc_4540
0x4526  ldloc.s  0xE
0x4528  ldloc.1
0x4529  ldftn    instance bool Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::<CleanupLogsAsync>b__58_8(string x)
0x452f  newobj   instance void class [mscorlib]System.Func`2<string, bool>::.ctor(object, native int)
0x4534  call     T0x2B00004B
0x4539  call     T0x2B000051
0x453e  brfalse.s loc_454B
0x4540  ldloc.s  4
0x4542  ldloc.s  0xC
0x4544  callvirt instance void LogFileQueue::Enqueue(class [mscorlib]System.Collections.Generic.IEnumerable`1<string> obj)
0x4549  br.s     loc_4592
0x454b  ldloc.s  0xD
0x454d  ldstr    aResult0Log// "_result_{0}.log"
0x4552  ldc.i4.0
0x4553  box      Microsoft.VisualStudio.Setup.OperationResult
0x4558  call     string [mscorlib]System.String::Format(string, object)
0x455d  ldc.i4.5
0x455e  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x4563  brfalse.s loc_456F
0x4565  ldloc.3
0x4566  ldloc.s  0xC
0x4568  callvirt instance void LogFileQueue::Enqueue(class [mscorlib]System.Collections.Generic.IEnumerable`1<string> obj)
0x456d  br.s     loc_4592
0x456f  ldloc.s  0xD
0x4571  ldstr    aResult0Log// "_result_{0}.log"
0x4576  ldc.i4.5
0x4577  box      Microsoft.VisualStudio.Setup.OperationResult
0x457c  call     string [mscorlib]System.String::Format(string, object)
0x4581  ldc.i4.5
0x4582  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x4587  brfalse.s loc_4592
0x4589  ldloc.s  7
0x458b  ldloc.s  0xC
0x458d  callvirt instance void LogFileQueue::Enqueue(class [mscorlib]System.Collections.Generic.IEnumerable`1<string> obj)
0x4592  ldloc.s  9
0x4594  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x4599  brtrue   loc_43E8
0x459e  leave.s  loc_45B0
0x45a0  ldloc.0
0x45a1  ldc.i4.0
0x45a2  bge.s    loc_45AF
0x45a4  ldloc.s  9
0x45a6  brfalse.s loc_45AF
0x45a8  ldloc.s  9
0x45aa  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x45af  endfinally
0x45b0  ldloc.s  5
0x45b2  callvirt instance void LogFileQueue::ExpireQueue()
0x45b7  ldloc.s  6
0x45b9  callvirt instance void LogFileQueue::ExpireQueue()
0x45be  ldloc.s  4
0x45c0  callvirt instance void LogFileQueue::ExpireQueue()
0x45c5  ldloc.3
0x45c6  callvirt instance void LogFileQueue::ExpireQueue()
0x45cb  ldloc.s  7
0x45cd  callvirt instance void LogFileQueue::ExpireQueue()
0x45d2  leave.s  loc_45ED
0x45d4  stloc.s  0xF
0x45d6  ldarg.0
0x45d7  ldc.i4.s 0xFE
0x45d9  stfld    int32 <CleanupLogsAsync>d__58::<>1__state
0x45de  ldarg.0
0x45df  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <CleanupLogsAsync>d__58::<>t__builder
0x45e4  ldloc.s  0xF
0x45e6  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetException(class [mscorlib]System.Exception)
0x45eb  leave.s  loc_4600
0x45ed  ldarg.0
0x45ee  ldc.i4.s 0xFE
0x45f0  stfld    int32 <CleanupLogsAsync>d__58::<>1__state
0x45f5  ldarg.0
0x45f6  ldflda   valuetype [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder <CleanupLogsAsync>d__58::<>t__builder
0x45fb  call     instance void [mscorlib]System.Runtime.CompilerServices.AsyncTaskMethodBuilder::SetResult()
0x4600  ret
```
