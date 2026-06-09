# Microsoft.VisualStudio.Setup.ElevationRequest::Equals_0

- ea: `0xd30`
- end: `0xe01`
- name: `Microsoft.VisualStudio.Setup.ElevationRequest::Equals_0`
- size: `209`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0xc40`
- `0xd20`

## callees

- `0xa20`
- `0xd30`

## pseudocode

```c

```

## disassembly

```asm
0xd30  ldarg.0
0xd31  ldarg.1
0xd32  beq      loc_DFF
0xd37  ldarg.1
0xd38  brfalse  loc_DFD
0xd3d  ldarg.0
0xd3e  callvirt instance class [mscorlib]System.Type Microsoft.VisualStudio.Setup.ElevationRequest::get_EqualityContract()
0xd43  ldarg.1
0xd44  callvirt instance class [mscorlib]System.Type Microsoft.VisualStudio.Setup.ElevationRequest::get_EqualityContract()
0xd49  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0xd4e  brfalse  loc_DFD
0xd53  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<string>::get_Default()
0xd58  ldarg.0
0xd59  ldfld    string Microsoft.VisualStudio.Setup.ElevationRequest::<ActivityId>k__BackingField
0xd5e  ldarg.1
0xd5f  ldfld    string Microsoft.VisualStudio.Setup.ElevationRequest::<ActivityId>k__BackingField
0xd64  callvirt instance bool class [mscorlib]System.Collections.Generic.EqualityComparer`1<string>::Equals(var<u1>, !!T0)
0xd69  brfalse  loc_DFD
0xd6e  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<string>::get_Default()
0xd73  ldarg.0
0xd74  ldfld    string Microsoft.VisualStudio.Setup.ElevationRequest::<SerializedSession>k__BackingField
0xd79  ldarg.1
0xd7a  ldfld    string Microsoft.VisualStudio.Setup.ElevationRequest::<SerializedSession>k__BackingField
0xd7f  callvirt instance bool class [mscorlib]System.Collections.Generic.EqualityComparer`1<string>::Equals(var<u1>, !!T0)
0xd84  brfalse.s loc_DFD
0xd86  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<string>::get_Default()
0xd8b  ldarg.0
0xd8c  ldfld    string Microsoft.VisualStudio.Setup.ElevationRequest::<Locale>k__BackingField
0xd91  ldarg.1
0xd92  ldfld    string Microsoft.VisualStudio.Setup.ElevationRequest::<Locale>k__BackingField
0xd97  callvirt instance bool class [mscorlib]System.Collections.Generic.EqualityComparer`1<string>::Equals(var<u1>, !!T0)
0xd9c  brfalse.s loc_DFD
0xd9e  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<string>::get_Default()
0xda3  ldarg.0
0xda4  ldfld    string Microsoft.VisualStudio.Setup.ElevationRequest::<CampaignId>k__BackingField
0xda9  ldarg.1
0xdaa  ldfld    string Microsoft.VisualStudio.Setup.ElevationRequest::<CampaignId>k__BackingField
0xdaf  callvirt instance bool class [mscorlib]System.Collections.Generic.EqualityComparer`1<string>::Equals(var<u1>, !!T0)
0xdb4  brfalse.s loc_DFD
0xdb6  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<int64>::get_Default()
0xdbb  ldarg.0
0xdbc  ldfld    int64 Microsoft.VisualStudio.Setup.ElevationRequest::<Handle>k__BackingField
0xdc1  ldarg.1
0xdc2  ldfld    int64 Microsoft.VisualStudio.Setup.ElevationRequest::<Handle>k__BackingField
0xdc7  callvirt instance bool class [mscorlib]System.Collections.Generic.EqualityComparer`1<int64>::Equals(var<u1>, !!T0)
0xdcc  brfalse.s loc_DFD
0xdce  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<bool>::get_Default()
0xdd3  ldarg.0
0xdd4  ldfld    bool Microsoft.VisualStudio.Setup.ElevationRequest::<IsQuiet>k__BackingField
0xdd9  ldarg.1
0xdda  ldfld    bool Microsoft.VisualStudio.Setup.ElevationRequest::<IsQuiet>k__BackingField
0xddf  callvirt instance bool class [mscorlib]System.Collections.Generic.EqualityComparer`1<bool>::Equals(var<u1>, !!T0)
0xde4  brfalse.s loc_DFD
0xde6  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<bool>::get_Default()
0xdeb  ldarg.0
0xdec  ldfld    bool Microsoft.VisualStudio.Setup.ElevationRequest::<IsPassive>k__BackingField
0xdf1  ldarg.1
0xdf2  ldfld    bool Microsoft.VisualStudio.Setup.ElevationRequest::<IsPassive>k__BackingField
0xdf7  callvirt instance bool class [mscorlib]System.Collections.Generic.EqualityComparer`1<bool>::Equals(var<u1>, !!T0)
0xdfc  ret
0xdfd  ldc.i4.0
0xdfe  ret
0xdff  ldc.i4.1
0xe00  ret
```
