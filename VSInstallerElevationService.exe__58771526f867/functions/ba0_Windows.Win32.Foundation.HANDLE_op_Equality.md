# Windows.Win32.Foundation.HANDLE::op_Equality

- ea: `0xba0`
- end: `0xbb2`
- name: `Windows.Win32.Foundation.HANDLE::op_Equality`
- size: `18`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0xbc0`

## pseudocode

```c

```

## disassembly

```asm
0xba0  ldarg.0
0xba1  ldfld    native int Windows.Win32.Foundation.HANDLE::Value
0xba6  ldarg.1
0xba7  ldfld    native int Windows.Win32.Foundation.HANDLE::Value
0xbac  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0xbb1  ret
```
