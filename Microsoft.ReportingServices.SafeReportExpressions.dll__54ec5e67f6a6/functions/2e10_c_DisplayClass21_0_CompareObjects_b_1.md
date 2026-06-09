# <>c__DisplayClass21_0::<CompareObjects>b__1

- ea: `0x2e10`
- end: `0x2e2d`
- name: `<>c__DisplayClass21_0::<CompareObjects>b__1`
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
0x2e10  ldarg.0
0x2e11  ldfld    object <>c__DisplayClass21_0::legacyExprResult
0x2e16  unbox.any [mscorlib]System.Guid
0x2e1b  stloc.0
0x2e1c  ldloca.s 0
0x2e1e  ldarg.0
0x2e1f  ldfld    object <>c__DisplayClass21_0::safeExprResult
0x2e24  call     instance int32 [mscorlib]System.Guid::CompareTo(object)
0x2e29  ldc.i4.0
0x2e2a  ceq
0x2e2c  ret
```
