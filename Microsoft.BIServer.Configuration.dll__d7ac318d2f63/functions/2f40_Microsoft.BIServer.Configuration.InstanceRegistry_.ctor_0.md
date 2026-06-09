# Microsoft.BIServer.Configuration.InstanceRegistry::.ctor_0

- ea: `0x2f40`
- end: `0x2f58`
- name: `Microsoft.BIServer.Configuration.InstanceRegistry::.ctor_0`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x2a30`
- `0x2f00`

## pseudocode

```c

```

## disassembly

```asm
0x2f40  ldarg.0
0x2f41  ldarg.1
0x2f42  ldarg.2
0x2f43  ldsfld   class [mscorlib]Microsoft.Win32.RegistryKey [mscorlib]Microsoft.Win32.Registry::LocalMachine
0x2f48  ldstr    aSoftwareMicros// "SOFTWARE\\Microsoft\\Microsoft SQL Serv"...
0x2f4d  newobj   instance void Microsoft.BIServer.Configuration.RegistryStore::.ctor(class [mscorlib]Microsoft.Win32.RegistryKey top, string commonPath)
0x2f52  call     instance void Microsoft.BIServer.Configuration.InstanceRegistry::.ctor(class Microsoft.BIServer.Configuration.InstanceId instanceId, class Microsoft.BIServer.Configuration.InstanceName instanceName, class Microsoft.BIServer.Configuration.IRegistryStore registryStore)
0x2f57  ret
```
