# <>c__DisplayClass21_0::<CompareObjects>b__10

- ea: `0x2f40`
- end: `0x2f5d`
- name: `<>c__DisplayClass21_0::<CompareObjects>b__10`
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
0x2f40  ldarg.0
0x2f41  ldfld    object <>c__DisplayClass21_0::legacyExprResult
0x2f46  unbox.any [mscorlib]System.UInt16
0x2f4b  stloc.0
0x2f4c  ldloca.s 0
0x2f4e  ldarg.0
0x2f4f  ldfld    object <>c__DisplayClass21_0::safeExprResult
0x2f54  call     instance int32 [mscorlib]System.UInt16::CompareTo(object)
0x2f59  ldc.i4.0
0x2f5a  ceq
0x2f5c  ret
```
