# <>c__DisplayClass21_0::<CompareObjects>b__16

- ea: `0x3000`
- end: `0x301d`
- name: `<>c__DisplayClass21_0::<CompareObjects>b__16`
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
0x3000  ldarg.0
0x3001  ldfld    object <>c__DisplayClass21_0::legacyExprResult
0x3006  unbox.any [mscorlib]System.Double
0x300b  stloc.0
0x300c  ldloca.s 0
0x300e  ldarg.0
0x300f  ldfld    object <>c__DisplayClass21_0::safeExprResult
0x3014  call     instance int32 [mscorlib]System.Double::CompareTo(object)
0x3019  ldc.i4.0
0x301a  ceq
0x301c  ret
```
