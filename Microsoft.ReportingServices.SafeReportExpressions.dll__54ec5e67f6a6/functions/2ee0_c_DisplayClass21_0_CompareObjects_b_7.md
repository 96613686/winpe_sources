# <>c__DisplayClass21_0::<CompareObjects>b__7

- ea: `0x2ee0`
- end: `0x2efd`
- name: `<>c__DisplayClass21_0::<CompareObjects>b__7`
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
0x2ee0  ldarg.0
0x2ee1  ldfld    object <>c__DisplayClass21_0::legacyExprResult
0x2ee6  unbox.any [mscorlib]System.SByte
0x2eeb  stloc.0
0x2eec  ldloca.s 0
0x2eee  ldarg.0
0x2eef  ldfld    object <>c__DisplayClass21_0::safeExprResult
0x2ef4  call     instance int32 [mscorlib]System.SByte::CompareTo(object)
0x2ef9  ldc.i4.0
0x2efa  ceq
0x2efc  ret
```
