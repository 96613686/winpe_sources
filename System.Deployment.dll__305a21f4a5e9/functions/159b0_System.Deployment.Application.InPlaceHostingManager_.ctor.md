# System.Deployment.Application.InPlaceHostingManager::.ctor

- ea: `0x159b0`
- end: `0x15a73`
- name: `System.Deployment.Application.InPlaceHostingManager::.ctor`
- size: `195`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x15a80`

## callees

- `0x10a60`
- `0x10c20`
- `0x159b0`
- `0x15a90`
- `0x17ce0`
- `0x17d30`
- `0x1c6b0`
- `0x218f0`
- `0x23020`

## string_xrefs

- `0x159d6`: `deploymentManifest`

## pseudocode

```c

```

## disassembly

```asm
0x159b0  ldarg.0
0x159b1  call     instance void [mscorlib]System.Object::.ctor()
0x159b6  call     bool System.Deployment.Application.PlatformSpecific::get_OnXPOrAbove()
0x159bb  brtrue.s loc_159CD
0x159bd  ldstr    aExRequiresxpor// "Ex_RequiresXPOrHigher"
0x159c2  call     string System.Deployment.Application.Resources::GetString(string s)
0x159c7  newobj   instance void [mscorlib]System.PlatformNotSupportedException::.ctor(string)
0x159cc  throw
0x159cd  ldarg.1
0x159ce  ldnull
0x159cf  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x159d4  brfalse.s loc_159E1
0x159d6  ldstr    aDeploymentmani// "deploymentManifest"
0x159db  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x159e0  throw
0x159e1  ldarg.1
0x159e2  ldstr    aDeploymentsour_0// "deploymentSource"
0x159e7  call     void System.Deployment.Application.UriHelper::ValidateSupportedSchemeInArgument(class [System]System.Uri uri, string argumentName)
0x159ec  ldarg.0
0x159ed  ldarg.1
0x159ee  ldc.i4.0
0x159ef  ldc.i4.1
0x159f0  ldnull
0x159f1  ldnull
0x159f2  newobj   instance void System.Deployment.Application.DeploymentManager::.ctor(class [System]System.Uri deploymentSource, bool isUpdate, bool isConfirmed, class System.Deployment.Application.DownloadOptions downloadOptions, class [System]System.ComponentModel.AsyncOperation optionalAsyncOp)
0x159f7  stfld    class System.Deployment.Application.DeploymentManager System.Deployment.Application.InPlaceHostingManager::_deploymentManager
0x159fc  ldarg.0
0x159fd  ldarg.0
0x159fe  ldfld    class System.Deployment.Application.DeploymentManager System.Deployment.Application.InPlaceHostingManager::_deploymentManager
0x15a03  callvirt instance class LogIdentity System.Deployment.Application.DeploymentManager::get_LogId()
0x15a08  stfld    class LogIdentity System.Deployment.Application.InPlaceHostingManager::_log
0x15a0d  ldarg.0
0x15a0e  ldarg.2
0x15a0f  stfld    bool System.Deployment.Application.InPlaceHostingManager::_isLaunchInHostProcess
0x15a14  ldarg.0
0x15a15  call     instance void System.Deployment.Application.InPlaceHostingManager::_Initialize()
0x15a1a  ldarg.0
0x15a1b  ldfld    class LogIdentity System.Deployment.Application.InPlaceHostingManager::_log
0x15a20  ldstr    aActivationThro_0// "Activation through IPHM APIs started."
0x15a25  call     void System.Deployment.Application.Logger::AddInternalState(class LogIdentity log, string message)
0x15a2a  ldarg.0
0x15a2b  ldfld    class LogIdentity System.Deployment.Application.InPlaceHostingManager::_log
0x15a30  ldc.i4.5
0x15a31  newarr   [mscorlib]System.String
0x15a36  dup
0x15a37  ldc.i4.0
0x15a38  ldstr    aInplacehosting// "InPlaceHostingManager("
0x15a3d  stelem.ref
0x15a3e  dup
0x15a3f  ldc.i4.1
0x15a40  ldarg.1
0x15a41  dup
0x15a42  brtrue.s loc_15A48
0x15a44  pop
0x15a45  ldnull
0x15a46  br.s     loc_15A4D
0x15a48  callvirt instance string [mscorlib]System.Object::ToString()
0x15a4d  stelem.ref
0x15a4e  dup
0x15a4f  ldc.i4.2
0x15a50  ldstr    asc_308B8// ","
0x15a55  stelem.ref
0x15a56  dup
0x15a57  ldc.i4.3
0x15a58  ldarga.s 2
0x15a5a  call     instance string [mscorlib]System.Boolean::ToString()
0x15a5f  stelem.ref
0x15a60  dup
0x15a61  ldc.i4.4
0x15a62  ldstr    aCalled// ") called."
0x15a67  stelem.ref
0x15a68  call     string [mscorlib]System.String::Concat(string[])
0x15a6d  call     void System.Deployment.Application.Logger::AddMethodCall(class LogIdentity log, string message)
0x15a72  ret
```
