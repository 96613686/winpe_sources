# <>c__DisplayClass21_0::<CompareObjects>b__15

- ea: `0x2fe0`
- end: `0x2ffd`
- name: `<>c__DisplayClass21_0::<CompareObjects>b__15`
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
0x2fe0  ldarg.0
0x2fe1  ldfld    object <>c__DisplayClass21_0::legacyExprResult
0x2fe6  unbox.any [mscorlib]System.Single
0x2feb  stloc.0
0x2fec  ldloca.s 0
0x2fee  ldarg.0
0x2fef  ldfld    object <>c__DisplayClass21_0::safeExprResult
0x2ff4  call     instance int32 [mscorlib]System.Single::CompareTo(object)
0x2ff9  ldc.i4.0
0x2ffa  ceq
0x2ffc  ret
```
