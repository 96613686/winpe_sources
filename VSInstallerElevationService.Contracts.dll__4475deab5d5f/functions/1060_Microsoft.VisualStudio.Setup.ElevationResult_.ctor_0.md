# Microsoft.VisualStudio.Setup.ElevationResult::.ctor_0

- ea: `0x1060`
- end: `0x107f`
- name: `Microsoft.VisualStudio.Setup.ElevationResult::.ctor_0`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1050`

## pseudocode

```c

```

## disassembly

```asm
0x1060  ldarg.0
0x1061  call     instance void [mscorlib]System.Object::.ctor()
0x1066  ldarg.0
0x1067  ldarg.1
0x1068  ldfld    bool Microsoft.VisualStudio.Setup.ElevationResult::<IsSuccess>k__BackingField
0x106d  stfld    bool Microsoft.VisualStudio.Setup.ElevationResult::<IsSuccess>k__BackingField
0x1072  ldarg.0
0x1073  ldarg.1
0x1074  ldfld    string Microsoft.VisualStudio.Setup.ElevationResult::<PipeName>k__BackingField
0x1079  stfld    string Microsoft.VisualStudio.Setup.ElevationResult::<PipeName>k__BackingField
0x107e  ret
```
