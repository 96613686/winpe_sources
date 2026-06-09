# <>c__DisplayClass21_0::<CompareObjects>b__2

- ea: `0x2e30`
- end: `0x2e52`
- name: `<>c__DisplayClass21_0::<CompareObjects>b__2`
- size: `34`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c

```

## disassembly

```asm
0x2e30  ldarg.0
0x2e31  ldfld    object <>c__DisplayClass21_0::legacyExprResult
0x2e36  unbox.any [mscorlib]System.DateTimeOffset
0x2e3b  stloc.0
0x2e3c  ldloca.s 0
0x2e3e  ldarg.0
0x2e3f  ldfld    object <>c__DisplayClass21_0::safeExprResult
0x2e44  unbox.any [mscorlib]System.DateTimeOffset
0x2e49  call     instance int32 [mscorlib]System.DateTimeOffset::CompareTo(valuetype [mscorlib]System.DateTimeOffset)
0x2e4e  ldc.i4.0
0x2e4f  ceq
0x2e51  ret
```
