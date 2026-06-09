# Microsoft.VisualStudio.Setup.ElevationResult::GetHashCode

- ea: `0xfb0`
- end: `0xfef`
- name: `Microsoft.VisualStudio.Setup.ElevationResult::GetHashCode`
- size: `63`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0xea0`

## pseudocode

```c

```

## disassembly

```asm
0xfb0  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<class [mscorlib]System.Type>::get_Default()
0xfb5  ldarg.0
0xfb6  callvirt instance class [mscorlib]System.Type Microsoft.VisualStudio.Setup.ElevationResult::get_EqualityContract()
0xfbb  callvirt instance int32 class [mscorlib]System.Collections.Generic.EqualityComparer`1<class [mscorlib]System.Type>::GetHashCode(var<u1>)
0xfc0  ldc.i4   0xA5555529
0xfc5  mul
0xfc6  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<bool>::get_Default()
0xfcb  ldarg.0
0xfcc  ldfld    bool Microsoft.VisualStudio.Setup.ElevationResult::<IsSuccess>k__BackingField
0xfd1  callvirt instance int32 class [mscorlib]System.Collections.Generic.EqualityComparer`1<bool>::GetHashCode(var<u1>)
0xfd6  add
0xfd7  ldc.i4   0xA5555529
0xfdc  mul
0xfdd  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<string>::get_Default()
0xfe2  ldarg.0
0xfe3  ldfld    string Microsoft.VisualStudio.Setup.ElevationResult::<PipeName>k__BackingField
0xfe8  callvirt instance int32 class [mscorlib]System.Collections.Generic.EqualityComparer`1<string>::GetHashCode(var<u1>)
0xfed  add
0xfee  ret
```
