# <>c__DisplayClass21_0::<CompareObjects>b__11

- ea: `0x2f60`
- end: `0x2f7d`
- name: `<>c__DisplayClass21_0::<CompareObjects>b__11`
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
0x2f60  ldarg.0
0x2f61  ldfld    object <>c__DisplayClass21_0::legacyExprResult
0x2f66  unbox.any [mscorlib]System.Int32
0x2f6b  stloc.0
0x2f6c  ldloca.s 0
0x2f6e  ldarg.0
0x2f6f  ldfld    object <>c__DisplayClass21_0::safeExprResult
0x2f74  call     instance int32 [mscorlib]System.Int32::CompareTo(object)
0x2f79  ldc.i4.0
0x2f7a  ceq
0x2f7c  ret
```
