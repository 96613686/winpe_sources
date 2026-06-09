# <>c__DisplayClass21_0::<CompareObjects>b__3

- ea: `0x2e60`
- end: `0x2e7d`
- name: `<>c__DisplayClass21_0::<CompareObjects>b__3`
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
0x2e60  ldarg.0
0x2e61  ldfld    object <>c__DisplayClass21_0::legacyExprResult
0x2e66  unbox.any [mscorlib]System.TimeSpan
0x2e6b  stloc.0
0x2e6c  ldloca.s 0
0x2e6e  ldarg.0
0x2e6f  ldfld    object <>c__DisplayClass21_0::safeExprResult
0x2e74  call     instance int32 [mscorlib]System.TimeSpan::CompareTo(object)
0x2e79  ldc.i4.0
0x2e7a  ceq
0x2e7c  ret
```
