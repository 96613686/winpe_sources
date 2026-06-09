# <>c__DisplayClass21_0::<CompareObjects>b__18

- ea: `0x3040`
- end: `0x305d`
- name: `<>c__DisplayClass21_0::<CompareObjects>b__18`
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
0x3040  ldarg.0
0x3041  ldfld    object <>c__DisplayClass21_0::legacyExprResult
0x3046  unbox.any [mscorlib]System.DateTime
0x304b  stloc.0
0x304c  ldloca.s 0
0x304e  ldarg.0
0x304f  ldfld    object <>c__DisplayClass21_0::safeExprResult
0x3054  call     instance int32 [mscorlib]System.DateTime::CompareTo(object)
0x3059  ldc.i4.0
0x305a  ceq
0x305c  ret
```
