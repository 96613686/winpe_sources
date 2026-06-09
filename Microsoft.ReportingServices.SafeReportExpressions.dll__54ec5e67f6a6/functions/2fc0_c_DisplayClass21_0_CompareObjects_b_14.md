# <>c__DisplayClass21_0::<CompareObjects>b__14

- ea: `0x2fc0`
- end: `0x2fdd`
- name: `<>c__DisplayClass21_0::<CompareObjects>b__14`
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
0x2fc0  ldarg.0
0x2fc1  ldfld    object <>c__DisplayClass21_0::legacyExprResult
0x2fc6  unbox.any [mscorlib]System.UInt64
0x2fcb  stloc.0
0x2fcc  ldloca.s 0
0x2fce  ldarg.0
0x2fcf  ldfld    object <>c__DisplayClass21_0::safeExprResult
0x2fd4  call     instance int32 [mscorlib]System.UInt64::CompareTo(object)
0x2fd9  ldc.i4.0
0x2fda  ceq
0x2fdc  ret
```
