# Microsoft.VisualStudio.Setup.CheckForUpdatesResult::GetHashCode

- ea: `0x27c0`
- end: `0x282d`
- name: `Microsoft.VisualStudio.Setup.CheckForUpdatesResult::GetHashCode`
- size: `109`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x2630`

## pseudocode

```c

```

## disassembly

```asm
0x27c0  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<class [mscorlib]System.Type>::get_Default()
0x27c5  ldarg.0
0x27c6  callvirt instance class [mscorlib]System.Type Microsoft.VisualStudio.Setup.CheckForUpdatesResult::get_EqualityContract()
0x27cb  callvirt instance int32 class [mscorlib]System.Collections.Generic.EqualityComparer`1<class [mscorlib]System.Type>::GetHashCode(var<u1>)
0x27d0  ldc.i4   0xA5555529
0x27d5  mul
0x27d6  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<bool>::get_Default()
0x27db  ldarg.0
0x27dc  ldfld    bool Microsoft.VisualStudio.Setup.CheckForUpdatesResult::<EngineUpdateRequired>k__BackingField
0x27e1  callvirt instance int32 class [mscorlib]System.Collections.Generic.EqualityComparer`1<bool>::GetHashCode(var<u1>)
0x27e6  add
0x27e7  ldc.i4   0xA5555529
0x27ec  mul
0x27ed  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<string>::get_Default()
0x27f2  ldarg.0
0x27f3  ldfld    string Microsoft.VisualStudio.Setup.CheckForUpdatesResult::<OpcUrl>k__BackingField
0x27f8  callvirt instance int32 class [mscorlib]System.Collections.Generic.EqualityComparer`1<string>::GetHashCode(var<u1>)
0x27fd  add
0x27fe  ldc.i4   0xA5555529
0x2803  mul
0x2804  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<class [mscorlib]System.Version>::get_Default()
0x2809  ldarg.0
0x280a  ldfld    class [mscorlib]System.Version Microsoft.VisualStudio.Setup.CheckForUpdatesResult::<OpcVersion>k__BackingField
0x280f  callvirt instance int32 class [mscorlib]System.Collections.Generic.EqualityComparer`1<class [mscorlib]System.Version>::GetHashCode(var<u1>)
0x2814  add
0x2815  ldc.i4   0xA5555529
0x281a  mul
0x281b  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<int32>::get_Default()
0x2820  ldarg.0
0x2821  ldfld    int32 Microsoft.VisualStudio.Setup.CheckForUpdatesResult::<UpdateResultCode>k__BackingField
0x2826  callvirt instance int32 class [mscorlib]System.Collections.Generic.EqualityComparer`1<int32>::GetHashCode(var<u1>)
0x282b  add
0x282c  ret
```
