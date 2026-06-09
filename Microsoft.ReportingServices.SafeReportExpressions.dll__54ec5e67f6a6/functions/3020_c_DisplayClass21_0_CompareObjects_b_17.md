# <>c__DisplayClass21_0::<CompareObjects>b__17

- ea: `0x3020`
- end: `0x303d`
- name: `<>c__DisplayClass21_0::<CompareObjects>b__17`
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
0x3020  ldarg.0
0x3021  ldfld    object <>c__DisplayClass21_0::legacyExprResult
0x3026  unbox.any [mscorlib]System.Decimal
0x302b  stloc.0
0x302c  ldloca.s 0
0x302e  ldarg.0
0x302f  ldfld    object <>c__DisplayClass21_0::safeExprResult
0x3034  call     instance int32 [mscorlib]System.Decimal::CompareTo(object)
0x3039  ldc.i4.0
0x303a  ceq
0x303c  ret
```
