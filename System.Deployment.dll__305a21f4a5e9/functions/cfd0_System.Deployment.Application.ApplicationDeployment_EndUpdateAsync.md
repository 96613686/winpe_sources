# System.Deployment.Application.ApplicationDeployment::EndUpdateAsync

- ea: `0xcfd0`
- end: `0xd05e`
- name: `System.Deployment.Application.ApplicationDeployment::EndUpdateAsync`
- size: `142`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `installer_update`

## callers

- `0xced0`
- `0xd060`

## callees

- `0xcbd0`
- `0xcfd0`
- `0x11120`
- `0x11160`
- `0x111a0`
- `0x111c0`
- `0x12690`
- `0x12750`
- `0x127e0`

## pseudocode

```c

```

## disassembly

```asm
0xcfd0  ldarg.0
0xcfd1  ldflda   int32 System.Deployment.Application.ApplicationDeployment::_guard
0xcfd6  ldc.i4.0
0xcfd7  call     int32 [mscorlib]System.Threading.Interlocked::Exchange(int32&, int32)
0xcfdc  pop
0xcfdd  ldarg.2
0xcfde  ldarg.3
0xcfdf  ldnull
0xcfe0  newobj   instance void [System]System.ComponentModel.AsyncCompletedEventArgs::.ctor(class [mscorlib]System.Exception, bool, object)
0xcfe5  stloc.0
0xcfe6  ldarg.0
0xcfe7  call     instance class [System]System.ComponentModel.EventHandlerList System.Deployment.Application.ApplicationDeployment::get_Events()
0xcfec  ldsfld   object System.Deployment.Application.ApplicationDeployment::updateCompletedKey
0xcff1  callvirt instance class [mscorlib]System.Delegate [System]System.ComponentModel.EventHandlerList::get_Item(object)
0xcff6  castclass [System]System.ComponentModel.AsyncCompletedEventHandler
0xcffb  stloc.1
0xcffc  ldloc.1
0xcffd  brfalse.s loc_D007
0xcfff  ldloc.1
0xd000  ldarg.0
0xd001  ldloc.0
0xd002  callvirt instance void [System]System.ComponentModel.AsyncCompletedEventHandler::Invoke(object, class [System]System.ComponentModel.AsyncCompletedEventArgs)
0xd007  ldarg.1
0xd008  brfalse.s loc_D05D
0xd00a  ldarg.1
0xd00b  ldarg.0
0xd00c  ldftn    instance void System.Deployment.Application.ApplicationDeployment::UpdateProgressChangedEventHandler(object sender, class System.Deployment.Application.DeploymentProgressChangedEventArgs e)
0xd012  newobj   instance void System.Deployment.Application.DeploymentProgressChangedEventHandler::.ctor(object object, native int method)
0xd017  callvirt instance void System.Deployment.Application.DeploymentManager::remove_ProgressChanged(class System.Deployment.Application.DeploymentProgressChangedEventHandler value)
0xd01c  ldarg.1
0xd01d  ldarg.0
0xd01e  ldftn    instance void System.Deployment.Application.ApplicationDeployment::UpdateBindCompletedEventHandler(object sender, class System.Deployment.Application.BindCompletedEventArgs e)
0xd024  newobj   instance void System.Deployment.Application.BindCompletedEventHandler::.ctor(object object, native int method)
0xd029  callvirt instance void System.Deployment.Application.DeploymentManager::remove_BindCompleted(class System.Deployment.Application.BindCompletedEventHandler value)
0xd02e  ldarg.1
0xd02f  ldarg.0
0xd030  ldftn    instance void System.Deployment.Application.ApplicationDeployment::SynchronizeNullCompletedEventHandler(object sender, class System.Deployment.Application.SynchronizeCompletedEventArgs e)
0xd036  newobj   instance void System.Deployment.Application.SynchronizeCompletedEventHandler::.ctor(object object, native int method)
0xd03b  callvirt instance void System.Deployment.Application.DeploymentManager::remove_SynchronizeCompleted(class System.Deployment.Application.SynchronizeCompletedEventHandler value)
0xd040  ldstr    aFulltrust_0// "FullTrust"
0xd045  newobj   instance void [mscorlib]System.Security.NamedPermissionSet::.ctor(string)
0xd04a  call     instance void [mscorlib]System.Security.PermissionSet::Assert()
0xd04f  ldarg.1
0xd050  callvirt instance void System.Deployment.Application.DeploymentManager::Dispose()
0xd055  leave.s  loc_D05D
0xd057  call     void [mscorlib]System.Security.CodeAccessPermission::RevertAssert()
0xd05c  endfinally
0xd05d  ret
```
