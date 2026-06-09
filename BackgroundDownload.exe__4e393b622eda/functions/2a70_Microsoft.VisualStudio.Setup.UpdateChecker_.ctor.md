# Microsoft.VisualStudio.Setup.UpdateChecker::.ctor

- ea: `0x2a70`
- end: `0x2a80`
- name: `Microsoft.VisualStudio.Setup.UpdateChecker::.ctor`
- size: `16`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2320`

## callees

- `0x1940`

## pseudocode

```c

```

## disassembly

```asm
0x2a70  ldarg.0
0x2a71  ldarg.1
0x2a72  ldarg.2
0x2a73  call     instance void Microsoft.VisualStudio.Setup.BackgroundDownloadJobBase::.ctor(class [mscorlib]System.IServiceProvider services, class Microsoft.VisualStudio.Setup.CommandLine commandLine)
0x2a78  ldarg.0
0x2a79  ldarg.3
0x2a7a  stfld    class [Microsoft.VisualStudio.Setup]Microsoft.VisualStudio.Setup.Services.ISingletonService Microsoft.VisualStudio.Setup.UpdateChecker::singletonService
0x2a7f  ret
```
