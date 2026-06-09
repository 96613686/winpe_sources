# Microsoft.VisualStudio.Setup.Services.PipeFactory::CreateServer

- ea: `0x1ae0`
- end: `0x1afc`
- name: `Microsoft.VisualStudio.Setup.Services.PipeFactory::CreateServer`
- size: `28`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callees

- `0x1000`
- `0x1b00`

## pseudocode

```c

```

## disassembly

```asm
0x1ae0  ldarg.1
0x1ae1  ldc.i4.3
0x1ae2  ldc.i4.1
0x1ae3  ldc.i4.0
0x1ae4  ldc.i4   0x40000000
0x1ae9  ldc.i4.0
0x1aea  ldc.i4.0
0x1aeb  ldarg.0
0x1aec  call     instance class [System.Core]System.IO.Pipes.PipeSecurity Microsoft.VisualStudio.Setup.Services.PipeFactory::CreateServerPipeSecurity()
0x1af1  newobj   instance void [System.Core]System.IO.Pipes.NamedPipeServerStream::.ctor(string, valuetype [System.Core]System.IO.Pipes.PipeDirection, int32, valuetype [System.Core]System.IO.Pipes.PipeTransmissionMode, valuetype [System.Core]System.IO.Pipes.PipeOptions, int32, int32, class [System.Core]System.IO.Pipes.PipeSecurity)
0x1af6  newobj   instance void Microsoft.VisualStudio.Setup.ServerPipeFacade::.ctor(class [System.Core]System.IO.Pipes.NamedPipeServerStream pipe)
0x1afb  ret
```
