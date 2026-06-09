# <>f__AnonymousType0`3::ToString

- ea: `0x110`
- end: `0x19a`
- name: `<>f__AnonymousType0`3::ToString`
- size: `138`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x110`

## string_xrefs

- `0x111`: `{{ currentUICultureName = {0}, inputMethodLanguage = {1}, keyboardLayoutPreload = {2} }}`

## pseudocode

```c

```

## disassembly

```asm
0x110  ldnull
0x111  ldstr    aCurrentuicultu// "{{ currentUICultureName = {0}, inputMet"...
0x116  ldc.i4.3
0x117  newarr   [mscorlib]System.Object
0x11c  dup
0x11d  ldc.i4.0
0x11e  ldarg.0
0x11f  ldfld    var<u1> class <>f__AnonymousType0`3<var<u1>, !!T0, var<u1>>::<currentUICultureName>i__Field
0x124  stloc.0
0x125  ldloca.s 0
0x127  dup
0x128  ldobj    var<u1>
0x12d  box      var<u1>
0x132  brtrue.s loc_138
0x134  pop
0x135  ldnull
0x136  br.s     loc_143
0x138  constrained. var<u1>
0x13e  callvirt instance string [mscorlib]System.Object::ToString()
0x143  stelem.ref
0x144  dup
0x145  ldc.i4.1
0x146  ldarg.0
0x147  ldfld    var<u1> class <>f__AnonymousType0`3<var<u1>, !!T0, var<u1>>::<inputMethodLanguage>i__Field
0x14c  stloc.1
0x14d  ldloca.s 1
0x14f  dup
0x150  ldobj    var<u1>
0x155  box      var<u1>
0x15a  brtrue.s loc_160
0x15c  pop
0x15d  ldnull
0x15e  br.s     loc_16B
0x160  constrained. var<u1>
0x166  callvirt instance string [mscorlib]System.Object::ToString()
0x16b  stelem.ref
0x16c  dup
0x16d  ldc.i4.2
0x16e  ldarg.0
0x16f  ldfld    var<u1> class <>f__AnonymousType0`3<var<u1>, !!T0, var<u1>>::<keyboardLayoutPreload>i__Field
0x174  stloc.2
0x175  ldloca.s 2
0x177  dup
0x178  ldobj    var<u1>
0x17d  box      var<u1>
0x182  brtrue.s loc_188
0x184  pop
0x185  ldnull
0x186  br.s     loc_193
0x188  constrained. var<u1>
0x18e  callvirt instance string [mscorlib]System.Object::ToString()
0x193  stelem.ref
0x194  call     string [mscorlib]System.String::Format(class [mscorlib]System.IFormatProvider, string, object[])
0x199  ret
```
