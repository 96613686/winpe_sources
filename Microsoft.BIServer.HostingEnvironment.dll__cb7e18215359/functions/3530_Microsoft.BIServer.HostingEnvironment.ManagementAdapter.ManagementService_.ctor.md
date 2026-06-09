# Microsoft.BIServer.HostingEnvironment.ManagementAdapter.ManagementService::.ctor

- ea: `0x3530`
- end: `0x3552`
- name: `Microsoft.BIServer.HostingEnvironment.ManagementAdapter.ManagementService::.ctor`
- size: `34`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x4e30`

## callees

- `0x3530`

## pseudocode

```c

```

## disassembly

```asm
0x3530  ldarg.0
0x3531  call     instance void [mscorlib]System.Object::.ctor()
0x3536  ldarg.1
0x3537  ldnull
0x3538  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x353d  brfalse.s loc_354A
0x353f  ldstr    aManagementurl// "managementUrl"
0x3544  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x3549  throw
0x354a  ldarg.0
0x354b  ldarg.1
0x354c  stfld    class [System]System.Uri Microsoft.BIServer.HostingEnvironment.ManagementAdapter.ManagementService::_managementUrl
0x3551  ret
```
