# System.Deployment.Application.SubscriptionStore::CheckCustomUXFlag

- ea: `0x1faf0`
- end: `0x1fb49`
- name: `System.Deployment.Application.SubscriptionStore::CheckCustomUXFlag`
- size: `89`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: ``

## callers

- `0xba90`
- `0x11d60`

## callees

- `0x146b0`
- `0x1ed00`
- `0x1ee80`
- `0x1faf0`
- `0x23020`
- `0x23de0`
- `0x24f90`

## string_xrefs

- `0x1fb10`: `Ex_CustomUXAlready`
- `0x1fb38`: `Ex_NotCustomUXAlready`

## pseudocode

```c

```

## disassembly

```asm
0x1faf0  ldarg.1
0x1faf1  callvirt instance bool System.Deployment.Application.SubscriptionState::get_IsInstalled()
0x1faf6  brfalse.s loc_1FB48
0x1faf8  ldarg.2
0x1faf9  callvirt instance class System.Deployment.Application.Manifest.EntryPoint[] System.Deployment.Application.Manifest.AssemblyManifest::get_EntryPoints()
0x1fafe  ldc.i4.0
0x1faff  ldelem.ref
0x1fb00  callvirt instance bool System.Deployment.Application.Manifest.EntryPoint::get_CustomUX()
0x1fb05  brfalse.s loc_1FB20
0x1fb07  ldarg.1
0x1fb08  callvirt instance valuetype System.Deployment.Application.AppType System.Deployment.Application.SubscriptionState::get_appType()
0x1fb0d  ldc.i4.4
0x1fb0e  beq.s    loc_1FB20
0x1fb10  ldstr    aExCustomuxalre// "Ex_CustomUXAlready"
0x1fb15  call     string System.Deployment.Application.Resources::GetString(string s)
0x1fb1a  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(string message)
0x1fb1f  throw
0x1fb20  ldarg.2
0x1fb21  callvirt instance class System.Deployment.Application.Manifest.EntryPoint[] System.Deployment.Application.Manifest.AssemblyManifest::get_EntryPoints()
0x1fb26  ldc.i4.0
0x1fb27  ldelem.ref
0x1fb28  callvirt instance bool System.Deployment.Application.Manifest.EntryPoint::get_CustomUX()
0x1fb2d  brtrue.s loc_1FB48
0x1fb2f  ldarg.1
0x1fb30  callvirt instance valuetype System.Deployment.Application.AppType System.Deployment.Application.SubscriptionState::get_appType()
0x1fb35  ldc.i4.4
0x1fb36  bne.un.s loc_1FB48
0x1fb38  ldstr    aExNotcustomuxa// "Ex_NotCustomUXAlready"
0x1fb3d  call     string System.Deployment.Application.Resources::GetString(string s)
0x1fb42  newobj   instance void System.Deployment.Application.DeploymentException::.ctor(string message)
0x1fb47  throw
0x1fb48  ret
```
