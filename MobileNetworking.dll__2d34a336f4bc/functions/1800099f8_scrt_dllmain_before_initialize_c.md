# __scrt_dllmain_before_initialize_c

- ea: `0x1800099f8`
- end: `0x1800099ff`
- name: `__scrt_dllmain_before_initialize_c`
- size: `7`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180009538`

## callees

- `0x180009b38`

## pseudocode

```c
__int64 _scrt_dllmain_before_initialize_c()
{
  return _scrt_initialize_onexit_tables(0);
}

```

## disassembly

```asm
0x1800099f8  xor     ecx, ecx
0x1800099fa  jmp     __scrt_initialize_onexit_tables
```
