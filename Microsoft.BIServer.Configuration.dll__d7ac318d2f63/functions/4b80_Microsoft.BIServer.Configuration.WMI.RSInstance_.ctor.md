# Microsoft.BIServer.Configuration.WMI.RSInstance::.ctor

- ea: `0x4b80`
- end: `0x4b90`
- name: `Microsoft.BIServer.Configuration.WMI.RSInstance::.ctor`
- size: `16`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callers

- `0x4bf0`
- `0x5a60`

## callees

- `0x4c30`

## pseudocode

```c

```

## disassembly

```asm
0x4b80  ldarg.0
0x4b81  ldarg.1
0x4b82  ldarg.2
0x4b83  call     instance void Microsoft.BIServer.Configuration.WMI.RSWmiInstance::.ctor(class [System.Management]System.Management.ManagementObject mo, string machineName)
0x4b88  ldarg.0
0x4b89  ldnull
0x4b8a  stfld    class [System]System.Net.IPAddress[] Microsoft.BIServer.Configuration.WMI.RSInstance::machineIPAddresses
0x4b8f  ret
```
