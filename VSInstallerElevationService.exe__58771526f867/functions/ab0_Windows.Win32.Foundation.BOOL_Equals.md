# Windows.Win32.Foundation.BOOL::Equals

- ea: `0xab0`
- end: `0xabf`
- name: `Windows.Win32.Foundation.BOOL::Equals`
- size: `15`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0xac0`

## pseudocode

```c

```

## disassembly

```asm
0xab0  ldarg.0
0xab1  ldfld    int32 Windows.Win32.Foundation.BOOL::Value
0xab6  ldarg.1
0xab7  ldfld    int32 Windows.Win32.Foundation.BOOL::Value
0xabc  ceq
0xabe  ret
```
