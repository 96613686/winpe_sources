# Windows.Win32.Foundation.BOOL::op_Equality

- ea: `0xa90`
- end: `0xa9f`
- name: `Windows.Win32.Foundation.BOOL::op_Equality`
- size: `15`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0xaa0`

## pseudocode

```c

```

## disassembly

```asm
0xa90  ldarg.0
0xa91  ldfld    int32 Windows.Win32.Foundation.BOOL::Value
0xa96  ldarg.1
0xa97  ldfld    int32 Windows.Win32.Foundation.BOOL::Value
0xa9c  ceq
0xa9e  ret
```
