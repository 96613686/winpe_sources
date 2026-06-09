# <>c__DisplayClass21_0::<CompareObjects>b__9

- ea: `0x2f20`
- end: `0x2f3d`
- name: `<>c__DisplayClass21_0::<CompareObjects>b__9`
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
0x2f20  ldarg.0
0x2f21  ldfld    object <>c__DisplayClass21_0::legacyExprResult
0x2f26  unbox.any [mscorlib]System.Int16
0x2f2b  stloc.0
0x2f2c  ldloca.s 0
0x2f2e  ldarg.0
0x2f2f  ldfld    object <>c__DisplayClass21_0::safeExprResult
0x2f34  call     instance int32 [mscorlib]System.Int16::CompareTo(object)
0x2f39  ldc.i4.0
0x2f3a  ceq
0x2f3c  ret
```
