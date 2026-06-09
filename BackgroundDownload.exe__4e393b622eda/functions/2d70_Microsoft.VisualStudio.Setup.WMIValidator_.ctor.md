# Microsoft.VisualStudio.Setup.WMIValidator::.ctor

- ea: `0x2d70`
- end: `0x2d7e`
- name: `Microsoft.VisualStudio.Setup.WMIValidator::.ctor`
- size: `14`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x2170`
- `0x2480`

## pseudocode

```c

```

## disassembly

```asm
0x2d70  ldarg.0
0x2d71  call     instance void [mscorlib]System.Object::.ctor()
0x2d76  ldarg.0
0x2d77  ldarg.1
0x2d78  stfld    class [Microsoft.VisualStudio.Setup.Common]Microsoft.VisualStudio.Setup.Services.ILogger Microsoft.VisualStudio.Setup.WMIValidator::logger
0x2d7d  ret
```
