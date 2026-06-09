# Microsoft.VisualStudio.Setup.ElevationRequest::.ctor_0

- ea: `0xe20`
- end: `0xe7b`
- name: `Microsoft.VisualStudio.Setup.ElevationRequest::.ctor_0`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: `installer_update, broker_com_uri`

## callers

- `0xe10`

## pseudocode

```c

```

## disassembly

```asm
0xe20  ldarg.0
0xe21  call     instance void [mscorlib]System.Object::.ctor()
0xe26  ldarg.0
0xe27  ldarg.1
0xe28  ldfld    string Microsoft.VisualStudio.Setup.ElevationRequest::<ActivityId>k__BackingField
0xe2d  stfld    string Microsoft.VisualStudio.Setup.ElevationRequest::<ActivityId>k__BackingField
0xe32  ldarg.0
0xe33  ldarg.1
0xe34  ldfld    string Microsoft.VisualStudio.Setup.ElevationRequest::<SerializedSession>k__BackingField
0xe39  stfld    string Microsoft.VisualStudio.Setup.ElevationRequest::<SerializedSession>k__BackingField
0xe3e  ldarg.0
0xe3f  ldarg.1
0xe40  ldfld    string Microsoft.VisualStudio.Setup.ElevationRequest::<Locale>k__BackingField
0xe45  stfld    string Microsoft.VisualStudio.Setup.ElevationRequest::<Locale>k__BackingField
0xe4a  ldarg.0
0xe4b  ldarg.1
0xe4c  ldfld    string Microsoft.VisualStudio.Setup.ElevationRequest::<CampaignId>k__BackingField
0xe51  stfld    string Microsoft.VisualStudio.Setup.ElevationRequest::<CampaignId>k__BackingField
0xe56  ldarg.0
0xe57  ldarg.1
0xe58  ldfld    int64 Microsoft.VisualStudio.Setup.ElevationRequest::<Handle>k__BackingField
0xe5d  stfld    int64 Microsoft.VisualStudio.Setup.ElevationRequest::<Handle>k__BackingField
0xe62  ldarg.0
0xe63  ldarg.1
0xe64  ldfld    bool Microsoft.VisualStudio.Setup.ElevationRequest::<IsQuiet>k__BackingField
0xe69  stfld    bool Microsoft.VisualStudio.Setup.ElevationRequest::<IsQuiet>k__BackingField
0xe6e  ldarg.0
0xe6f  ldarg.1
0xe70  ldfld    bool Microsoft.VisualStudio.Setup.ElevationRequest::<IsPassive>k__BackingField
0xe75  stfld    bool Microsoft.VisualStudio.Setup.ElevationRequest::<IsPassive>k__BackingField
0xe7a  ret
```
