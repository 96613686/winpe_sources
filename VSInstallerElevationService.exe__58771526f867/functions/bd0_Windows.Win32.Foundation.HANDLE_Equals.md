# Windows.Win32.Foundation.HANDLE::Equals

- ea: `0xbd0`
- end: `0xbe2`
- name: `Windows.Win32.Foundation.HANDLE::Equals`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0xbf0`

## pseudocode

```c

```

## disassembly

```asm
0xbd0  ldarg.0
0xbd1  ldfld    native int Windows.Win32.Foundation.HANDLE::Value
0xbd6  ldarg.1
0xbd7  ldfld    native int Windows.Win32.Foundation.HANDLE::Value
0xbdc  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0xbe1  ret
```
