# Microsoft.BIServer.BIService.ProcessLaunchers.DefaultProcessLauncher::.ctor

- ea: `0x2af0`
- end: `0x2afe`
- name: `Microsoft.BIServer.BIService.ProcessLaunchers.DefaultProcessLauncher::.ctor`
- size: `14`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x2c90`

## pseudocode

```c

```

## disassembly

```asm
0x2af0  ldarg.0
0x2af1  call     instance void [mscorlib]System.Object::.ctor()
0x2af6  ldarg.0
0x2af7  ldarg.1
0x2af8  stfld    class Microsoft.BIServer.BIService.ProcessConfig Microsoft.BIServer.BIService.ProcessLaunchers.DefaultProcessLauncher::_processConfig
0x2afd  ret
```
