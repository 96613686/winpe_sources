# PROPVARIANT::get_DeviceName

- ea: `0x1030`
- end: `0x1041`
- name: `PROPVARIANT::get_DeviceName`
- size: `17`
- prototype: ``
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x160`

## pseudocode

```c

```

## disassembly

```asm
0x1030  ldarg.0
0x1031  ldflda   valuetype UnionMembers PROPVARIANT::unionmembers
0x1036  ldfld    native int UnionMembers::deviceName
0x103b  call     string [mscorlib]System.Runtime.InteropServices.Marshal::PtrToStringAuto(native int)
0x1040  ret
```
