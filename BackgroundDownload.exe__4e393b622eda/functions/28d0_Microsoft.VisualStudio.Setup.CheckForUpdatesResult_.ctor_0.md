# Microsoft.VisualStudio.Setup.CheckForUpdatesResult::.ctor_0

- ea: `0x28d0`
- end: `0x2907`
- name: `Microsoft.VisualStudio.Setup.CheckForUpdatesResult::.ctor_0`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0x28c0`

## pseudocode

```c

```

## disassembly

```asm
0x28d0  ldarg.0
0x28d1  call     instance void [mscorlib]System.Object::.ctor()
0x28d6  ldarg.0
0x28d7  ldarg.1
0x28d8  ldfld    bool Microsoft.VisualStudio.Setup.CheckForUpdatesResult::<EngineUpdateRequired>k__BackingField
0x28dd  stfld    bool Microsoft.VisualStudio.Setup.CheckForUpdatesResult::<EngineUpdateRequired>k__BackingField
0x28e2  ldarg.0
0x28e3  ldarg.1
0x28e4  ldfld    string Microsoft.VisualStudio.Setup.CheckForUpdatesResult::<OpcUrl>k__BackingField
0x28e9  stfld    string Microsoft.VisualStudio.Setup.CheckForUpdatesResult::<OpcUrl>k__BackingField
0x28ee  ldarg.0
0x28ef  ldarg.1
0x28f0  ldfld    class [mscorlib]System.Version Microsoft.VisualStudio.Setup.CheckForUpdatesResult::<OpcVersion>k__BackingField
0x28f5  stfld    class [mscorlib]System.Version Microsoft.VisualStudio.Setup.CheckForUpdatesResult::<OpcVersion>k__BackingField
0x28fa  ldarg.0
0x28fb  ldarg.1
0x28fc  ldfld    int32 Microsoft.VisualStudio.Setup.CheckForUpdatesResult::<UpdateResultCode>k__BackingField
0x2901  stfld    int32 Microsoft.VisualStudio.Setup.CheckForUpdatesResult::<UpdateResultCode>k__BackingField
0x2906  ret
```
