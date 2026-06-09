# PROPVARIANT::get_DeviceTypeValue

- ea: `0x1050`
- end: `0x105c`
- name: `PROPVARIANT::get_DeviceTypeValue`
- size: `12`
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
0x1050  ldarg.0
0x1051  ldflda   valuetype UnionMembers PROPVARIANT::unionmembers
0x1056  ldfld    unsigned int32 UnionMembers::deviceTypeValue
0x105b  ret
```
