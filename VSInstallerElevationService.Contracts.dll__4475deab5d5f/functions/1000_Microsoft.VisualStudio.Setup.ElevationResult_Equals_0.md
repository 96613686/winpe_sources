# Microsoft.VisualStudio.Setup.ElevationResult::Equals_0

- ea: `0x1000`
- end: `0x104d`
- name: `Microsoft.VisualStudio.Setup.ElevationResult::Equals_0`
- size: `77`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0xf90`
- `0xff0`

## callees

- `0xea0`
- `0x1000`

## pseudocode

```c

```

## disassembly

```asm
0x1000  ldarg.0
0x1001  ldarg.1
0x1002  beq.s    loc_104B
0x1004  ldarg.1
0x1005  brfalse.s loc_1049
0x1007  ldarg.0
0x1008  callvirt instance class [mscorlib]System.Type Microsoft.VisualStudio.Setup.ElevationResult::get_EqualityContract()
0x100d  ldarg.1
0x100e  callvirt instance class [mscorlib]System.Type Microsoft.VisualStudio.Setup.ElevationResult::get_EqualityContract()
0x1013  call     bool [mscorlib]System.Type::op_Equality(class [mscorlib]System.Type, class [mscorlib]System.Type)
0x1018  brfalse.s loc_1049
0x101a  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<bool>::get_Default()
0x101f  ldarg.0
0x1020  ldfld    bool Microsoft.VisualStudio.Setup.ElevationResult::<IsSuccess>k__BackingField
0x1025  ldarg.1
0x1026  ldfld    bool Microsoft.VisualStudio.Setup.ElevationResult::<IsSuccess>k__BackingField
0x102b  callvirt instance bool class [mscorlib]System.Collections.Generic.EqualityComparer`1<bool>::Equals(var<u1>, !!T0)
0x1030  brfalse.s loc_1049
0x1032  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<string>::get_Default()
0x1037  ldarg.0
0x1038  ldfld    string Microsoft.VisualStudio.Setup.ElevationResult::<PipeName>k__BackingField
0x103d  ldarg.1
0x103e  ldfld    string Microsoft.VisualStudio.Setup.ElevationResult::<PipeName>k__BackingField
0x1043  callvirt instance bool class [mscorlib]System.Collections.Generic.EqualityComparer`1<string>::Equals(var<u1>, !!T0)
0x1048  ret
0x1049  ldc.i4.0
0x104a  ret
0x104b  ldc.i4.1
0x104c  ret
```
