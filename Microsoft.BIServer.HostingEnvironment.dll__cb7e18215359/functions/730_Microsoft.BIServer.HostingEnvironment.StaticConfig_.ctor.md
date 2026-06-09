# Microsoft.BIServer.HostingEnvironment.StaticConfig::.ctor

- ea: `0x730`
- end: `0x742`
- name: `Microsoft.BIServer.HostingEnvironment.StaticConfig::.ctor`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `registry_config, broker_com_uri`

## callers

- `0x8a0`

## pseudocode

```c

```

## disassembly

```asm
0x730  ldarg.0
0x731  call     instance void [mscorlib]System.Object::.ctor()
0x736  ldarg.0
0x737  ldsfld   class Microsoft.BIServer.HostingEnvironment.Args Microsoft.BIServer.HostingEnvironment.Args::CommandLine
0x73c  stfld    class Microsoft.BIServer.HostingEnvironment.Args Microsoft.BIServer.HostingEnvironment.StaticConfig::_args
0x741  ret
```
