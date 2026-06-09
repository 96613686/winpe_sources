# Microsoft.VisualStudio.Setup.Extensions::IsNullOrEmpty

- ea: `0x61d0`
- end: `0x61d7`
- name: `Microsoft.VisualStudio.Setup.Extensions::IsNullOrEmpty`
- size: `7`
- prototype: ``
- caller_count: `8`
- callee_count: `0`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x30e0`
- `0x63f0`
- `0xd400`
- `0x10010`
- `0x100b0`
- `0x16c00`
- `0x16e40`
- `0x170e0`

## pseudocode

```c

```

## disassembly

```asm
0x61d0  ldarg.0
0x61d1  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x61d6  ret
```
