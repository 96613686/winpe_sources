# Microsoft.BIServer.Configuration.WMI.RSInstance::Clone

- ea: `0x4bf0`
- end: `0x4c0c`
- name: `Microsoft.BIServer.Configuration.WMI.RSInstance::Clone`
- size: `28`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x4b80`
- `0x4c90`

## pseudocode

```c

```

## disassembly

```asm
0x4bf0  ldarg.0
0x4bf1  ldfld    class [System.Management]System.Management.ManagementObject Microsoft.BIServer.Configuration.WMI.RSWmiInstance::_internalObject
0x4bf6  callvirt instance object [System.Management]System.Management.ManagementBaseObject::Clone()
0x4bfb  isinst   [System.Management]System.Management.ManagementObject
0x4c00  ldarg.0
0x4c01  call     instance string Microsoft.BIServer.Configuration.WMI.RSWmiInstance::get_MachineName()
0x4c06  newobj   instance void Microsoft.BIServer.Configuration.WMI.RSInstance::.ctor(class [System.Management]System.Management.ManagementObject mo, string machineName)
0x4c0b  ret
```
