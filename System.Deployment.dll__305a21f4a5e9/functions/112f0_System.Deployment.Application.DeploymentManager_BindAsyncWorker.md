# System.Deployment.Application.DeploymentManager::BindAsyncWorker

- ea: `0x112f0`
- end: `0x113a9`
- name: `System.Deployment.Application.DeploymentManager::BindAsyncWorker`
- size: `185`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x112f0`
- `0x113b0`
- `0x126e0`
- `0x13110`
- `0x14ba0`
- `0x17d30`

## string_xrefs

- `0x11304`: `Binding started in a worker thread.`

## pseudocode

```c

```

## disassembly

```asm
0x112f0  ldnull
0x112f1  stloc.0
0x112f2  ldc.i4.0
0x112f3  stloc.1
0x112f4  ldnull
0x112f5  stloc.2
0x112f6  ldnull
0x112f7  stloc.3
0x112f8  ldnull
0x112f9  stloc.s  4
0x112fb  ldnull
0x112fc  stloc.s  5
0x112fe  ldarg.0
0x112ff  ldfld    class LogIdentity System.Deployment.Application.DeploymentManager::_log
0x11304  ldstr    aBindingStarted// "Binding started in a worker thread."
0x11309  call     void System.Deployment.Application.Logger::AddInternalState(class LogIdentity log, string message)
0x1130e  ldarg.0
0x1130f  ldc.i4.0
0x11310  ldloca.s 3
0x11312  ldloca.s 4
0x11314  ldloca.s 5
0x11316  ldloca.s 2
0x11318  call     instance bool System.Deployment.Application.DeploymentManager::BindCore(bool blocking, class System.Deployment.Application.TempFile& tempDeploy, class System.Deployment.Application.TempDirectory& tempAppDir, class [mscorlib]System.IO.FileStream& refTransaction, string& productName)
0x1131d  stloc.1
0x1131e  ldarg.0
0x1131f  ldfld    class LogIdentity System.Deployment.Application.DeploymentManager::_log
0x11324  ldstr    aBindingIsSucce// "Binding is successful."
0x11329  call     void System.Deployment.Application.Logger::AddInternalState(class LogIdentity log, string message)
0x1132e  leave.s  loc_113A8
0x11330  stloc.s  6
0x11332  ldloc.s  6
0x11334  call     bool System.Deployment.Application.ExceptionUtility::IsHardException(class [mscorlib]System.Exception exception)
0x11339  brfalse.s loc_1133D
0x1133b  rethrow
0x1133d  ldloc.s  6
0x1133f  isinst   System.Deployment.Application.DownloadCancelledException
0x11344  brfalse.s loc_1134A
0x11346  ldc.i4.1
0x11347  stloc.1
0x11348  br.s     loc_1134D
0x1134a  ldloc.s  6
0x1134c  stloc.0
0x1134d  leave.s  loc_113A8
0x1134f  ldarg.0
0x11350  ldc.i4.2
0x11351  stfld    valuetype System.Deployment.Application.DeploymentProgressState System.Deployment.Application.DeploymentManager::_state
0x11356  ldloc.0
0x11357  ldnull
0x11358  cgt.un
0x1135a  ldloc.1
0x1135b  or
0x1135c  brfalse.s loc_1137D
0x1135e  ldloc.s  4
0x11360  brfalse.s loc_11369
0x11362  ldloc.s  4
0x11364  callvirt instance void System.Deployment.Application.DisposableBase::Dispose()
0x11369  ldloc.3
0x1136a  brfalse.s loc_11372
0x1136c  ldloc.3
0x1136d  callvirt instance void System.Deployment.Application.DisposableBase::Dispose()
0x11372  ldloc.s  5
0x11374  brfalse.s loc_1137D
0x11376  ldloc.s  5
0x11378  callvirt instance void [mscorlib]System.IO.Stream::Close()
0x1137d  ldloc.0
0x1137e  ldloc.1
0x1137f  ldnull
0x11380  ldarg.0
0x11381  ldfld    class [mscorlib]System.ActivationContext System.Deployment.Application.DeploymentManager::_actCtx
0x11386  ldloc.2
0x11387  ldarg.0
0x11388  ldfld    bool System.Deployment.Application.DeploymentManager::_cached
0x1138d  newobj   instance void System.Deployment.Application.BindCompletedEventArgs::.ctor(class [mscorlib]System.Exception error, bool cancelled, object userState, class [mscorlib]System.ActivationContext actCtx, string name, bool cached)
0x11392  stloc.s  7
0x11394  ldarg.0
0x11395  ldfld    class [System]System.ComponentModel.AsyncOperation System.Deployment.Application.DeploymentManager::asyncOperation
0x1139a  ldarg.0
0x1139b  ldfld    class [mscorlib]System.Threading.SendOrPostCallback System.Deployment.Application.DeploymentManager::bindCompleted
0x113a0  ldloc.s  7
0x113a2  callvirt instance void [System]System.ComponentModel.AsyncOperation::Post(class [mscorlib]System.Threading.SendOrPostCallback, object)
0x113a7  endfinally
0x113a8  ret
```
