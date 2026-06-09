# Microsoft.VisualStudio.Setup.CheckForUpdatesResult::Equals_0

- ea: `0x2840`
- end: `0x28bd`
- name: `Microsoft.VisualStudio.Setup.CheckForUpdatesResult::Equals_0`
- size: `125`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x27a0`
- `0x2830`

## callees

- `0x2630`
- `0x2840`

## pseudocode

```c

```

## disassembly

```asm
0x2840  ldarg.0
0x2841  ldarg.1
0x2842  beq.s    loc_28BB
0x2844  ldarg.1
0x2845  brfalse.s loc_28B9
0x2847  ldarg.0
0x2848  callvirt instance class [mscorlib]System.Type Microsoft.VisualStudio.Setup.CheckForUpdatesResult::get_EqualityContract()
0x284d  ldarg.1
0x284e  callvirt instance class [mscorlib]System.Type Microsoft.VisualStudio.Setup.CheckForUpdatesResult::get_EqualityContract()
0x2853  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x2858  brfalse.s loc_28B9
0x285a  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<bool>::get_Default()
0x285f  ldarg.0
0x2860  ldfld    bool Microsoft.VisualStudio.Setup.CheckForUpdatesResult::<EngineUpdateRequired>k__BackingField
0x2865  ldarg.1
0x2866  ldfld    bool Microsoft.VisualStudio.Setup.CheckForUpdatesResult::<EngineUpdateRequired>k__BackingField
0x286b  callvirt instance bool class [mscorlib]System.Collections.Generic.EqualityComparer`1<bool>::Equals(var<u1>, !!T0)
0x2870  brfalse.s loc_28B9
0x2872  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<string>::get_Default()
0x2877  ldarg.0
0x2878  ldfld    string Microsoft.VisualStudio.Setup.CheckForUpdatesResult::<OpcUrl>k__BackingField
0x287d  ldarg.1
0x287e  ldfld    string Microsoft.VisualStudio.Setup.CheckForUpdatesResult::<OpcUrl>k__BackingField
0x2883  callvirt instance bool class [mscorlib]System.Collections.Generic.EqualityComparer`1<string>::Equals(var<u1>, !!T0)
0x2888  brfalse.s loc_28B9
0x288a  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<class [mscorlib]System.Version>::get_Default()
0x288f  ldarg.0
0x2890  ldfld    class [mscorlib]System.Version Microsoft.VisualStudio.Setup.CheckForUpdatesResult::<OpcVersion>k__BackingField
0x2895  ldarg.1
0x2896  ldfld    class [mscorlib]System.Version Microsoft.VisualStudio.Setup.CheckForUpdatesResult::<OpcVersion>k__BackingField
0x289b  callvirt instance bool class [mscorlib]System.Collections.Generic.EqualityComparer`1<class [mscorlib]System.Version>::Equals(var<u1>, !!T0)
0x28a0  brfalse.s loc_28B9
0x28a2  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<int32>::get_Default()
0x28a7  ldarg.0
0x28a8  ldfld    int32 Microsoft.VisualStudio.Setup.CheckForUpdatesResult::<UpdateResultCode>k__BackingField
0x28ad  ldarg.1
0x28ae  ldfld    int32 Microsoft.VisualStudio.Setup.CheckForUpdatesResult::<UpdateResultCode>k__BackingField
0x28b3  callvirt instance bool class [mscorlib]System.Collections.Generic.EqualityComparer`1<int32>::Equals(var<u1>, !!T0)
0x28b8  ret
0x28b9  ldc.i4.0
0x28ba  ret
0x28bb  ldc.i4.1
0x28bc  ret
```
