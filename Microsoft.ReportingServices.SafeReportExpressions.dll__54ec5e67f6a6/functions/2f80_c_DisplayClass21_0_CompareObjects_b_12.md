# <>c__DisplayClass21_0::<CompareObjects>b__12

- ea: `0x2f80`
- end: `0x2f9d`
- name: `<>c__DisplayClass21_0::<CompareObjects>b__12`
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
0x2f80  ldarg.0
0x2f81  ldfld    object <>c__DisplayClass21_0::legacyExprResult
0x2f86  unbox.any [mscorlib]System.UInt32
0x2f8b  stloc.0
0x2f8c  ldloca.s 0
0x2f8e  ldarg.0
0x2f8f  ldfld    object <>c__DisplayClass21_0::safeExprResult
0x2f94  call     instance int32 [mscorlib]System.UInt32::CompareTo(object)
0x2f99  ldc.i4.0
0x2f9a  ceq
0x2f9c  ret
```
