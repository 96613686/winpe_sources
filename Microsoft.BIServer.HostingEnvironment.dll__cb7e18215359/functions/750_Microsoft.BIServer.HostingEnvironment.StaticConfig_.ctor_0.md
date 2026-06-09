# Microsoft.BIServer.HostingEnvironment.StaticConfig::.ctor_0

- ea: `0x750`
- end: `0x763`
- name: `Microsoft.BIServer.HostingEnvironment.StaticConfig::.ctor_0`
- size: `19`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1c0`

## pseudocode

```c

```

## disassembly

```asm
0x750  ldarg.0
0x751  call     instance void [mscorlib]System.Object::.ctor()
0x756  ldarg.0
0x757  ldarg.1
0x758  newobj   instance void Microsoft.BIServer.HostingEnvironment.Args::.ctor(string[] args)
0x75d  stfld    class Microsoft.BIServer.HostingEnvironment.Args Microsoft.BIServer.HostingEnvironment.StaticConfig::_args
0x762  ret
```
