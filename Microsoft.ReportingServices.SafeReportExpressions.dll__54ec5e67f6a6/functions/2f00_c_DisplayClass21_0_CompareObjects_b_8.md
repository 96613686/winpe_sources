# <>c__DisplayClass21_0::<CompareObjects>b__8

- ea: `0x2f00`
- end: `0x2f1d`
- name: `<>c__DisplayClass21_0::<CompareObjects>b__8`
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
0x2f00  ldarg.0
0x2f01  ldfld    object <>c__DisplayClass21_0::legacyExprResult
0x2f06  unbox.any [mscorlib]System.Byte
0x2f0b  stloc.0
0x2f0c  ldloca.s 0
0x2f0e  ldarg.0
0x2f0f  ldfld    object <>c__DisplayClass21_0::safeExprResult
0x2f14  call     instance int32 [mscorlib]System.Byte::CompareTo(object)
0x2f19  ldc.i4.0
0x2f1a  ceq
0x2f1c  ret
```
