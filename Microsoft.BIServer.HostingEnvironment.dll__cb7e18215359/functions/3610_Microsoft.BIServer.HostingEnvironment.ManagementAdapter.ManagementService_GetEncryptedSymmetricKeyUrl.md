# Microsoft.BIServer.HostingEnvironment.ManagementAdapter.ManagementService::GetEncryptedSymmetricKeyUrl

- ea: `0x3610`
- end: `0x3632`
- name: `Microsoft.BIServer.HostingEnvironment.ManagementAdapter.ManagementService::GetEncryptedSymmetricKeyUrl`
- size: `34`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x68c0`

## pseudocode

```c

```

## disassembly

```asm
0x3610  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x3615  stloc.0
0x3616  ldstr    a0ApiV10Keys1// "{0}/api/v1.0/Keys/{1}"
0x361b  ldarg.0
0x361c  ldfld    class [System]System.Uri Microsoft.BIServer.HostingEnvironment.ManagementAdapter.ManagementService::_managementUrl
0x3621  ldloc.0
0x3622  box      [mscorlib]System.Guid
0x3627  call     string [mscorlib]System.String::Format(string, object, object)
0x362c  newobj   instance void [System]System.Uri::.ctor(string)
0x3631  ret
```
