# System.Deployment.Application.DeploymentManager::SynchronizeAsyncWorker

- ea: `0x11cf0`
- end: `0x11d57`
- name: `System.Deployment.Application.DeploymentManager::SynchronizeAsyncWorker`
- size: `103`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x11cf0`
- `0x11d60`
- `0x127a0`
- `0x14ba0`
- `0x17d30`

## string_xrefs

- `0x11cfa`: `Download and install of the application started in a worker thread.`
- `0x11d12`: `Installation is successful.`

## pseudocode

```c

```

## disassembly

```asm
0x11cf0  ldnull
0x11cf1  stloc.0
0x11cf2  ldc.i4.0
0x11cf3  stloc.1
0x11cf4  ldarg.0
0x11cf5  ldfld    class LogIdentity System.Deployment.Application.DeploymentManager::_log
0x11cfa  ldstr    aDownloadAndIns// "Download and install of the application"...
0x11cff  call     void System.Deployment.Application.Logger::AddInternalState(class LogIdentity log, string message)
0x11d04  ldarg.0
0x11d05  ldc.i4.0
0x11d06  call     instance bool System.Deployment.Application.DeploymentManager::SynchronizeCore(bool blocking)
0x11d0b  stloc.1
0x11d0c  ldarg.0
0x11d0d  ldfld    class LogIdentity System.Deployment.Application.DeploymentManager::_log
0x11d12  ldstr    aInstallationIs// "Installation is successful."
0x11d17  call     void System.Deployment.Application.Logger::AddInternalState(class LogIdentity log, string message)
0x11d1c  leave.s  loc_11D56
0x11d1e  stloc.2
0x11d1f  ldloc.2
0x11d20  call     bool System.Deployment.Application.ExceptionUtility::IsHardException(class [mscorlib]System.Exception exception)
0x11d25  brfalse.s loc_11D29
0x11d27  rethrow
0x11d29  ldloc.2
0x11d2a  isinst   System.Deployment.Application.DownloadCancelledException
0x11d2f  brfalse.s loc_11D35
0x11d31  ldc.i4.1
0x11d32  stloc.1
0x11d33  br.s     loc_11D37
0x11d35  ldloc.2
0x11d36  stloc.0
0x11d37  leave.s  loc_11D56
0x11d39  ldloc.0
0x11d3a  ldloc.1
0x11d3b  ldnull
0x11d3c  ldnull
0x11d3d  newobj   instance void System.Deployment.Application.SynchronizeCompletedEventArgs::.ctor(class [mscorlib]System.Exception error, bool cancelled, object userState, string groupName)
0x11d42  stloc.3
0x11d43  ldarg.0
0x11d44  ldfld    class [System]System.ComponentModel.AsyncOperation System.Deployment.Application.DeploymentManager::asyncOperation
0x11d49  ldarg.0
0x11d4a  ldfld    class [mscorlib]System.Threading.SendOrPostCallback System.Deployment.Application.DeploymentManager::synchronizeCompleted
0x11d4f  ldloc.3
0x11d50  callvirt instance void [System]System.ComponentModel.AsyncOperation::Post(class [mscorlib]System.Threading.SendOrPostCallback, object)
0x11d55  endfinally
0x11d56  ret
```
