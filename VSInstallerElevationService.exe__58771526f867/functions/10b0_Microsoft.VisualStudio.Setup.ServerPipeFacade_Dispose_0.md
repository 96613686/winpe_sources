# Microsoft.VisualStudio.Setup.ServerPipeFacade::Dispose_0

- ea: `0x10b0`
- end: `0x10e6`
- name: `Microsoft.VisualStudio.Setup.ServerPipeFacade::Dispose_0`
- size: `54`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x10a0`

## callees

- `0x10b0`

## pseudocode

```c

```

## disassembly

```asm
0x10b0  ldarg.0
0x10b1  ldfld    bool Microsoft.VisualStudio.Setup.ServerPipeFacade::isDisposed
0x10b6  brtrue.s loc_10E5
0x10b8  ldarg.1
0x10b9  brfalse.s loc_10DE
0x10bb  ldarg.0
0x10bc  ldfld    class [System.Core]System.IO.Pipes.NamedPipeServerStream Microsoft.VisualStudio.Setup.ServerPipeFacade::pipe
0x10c1  callvirt instance bool [System.Core]System.IO.Pipes.PipeStream::get_IsConnected()
0x10c6  brfalse.s loc_10D3
0x10c8  ldarg.0
0x10c9  ldfld    class [System.Core]System.IO.Pipes.NamedPipeServerStream Microsoft.VisualStudio.Setup.ServerPipeFacade::pipe
0x10ce  callvirt instance void [System.Core]System.IO.Pipes.NamedPipeServerStream::Disconnect()
0x10d3  ldarg.0
0x10d4  ldfld    class [System.Core]System.IO.Pipes.NamedPipeServerStream Microsoft.VisualStudio.Setup.ServerPipeFacade::pipe
0x10d9  callvirt instance void [mscorlib]System.IO.Stream::Dispose()
0x10de  ldarg.0
0x10df  ldc.i4.1
0x10e0  stfld    bool Microsoft.VisualStudio.Setup.ServerPipeFacade::isDisposed
0x10e5  ret
```
