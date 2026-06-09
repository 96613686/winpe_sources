# System.Security.RightsManagement.SecureEnvironment::CriticalCreate_0

- ea: `0x4d360`
- end: `0x4d3ed`
- name: `System.Security.RightsManagement.SecureEnvironment::CriticalCreate_0`
- size: `141`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4d080`

## callees

- `0x127c0`
- `0x12870`
- `0x12990`
- `0x129b0`
- `0x129d0`
- `0x12a30`
- `0x12a80`
- `0x12ad0`
- `0x4d360`
- `0x4d3f0`

## string_xrefs

- `0x4d363`: `applicationManifest`

## pseudocode

```c

```

## disassembly

```asm
0x4d360  ldarg.0
0x4d361  brtrue.s loc_4D36E
0x4d363  ldstr    aApplicationman// "applicationManifest"
0x4d368  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4d36d  throw
0x4d36e  ldarg.1
0x4d36f  brfalse.s loc_4D380
0x4d371  ldarg.1
0x4d372  ldc.i4.1
0x4d373  beq.s    loc_4D380
0x4d375  ldstr    aAuthentication// "authentication"
0x4d37a  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x4d37f  throw
0x4d380  ldarg.2
0x4d381  brfalse.s loc_4D392
0x4d383  ldarg.2
0x4d384  ldc.i4.1
0x4d385  beq.s    loc_4D392
0x4d387  ldstr    aUseractivation// "userActivationMode"
0x4d38c  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x4d391  throw
0x4d392  ldarg.1
0x4d393  call     class MS.Internal.Security.RightsManagement.ClientSession MS.Internal.Security.RightsManagement.ClientSession::DefaultUserClientSession(valuetype System.Security.RightsManagement.AuthenticationType authentication)
0x4d398  stloc.2
0x4d399  ldloc.2
0x4d39a  callvirt instance bool MS.Internal.Security.RightsManagement.ClientSession::IsMachineActivated()
0x4d39f  brtrue.s loc_4D3A8
0x4d3a1  ldloc.2
0x4d3a2  ldarg.1
0x4d3a3  callvirt instance void MS.Internal.Security.RightsManagement.ClientSession::ActivateMachine(valuetype System.Security.RightsManagement.AuthenticationType authentication)
0x4d3a8  ldloc.2
0x4d3a9  ldarg.1
0x4d3aa  ldarg.2
0x4d3ab  callvirt instance class System.Security.RightsManagement.ContentUser MS.Internal.Security.RightsManagement.ClientSession::ActivateUser(valuetype System.Security.RightsManagement.AuthenticationType authentication, valuetype System.Security.RightsManagement.UserActivationMode userActivationMode)
0x4d3b0  stloc.0
0x4d3b1  leave.s  loc_4D3BD
0x4d3b3  ldloc.2
0x4d3b4  brfalse.s loc_4D3BC
0x4d3b6  ldloc.2
0x4d3b7  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x4d3bc  endfinally
0x4d3bd  ldloc.0
0x4d3be  ldarg.2
0x4d3bf  newobj   instance void MS.Internal.Security.RightsManagement.ClientSession::.ctor(class System.Security.RightsManagement.ContentUser user, valuetype System.Security.RightsManagement.UserActivationMode userActivationMode)
0x4d3c4  stloc.1
0x4d3c5  ldloc.1
0x4d3c6  callvirt instance void MS.Internal.Security.RightsManagement.ClientSession::AcquireClientLicensorCertificate()
0x4d3cb  leave.s  loc_4D3D0
0x4d3cd  pop
0x4d3ce  leave.s  loc_4D3D0
0x4d3d0  ldloc.1
0x4d3d1  ldarg.0
0x4d3d2  callvirt instance void MS.Internal.Security.RightsManagement.ClientSession::BuildSecureEnvironment(string applicationManifest)
0x4d3d7  ldarg.0
0x4d3d8  ldloc.0
0x4d3d9  ldloc.1
0x4d3da  newobj   instance void System.Security.RightsManagement.SecureEnvironment::.ctor(string applicationManifest, class System.Security.RightsManagement.ContentUser user, class MS.Internal.Security.RightsManagement.ClientSession clientSession)
0x4d3df  stloc.3
0x4d3e0  leave.s  loc_4D3EB
0x4d3e2  pop
0x4d3e3  ldloc.1
0x4d3e4  callvirt instance void MS.Internal.Security.RightsManagement.ClientSession::Dispose()
0x4d3e9  rethrow
0x4d3eb  ldloc.3
0x4d3ec  ret
```
