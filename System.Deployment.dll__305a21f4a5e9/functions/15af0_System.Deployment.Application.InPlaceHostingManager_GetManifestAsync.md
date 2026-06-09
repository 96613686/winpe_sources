# System.Deployment.Application.InPlaceHostingManager::GetManifestAsync

- ea: `0x15af0`
- end: `0x15b8f`
- name: `System.Deployment.Application.InPlaceHostingManager::GetManifestAsync`
- size: `159`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x10c30`
- `0x15af0`
- `0x16740`
- `0x16850`
- `0x17ce0`
- `0x17d30`

## string_xrefs

- `0x15b0e`: `InPlaceHostingManager.GetManifestAsync() called.`
- `0x15b3b`: `Exception thrown in  GetManifestAsync(): `

## pseudocode

```c

```

## disassembly

```asm
0x15af0  ldarg.0
0x15af1  ldfld    object System.Deployment.Application.InPlaceHostingManager::_lock
0x15af6  stloc.0
0x15af7  ldc.i4.0
0x15af8  stloc.1
0x15af9  ldloc.0
0x15afa  ldloca.s 1
0x15afc  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x15b01  ldarg.0
0x15b02  ldc.i4.0
0x15b03  call     instance void System.Deployment.Application.InPlaceHostingManager::AssertState(valuetype State validState)
0x15b08  ldarg.0
0x15b09  ldfld    class LogIdentity System.Deployment.Application.InPlaceHostingManager::_log
0x15b0e  ldstr    aInplacehosting_0// "InPlaceHostingManager.GetManifestAsync("...
0x15b13  call     void System.Deployment.Application.Logger::AddMethodCall(class LogIdentity log, string message)
0x15b18  ldarg.0
0x15b19  ldc.i4.1
0x15b1a  call     instance void System.Deployment.Application.InPlaceHostingManager::ChangeState(valuetype State nextState)
0x15b1f  ldarg.0
0x15b20  ldfld    class System.Deployment.Application.DeploymentManager System.Deployment.Application.InPlaceHostingManager::_deploymentManager
0x15b25  callvirt instance void System.Deployment.Application.DeploymentManager::BindAsync()
0x15b2a  leave.s  loc_15B8E
0x15b2c  stloc.2
0x15b2d  ldarg.0
0x15b2e  ldfld    class LogIdentity System.Deployment.Application.InPlaceHostingManager::_log
0x15b33  ldc.i4.6
0x15b34  newarr   [mscorlib]System.String
0x15b39  dup
0x15b3a  ldc.i4.0
0x15b3b  ldstr    aExceptionThrow_5// "Exception thrown in  GetManifestAsync()"...
0x15b40  stelem.ref
0x15b41  dup
0x15b42  ldc.i4.1
0x15b43  ldloc.2
0x15b44  callvirt instance class [mscorlib]System.Type [mscorlib]System.Exception::GetType()
0x15b49  callvirt instance string [mscorlib]System.Object::ToString()
0x15b4e  stelem.ref
0x15b4f  dup
0x15b50  ldc.i4.2
0x15b51  ldstr    asc_3345E// " : "
0x15b56  stelem.ref
0x15b57  dup
0x15b58  ldc.i4.3
0x15b59  ldloc.2
0x15b5a  callvirt instance string [mscorlib]System.Exception::get_Message()
0x15b5f  stelem.ref
0x15b60  dup
0x15b61  ldc.i4.4
0x15b62  ldstr    asc_3279C// "\r\n"
0x15b67  stelem.ref
0x15b68  dup
0x15b69  ldc.i4.5
0x15b6a  ldloc.2
0x15b6b  callvirt instance string [mscorlib]System.Exception::get_StackTrace()
0x15b70  stelem.ref
0x15b71  call     string [mscorlib]System.String::Concat(string[])
0x15b76  call     void System.Deployment.Application.Logger::AddInternalState(class LogIdentity log, string message)
0x15b7b  ldarg.0
0x15b7c  ldc.i4.7
0x15b7d  call     instance void System.Deployment.Application.InPlaceHostingManager::ChangeState(valuetype State nextState)
0x15b82  rethrow
0x15b84  ldloc.1
0x15b85  brfalse.s loc_15B8D
0x15b87  ldloc.0
0x15b88  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x15b8d  endfinally
0x15b8e  ret
```
