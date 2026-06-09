# __scrt_dllmain_before_initialize_c

- ea: `0x18000ec10`
- end: `0x18000ec17`
- name: `__scrt_dllmain_before_initialize_c`
- size: `7`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000e858`

## callees

- `0x18000ed50`

## pseudocode

```c
__int64 _scrt_dllmain_before_initialize_c()
{
  return _scrt_initialize_onexit_tables(0);
}

```

## disassembly

```asm
0x18000ec10  xor     ecx, ecx
0x18000ec12  jmp     __scrt_initialize_onexit_tables
```
