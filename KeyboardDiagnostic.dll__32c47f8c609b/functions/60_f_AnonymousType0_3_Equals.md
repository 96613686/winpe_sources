# <>f__AnonymousType0`3::Equals

- ea: `0x60`
- end: `0xb9`
- name: `<>f__AnonymousType0`3::Equals`
- size: `89`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x60`

## pseudocode

```c

```

## disassembly

```asm
0x60  ldarg.1
0x61  isinst   class <>f__AnonymousType0`3<var<u1>, !!T0, var<u1>>
0x66  stloc.0
0x67  ldarg.0
0x68  ldloc.0
0x69  beq.s    loc_B7
0x6b  ldloc.0
0x6c  brfalse.s loc_B5
0x6e  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::get_Default()
0x73  ldarg.0
0x74  ldfld    var<u1> class <>f__AnonymousType0`3<var<u1>, !!T0, var<u1>>::<currentUICultureName>i__Field
0x79  ldloc.0
0x7a  ldfld    var<u1> class <>f__AnonymousType0`3<var<u1>, !!T0, var<u1>>::<currentUICultureName>i__Field
0x7f  callvirt instance bool class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::Equals(var<u1>, !!T0)
0x84  brfalse.s loc_B5
0x86  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::get_Default()
0x8b  ldarg.0
0x8c  ldfld    var<u1> class <>f__AnonymousType0`3<var<u1>, !!T0, var<u1>>::<inputMethodLanguage>i__Field
0x91  ldloc.0
0x92  ldfld    var<u1> class <>f__AnonymousType0`3<var<u1>, !!T0, var<u1>>::<inputMethodLanguage>i__Field
0x97  callvirt instance bool class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::Equals(var<u1>, !!T0)
0x9c  brfalse.s loc_B5
0x9e  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::get_Default()
0xa3  ldarg.0
0xa4  ldfld    var<u1> class <>f__AnonymousType0`3<var<u1>, !!T0, var<u1>>::<keyboardLayoutPreload>i__Field
0xa9  ldloc.0
0xaa  ldfld    var<u1> class <>f__AnonymousType0`3<var<u1>, !!T0, var<u1>>::<keyboardLayoutPreload>i__Field
0xaf  callvirt instance bool class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::Equals(var<u1>, !!T0)
0xb4  ret
0xb5  ldc.i4.0
0xb6  ret
0xb7  ldc.i4.1
0xb8  ret
```
