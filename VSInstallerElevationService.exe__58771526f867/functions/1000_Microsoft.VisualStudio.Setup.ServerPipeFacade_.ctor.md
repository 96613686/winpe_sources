# Microsoft.VisualStudio.Setup.ServerPipeFacade::.ctor

- ea: `0x1000`
- end: `0x100e`
- name: `Microsoft.VisualStudio.Setup.ServerPipeFacade::.ctor`
- size: `14`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1ae0`

## pseudocode

```c

```

## disassembly

```asm
0x1000  ldarg.0
0x1001  call     instance void [mscorlib]System.Object::.ctor()
0x1006  ldarg.0
0x1007  ldarg.1
0x1008  stfld    class [System.Core]System.IO.Pipes.NamedPipeServerStream Microsoft.VisualStudio.Setup.ServerPipeFacade::pipe
0x100d  ret
```
