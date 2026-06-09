# Microsoft.VisualStudio.Setup.CheckForUpdatesResult::.ctor

- ea: `0x2600`
- end: `0x2624`
- name: `Microsoft.VisualStudio.Setup.CheckForUpdatesResult::.ctor`
- size: `36`
- prototype: ``
- caller_count: `2`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x5920`
- `0x5f80`

## pseudocode

```c

```

## disassembly

```asm
0x2600  ldarg.0
0x2601  ldarg.1
0x2602  stfld    bool Microsoft.VisualStudio.Setup.CheckForUpdatesResult::<EngineUpdateRequired>k__BackingField
0x2607  ldarg.0
0x2608  ldarg.2
0x2609  stfld    string Microsoft.VisualStudio.Setup.CheckForUpdatesResult::<OpcUrl>k__BackingField
0x260e  ldarg.0
0x260f  ldarg.3
0x2610  stfld    class [mscorlib]System.Version Microsoft.VisualStudio.Setup.CheckForUpdatesResult::<OpcVersion>k__BackingField
0x2615  ldarg.0
0x2616  ldarg.s  4
0x2618  stfld    int32 Microsoft.VisualStudio.Setup.CheckForUpdatesResult::<UpdateResultCode>k__BackingField
0x261d  ldarg.0
0x261e  call     instance void [mscorlib]System.Object::.ctor()
0x2623  ret
```
