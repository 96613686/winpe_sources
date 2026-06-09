# <>f__AnonymousType0`3::GetHashCode

- ea: `0xc0`
- end: `0x10b`
- name: `<>f__AnonymousType0`3::GetHashCode`
- size: `75`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c

```

## disassembly

```asm
0xc0  ldc.i4   0x7583ECE9
0xc5  ldc.i4   0xA5555529
0xca  mul
0xcb  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::get_Default()
0xd0  ldarg.0
0xd1  ldfld    var<u1> class <>f__AnonymousType0`3<var<u1>, !!T0, var<u1>>::<currentUICultureName>i__Field
0xd6  callvirt instance int32 class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::GetHashCode(var<u1>)
0xdb  add
0xdc  ldc.i4   0xA5555529
0xe1  mul
0xe2  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::get_Default()
0xe7  ldarg.0
0xe8  ldfld    var<u1> class <>f__AnonymousType0`3<var<u1>, !!T0, var<u1>>::<inputMethodLanguage>i__Field
0xed  callvirt instance int32 class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::GetHashCode(var<u1>)
0xf2  add
0xf3  ldc.i4   0xA5555529
0xf8  mul
0xf9  call     class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>> class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::get_Default()
0xfe  ldarg.0
0xff  ldfld    var<u1> class <>f__AnonymousType0`3<var<u1>, !!T0, var<u1>>::<keyboardLayoutPreload>i__Field
0x104  callvirt instance int32 class [mscorlib]System.Collections.Generic.EqualityComparer`1<var<u1>>::GetHashCode(var<u1>)
0x109  add
0x10a  ret
```
