# System.Security.RightsManagement.SecureEnvironment::CriticalCreate

- ea: `0x4d2f0`
- end: `0x4d35f`
- name: `System.Security.RightsManagement.SecureEnvironment::CriticalCreate`
- size: `111`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4d070`

## callees

- `0x127b0`
- `0x12870`
- `0x12ad0`
- `0x4d090`
- `0x4d2f0`
- `0x4d3f0`
- `0x4e0d0`
- `0x4e3b0`

## string_xrefs

- `0x4d2f3`: `applicationManifest`

## pseudocode

```c

```

## disassembly

```asm
0x4d2f0  ldarg.0
0x4d2f1  brtrue.s loc_4D2FE
0x4d2f3  ldstr    aApplicationman// "applicationManifest"
0x4d2f8  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4d2fd  throw
0x4d2fe  ldarg.1
0x4d2ff  brtrue.s loc_4D30C
0x4d301  ldstr    aUser// "user"
0x4d306  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x4d30b  throw
0x4d30c  ldarg.1
0x4d30d  callvirt instance valuetype System.Security.RightsManagement.AuthenticationType System.Security.RightsManagement.ContentUser::get_AuthenticationType()
0x4d312  brfalse.s loc_4D328
0x4d314  ldarg.1
0x4d315  callvirt instance valuetype System.Security.RightsManagement.AuthenticationType System.Security.RightsManagement.ContentUser::get_AuthenticationType()
0x4d31a  ldc.i4.1
0x4d31b  beq.s    loc_4D328
0x4d31d  ldstr    aUser// "user"
0x4d322  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0x4d327  throw
0x4d328  ldarg.1
0x4d329  call     bool System.Security.RightsManagement.SecureEnvironment::IsUserActivated(class System.Security.RightsManagement.ContentUser user)
0x4d32e  brtrue.s loc_4D33B
0x4d330  ldc.i4   0x8004CF3E
0x4d335  newobj   instance void System.Security.RightsManagement.RightsManagementException::.ctor(valuetype System.Security.RightsManagement.RightsManagementFailureCode failureCode)
0x4d33a  throw
0x4d33b  ldarg.1
0x4d33c  newobj   instance void MS.Internal.Security.RightsManagement.ClientSession::.ctor(class System.Security.RightsManagement.ContentUser user)
0x4d341  stloc.0
0x4d342  ldloc.0
0x4d343  ldarg.0
0x4d344  callvirt instance void MS.Internal.Security.RightsManagement.ClientSession::BuildSecureEnvironment(string applicationManifest)
0x4d349  ldarg.0
0x4d34a  ldarg.1
0x4d34b  ldloc.0
0x4d34c  newobj   instance void System.Security.RightsManagement.SecureEnvironment::.ctor(string applicationManifest, class System.Security.RightsManagement.ContentUser user, class MS.Internal.Security.RightsManagement.ClientSession clientSession)
0x4d351  stloc.1
0x4d352  leave.s  loc_4D35D
0x4d354  pop
0x4d355  ldloc.0
0x4d356  callvirt instance void MS.Internal.Security.RightsManagement.ClientSession::Dispose()
0x4d35b  rethrow
0x4d35d  ldloc.1
0x4d35e  ret
```
