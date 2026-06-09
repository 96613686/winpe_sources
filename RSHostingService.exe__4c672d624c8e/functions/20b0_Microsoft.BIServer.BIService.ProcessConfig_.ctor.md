# Microsoft.BIServer.BIService.ProcessConfig::.ctor

- ea: `0x20b0`
- end: `0x20c2`
- name: `Microsoft.BIServer.BIService.ProcessConfig::.ctor`
- size: `18`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x21a0`

## pseudocode

```c

```

## disassembly

```asm
0x20b0  ldarg.0
0x20b1  call     instance void [mscorlib]System.Object::.ctor()
0x20b6  ldarg.0
0x20b7  newobj   instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::.ctor()
0x20bc  call     instance void Microsoft.BIServer.BIService.ProcessConfig::set_Config(class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> value)
0x20c1  ret
```
