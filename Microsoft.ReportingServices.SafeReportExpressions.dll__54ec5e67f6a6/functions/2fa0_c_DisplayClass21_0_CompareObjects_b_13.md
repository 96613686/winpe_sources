# <>c__DisplayClass21_0::<CompareObjects>b__13

- ea: `0x2fa0`
- end: `0x2fbd`
- name: `<>c__DisplayClass21_0::<CompareObjects>b__13`
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
0x2fa0  ldarg.0
0x2fa1  ldfld    object <>c__DisplayClass21_0::legacyExprResult
0x2fa6  unbox.any [mscorlib]System.Int64
0x2fab  stloc.0
0x2fac  ldloca.s 0
0x2fae  ldarg.0
0x2faf  ldfld    object <>c__DisplayClass21_0::safeExprResult
0x2fb4  call     instance int32 [mscorlib]System.Int64::CompareTo(object)
0x2fb9  ldc.i4.0
0x2fba  ceq
0x2fbc  ret
```
