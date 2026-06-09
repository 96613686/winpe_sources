# Microsoft.VisualStudio.Setup.Installer.InstallerBase::ExecutePackageWithRetry

- ea: `0x2c1a0`
- end: `0x2c3e7`
- name: `Microsoft.VisualStudio.Setup.Installer.InstallerBase::ExecutePackageWithRetry`
- size: `583`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x6c960`

## callees

- `0x1acb0`
- `0x2b940`
- `0x2ba30`
- `0x2ba70`
- `0x2c1a0`
- `0x2c500`
- `0x2d7f0`
- `0x2d830`
- `0x6c800`
- `0x6c8a0`

## string_xrefs

- `0x2c2aa`: `Package '{0}' failed with return code {1}. Attempting to resolve and retry #{2}/{3} times.`
- `0x2c315`: `Package '{0}' failed with return code {1}. Attempting retry #{2}/{3} after {4} seconds.`

## pseudocode

```c

```

## disassembly

```asm
0x2c1a0  ldarg.0
0x2c1a1  call     instance valuetype [mscorlib]System.Threading.CancellationToken Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_Token()
0x2c1a6  stloc.0
0x2c1a7  ldloca.s 0
0x2c1a9  call     instance bool [mscorlib]System.Threading.CancellationToken::get_IsCancellationRequested()
0x2c1ae  brtrue   loc_2C3DE
0x2c1b3  ldnull
0x2c1b4  stloc.1
0x2c1b5  ldnull
0x2c1b6  ldarg.0
0x2c1b7  dup
0x2c1b8  ldvirtftn instance void Microsoft.VisualStudio.Setup.Installer.InstallerBase::OnProgressReceived(class Microsoft.VisualStudio.Setup.ProgressDataEventArgs e)
0x2c1be  newobj   instance void class [mscorlib]System.Action`1<class Microsoft.VisualStudio.Setup.ProgressDataEventArgs>::.ctor(object, native int)
0x2c1c3  ldarg.s  4
0x2c1c5  ldarg.1
0x2c1c6  brtrue.s loc_2C1CB
0x2c1c8  ldnull
0x2c1c9  br.s     loc_2C1D1
0x2c1cb  ldarg.1
0x2c1cc  call     instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_Id()
0x2c1d1  ldc.i4.0
0x2c1d2  newobj   instance void DefaultProgressReport::.ctor(class InstallData pkgData, class [mscorlib]System.Action`1<class Microsoft.VisualStudio.Setup.ProgressDataEventArgs> onProgress, valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.ExecuteAction action, [opt] string packageDisplayInfo, [opt] bool completeProgressInDispose)
0x2c1d7  stloc.2
0x2c1d8  ldarg.2
0x2c1d9  callvirt instance var<u1> class [mscorlib]System.Func`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult>::Invoke()
0x2c1de  stloc.1
0x2c1df  ldarg.3
0x2c1e0  ldloc.1
0x2c1e1  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult, valuetype Microsoft.VisualStudio.Setup.Installer.InstallRetry>::ContainsKey(var<u1>)
0x2c1e6  brfalse  loc_2C3D0
0x2c1eb  ldarg.3
0x2c1ec  callvirt instance class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult, valuetype Microsoft.VisualStudio.Setup.Installer.InstallRetry>::get_Comparer()
0x2c1f1  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult, int32>::.ctor(class [mscorlib]System.Collections.Generic.IEqualityComparer`1<var<u1>>)
0x2c1f6  stloc.3
0x2c1f7  ldarg.3
0x2c1f8  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult, valuetype Microsoft.VisualStudio.Setup.Installer.InstallRetry>::get_Keys()
0x2c1fd  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult, valuetype Microsoft.VisualStudio.Setup.Installer.InstallRetry>::GetEnumerator()
0x2c202  stloc.s  4
0x2c204  br.s     loc_2C218
0x2c206  ldloca.s 4
0x2c208  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult, valuetype Microsoft.VisualStudio.Setup.Installer.InstallRetry>::get_Current()
0x2c20d  stloc.s  5
0x2c20f  ldloc.3
0x2c210  ldloc.s  5
0x2c212  ldc.i4.0
0x2c213  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult, int32>::Add(var<u1>, !!T0)
0x2c218  ldloca.s 4
0x2c21a  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult, valuetype Microsoft.VisualStudio.Setup.Installer.InstallRetry>::MoveNext()
0x2c21f  brtrue.s loc_2C206
0x2c221  leave    loc_2C397
0x2c226  ldloca.s 4
0x2c228  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection/Enumerator<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult, valuetype Microsoft.VisualStudio.Setup.Installer.InstallRetry>
0x2c22e  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2c233  endfinally
0x2c234  ldarg.3
0x2c235  ldloc.1
0x2c236  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult, valuetype Microsoft.VisualStudio.Setup.Installer.InstallRetry>::get_Item(void)
0x2c23b  stloc.s  6
0x2c23d  ldloc.3
0x2c23e  ldloc.1
0x2c23f  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult, int32>::get_Item(void)
0x2c244  stloc.s  7
0x2c246  ldarg.1
0x2c247  brfalse.s loc_2C292
0x2c249  ldarg.1
0x2c24a  call     instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_Id()
0x2c24f  brfalse.s loc_2C292
0x2c251  ldarg.1
0x2c252  brtrue.s loc_2C257
0x2c254  ldnull
0x2c255  br.s     loc_2C25D
0x2c257  ldarg.1
0x2c258  call     instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::get_Id()
0x2c25d  call     string Microsoft.VisualStudio.Setup.Resources::get_RetryCounts()
0x2c262  ldloc.s  7
0x2c264  box      [mscorlib]System.Int32
0x2c269  ldloca.s 6
0x2c26b  call     instance int32 Microsoft.VisualStudio.Setup.Installer.InstallRetry::get_RetryCount()
0x2c270  box      [mscorlib]System.Int32
0x2c275  call     string [mscorlib]System.String::Format(string, object, object)
0x2c27a  call     string [mscorlib]System.String::Concat(string, string)
0x2c27f  stloc.s  9
0x2c281  ldloc.2
0x2c282  ldloc.s  9
0x2c284  ldc.r8   0.0
0x2c28d  callvirt instance void DefaultProgressReport::SendProgress(string displayInfo, float64 progress)
0x2c292  ldc.i4.0
0x2c293  stloc.s  8
0x2c295  ldloca.s 6
0x2c297  call     instance bool Microsoft.VisualStudio.Setup.Installer.InstallRetry::get_ShouldResolve()
0x2c29c  brfalse.s loc_2C2FE
0x2c29e  ldarg.0
0x2c29f  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_LoggingService()
0x2c2a4  dup
0x2c2a5  brtrue.s loc_2C2AA
0x2c2a7  pop
0x2c2a8  br.s     loc_2C2F0
0x2c2aa  ldstr    aPackage0Failed// "Package '{0}' failed with return code {"...
0x2c2af  ldc.i4.4
0x2c2b0  newarr   [mscorlib]System.Object
0x2c2b5  dup
0x2c2b6  ldc.i4.0
0x2c2b7  ldarg.1
0x2c2b8  brtrue.s loc_2C2BD
0x2c2ba  ldnull
0x2c2bb  br.s     loc_2C2C3
0x2c2bd  ldarg.1
0x2c2be  call     instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::GetUniqueId()
0x2c2c3  stelem.ref
0x2c2c4  dup
0x2c2c5  ldc.i4.1
0x2c2c6  ldloc.1
0x2c2c7  callvirt instance int32 [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::get_ReturnCode()
0x2c2cc  box      [mscorlib]System.Int32
0x2c2d1  stelem.ref
0x2c2d2  dup
0x2c2d3  ldc.i4.2
0x2c2d4  ldloc.s  7
0x2c2d6  box      [mscorlib]System.Int32
0x2c2db  stelem.ref
0x2c2dc  dup
0x2c2dd  ldc.i4.3
0x2c2de  ldloca.s 6
0x2c2e0  call     instance int32 Microsoft.VisualStudio.Setup.Installer.InstallRetry::get_RetryCount()
0x2c2e5  box      [mscorlib]System.Int32
0x2c2ea  stelem.ref
0x2c2eb  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x2c2f0  ldarg.0
0x2c2f1  ldloc.1
0x2c2f2  callvirt instance bool Microsoft.VisualStudio.Setup.Installer.InstallerBase::OnErrorRetry(class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult result)
0x2c2f7  brtrue.s loc_2C36B
0x2c2f9  leave    loc_2C3DC
0x2c2fe  ldloc.s  7
0x2c300  ldarg.0
0x2c301  call     instance int32 Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_SleepMilliseconds()
0x2c306  mul
0x2c307  stloc.s  8
0x2c309  ldarg.0
0x2c30a  call     instance class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_LoggingService()
0x2c30f  dup
0x2c310  brtrue.s loc_2C315
0x2c312  pop
0x2c313  br.s     loc_2C36B
0x2c315  ldstr    aPackage0Failed_0// "Package '{0}' failed with return code {"...
0x2c31a  ldc.i4.5
0x2c31b  newarr   [mscorlib]System.Object
0x2c320  dup
0x2c321  ldc.i4.0
0x2c322  ldarg.1
0x2c323  brtrue.s loc_2C328
0x2c325  ldnull
0x2c326  br.s     loc_2C32E
0x2c328  ldarg.1
0x2c329  call     instance string [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Package::GetUniqueId()
0x2c32e  stelem.ref
0x2c32f  dup
0x2c330  ldc.i4.1
0x2c331  ldloc.1
0x2c332  callvirt instance int32 [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::get_ReturnCode()
0x2c337  box      [mscorlib]System.Int32
0x2c33c  stelem.ref
0x2c33d  dup
0x2c33e  ldc.i4.2
0x2c33f  ldloc.s  7
0x2c341  box      [mscorlib]System.Int32
0x2c346  stelem.ref
0x2c347  dup
0x2c348  ldc.i4.3
0x2c349  ldloca.s 6
0x2c34b  call     instance int32 Microsoft.VisualStudio.Setup.Installer.InstallRetry::get_RetryCount()
0x2c350  box      [mscorlib]System.Int32
0x2c355  stelem.ref
0x2c356  dup
0x2c357  ldc.i4.4
0x2c358  ldloc.s  8
0x2c35a  ldc.i4   0x3E8
0x2c35f  div
0x2c360  box      [mscorlib]System.Int32
0x2c365  stelem.ref
0x2c366  callvirt instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger::WriteVerbose(string, object[])
0x2c36b  ldarg.0
0x2c36c  call     instance valuetype [mscorlib]System.Threading.CancellationToken Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_Token()
0x2c371  stloc.0
0x2c372  ldloca.s 0
0x2c374  call     instance class [mscorlib]System.Threading.WaitHandle [mscorlib]System.Threading.CancellationToken::get_WaitHandle()
0x2c379  ldloc.s  8
0x2c37b  callvirt instance bool [mscorlib]System.Threading.WaitHandle::WaitOne(int32)
0x2c380  brtrue.s loc_2C389
0x2c382  ldarg.2
0x2c383  callvirt instance var<u1> class [mscorlib]System.Func`1<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult>::Invoke()
0x2c388  stloc.1
0x2c389  ldarg.0
0x2c38a  call     instance valuetype [mscorlib]System.Threading.CancellationToken Microsoft.VisualStudio.Setup.Installer.InstallerBase::get_Token()
0x2c38f  stloc.0
0x2c390  ldloca.s 0
0x2c392  call     instance void [mscorlib]System.Threading.CancellationToken::ThrowIfCancellationRequested()
0x2c397  ldloc.3
0x2c398  ldloc.1
0x2c399  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult, int32>::ContainsKey(var<u1>)
0x2c39e  brfalse.s loc_2C3D0
0x2c3a0  ldloc.3
0x2c3a1  ldloc.1
0x2c3a2  stloc.s  0xA
0x2c3a4  dup
0x2c3a5  ldloc.s  0xA
0x2c3a7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult, int32>::get_Item(void)
0x2c3ac  stloc.s  0xB
0x2c3ae  ldloc.s  0xA
0x2c3b0  ldloc.s  0xB
0x2c3b2  ldc.i4.1
0x2c3b3  add
0x2c3b4  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult, int32>::set_Item(var<u1>, !!T0)
0x2c3b9  ldloc.s  0xB
0x2c3bb  ldarg.3
0x2c3bc  ldloc.1
0x2c3bd  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.Dictionary`2<class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult, valuetype Microsoft.VisualStudio.Setup.Installer.InstallRetry>::get_Item(void)
0x2c3c2  stloc.s  0xC
0x2c3c4  ldloca.s 0xC
0x2c3c6  call     instance int32 Microsoft.VisualStudio.Setup.Installer.InstallRetry::get_RetryCount()
0x2c3cb  blt      loc_2C234
0x2c3d0  leave.s  loc_2C3DC
0x2c3d2  ldloc.2
0x2c3d3  brfalse.s loc_2C3DB
0x2c3d5  ldloc.2
0x2c3d6  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2c3db  endfinally
0x2c3dc  ldloc.1
0x2c3dd  ret
0x2c3de  ldc.i4.7
0x2c3df  ldc.i4.0
0x2c3e0  ldnull
0x2c3e1  newobj   instance void [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResult::.ctor(valuetype [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.InstallResultType, int32, string)
0x2c3e6  ret
```
