# <>c__DisplayClass21_0::<CompareObjects>b__6

- ea: `0x2ec0`
- end: `0x2edd`
- name: `<>c__DisplayClass21_0::<CompareObjects>b__6`
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
0x2ec0  ldarg.0
0x2ec1  ldfld    object <>c__DisplayClass21_0::legacyExprResult
0x2ec6  unbox.any [mscorlib]System.Char
0x2ecb  stloc.0
0x2ecc  ldloca.s 0
0x2ece  ldarg.0
0x2ecf  ldfld    object <>c__DisplayClass21_0::safeExprResult
0x2ed4  call     instance int32 [mscorlib]System.Char::CompareTo(object)
0x2ed9  ldc.i4.0
0x2eda  ceq
0x2edc  ret
```
