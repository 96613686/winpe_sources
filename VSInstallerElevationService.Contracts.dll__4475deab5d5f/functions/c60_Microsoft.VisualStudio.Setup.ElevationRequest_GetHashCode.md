# Microsoft.VisualStudio.Setup.ElevationRequest::GetHashCode

- ea: `0xc60`
- end: `0xd12`
- name: `Microsoft.VisualStudio.Setup.ElevationRequest::GetHashCode`
- size: `178`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0xa20`

## pseudocode

```c

```

## disassembly

```asm
0xc60  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<class [mscorlib]System.Type>::get_Default()
0xc65  ldarg.0
0xc66  callvirt instance class [mscorlib]System.Type Microsoft.VisualStudio.Setup.ElevationRequest::get_EqualityContract()
0xc6b  callvirt instance int32 class [mscorlib]System.Collections.Generic.EqualityComparer`1<class [mscorlib]System.Type>::GetHashCode(var<u1>)
0xc70  ldc.i4   0xA5555529
0xc75  mul
0xc76  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<string>::get_Default()
0xc7b  ldarg.0
0xc7c  ldfld    string Microsoft.VisualStudio.Setup.ElevationRequest::<ActivityId>k__BackingField
0xc81  callvirt instance int32 class [mscorlib]System.Collections.Generic.EqualityComparer`1<string>::GetHashCode(var<u1>)
0xc86  add
0xc87  ldc.i4   0xA5555529
0xc8c  mul
0xc8d  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<string>::get_Default()
0xc92  ldarg.0
0xc93  ldfld    string Microsoft.VisualStudio.Setup.ElevationRequest::<SerializedSession>k__BackingField
0xc98  callvirt instance int32 class [mscorlib]System.Collections.Generic.EqualityComparer`1<string>::GetHashCode(var<u1>)
0xc9d  add
0xc9e  ldc.i4   0xA5555529
0xca3  mul
0xca4  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<string>::get_Default()
0xca9  ldarg.0
0xcaa  ldfld    string Microsoft.VisualStudio.Setup.ElevationRequest::<Locale>k__BackingField
0xcaf  callvirt instance int32 class [mscorlib]System.Collections.Generic.EqualityComparer`1<string>::GetHashCode(var<u1>)
0xcb4  add
0xcb5  ldc.i4   0xA5555529
0xcba  mul
0xcbb  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<string>::get_Default()
0xcc0  ldarg.0
0xcc1  ldfld    string Microsoft.VisualStudio.Setup.ElevationRequest::<CampaignId>k__BackingField
0xcc6  callvirt instance int32 class [mscorlib]System.Collections.Generic.EqualityComparer`1<string>::GetHashCode(var<u1>)
0xccb  add
0xccc  ldc.i4   0xA5555529
0xcd1  mul
0xcd2  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<int64>::get_Default()
0xcd7  ldarg.0
0xcd8  ldfld    int64 Microsoft.VisualStudio.Setup.ElevationRequest::<Handle>k__BackingField
0xcdd  callvirt instance int32 class [mscorlib]System.Collections.Generic.EqualityComparer`1<int64>::GetHashCode(var<u1>)
0xce2  add
0xce3  ldc.i4   0xA5555529
0xce8  mul
0xce9  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<bool>::get_Default()
0xcee  ldarg.0
0xcef  ldfld    bool Microsoft.VisualStudio.Setup.ElevationRequest::<IsQuiet>k__BackingField
0xcf4  callvirt instance int32 class [mscorlib]System.Collections.Generic.EqualityComparer`1<bool>::GetHashCode(var<u1>)
0xcf9  add
0xcfa  ldc.i4   0xA5555529
0xcff  mul
0xd00  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<bool>::get_Default()
0xd05  ldarg.0
0xd06  ldfld    bool Microsoft.VisualStudio.Setup.ElevationRequest::<IsPassive>k__BackingField
0xd0b  callvirt instance int32 class [mscorlib]System.Collections.Generic.EqualityComparer`1<bool>::GetHashCode(var<u1>)
0xd10  add
0xd11  ret
```
