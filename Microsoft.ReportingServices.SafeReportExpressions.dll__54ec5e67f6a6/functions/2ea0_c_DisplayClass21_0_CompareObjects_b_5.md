# <>c__DisplayClass21_0::<CompareObjects>b__5

- ea: `0x2ea0`
- end: `0x2ebd`
- name: `<>c__DisplayClass21_0::<CompareObjects>b__5`
- size: `29`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x2ea0  ldarg.0
0x2ea1  ldfld    object <>c__DisplayClass21_0::legacyExprResult
0x2ea6  unbox.any [mscorlib]System.Boolean
0x2eab  stloc.0
0x2eac  ldloca.s 0
0x2eae  ldarg.0
0x2eaf  ldfld    object <>c__DisplayClass21_0::safeExprResult
0x2eb4  call     instance int32 [mscorlib]System.Boolean::CompareTo(object)
0x2eb9  ldc.i4.0
0x2eba  ceq
0x2ebc  ret
```
