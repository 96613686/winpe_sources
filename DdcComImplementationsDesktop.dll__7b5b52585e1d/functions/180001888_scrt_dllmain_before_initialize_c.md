# __scrt_dllmain_before_initialize_c

- ea: `0x180001888`
- end: `0x18000188f`
- name: `__scrt_dllmain_before_initialize_c`
- size: `7`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001388`

## callees

- `0x1800019c8`

## pseudocode

```c
__int64 _scrt_dllmain_before_initialize_c()
{
  return _scrt_initialize_onexit_tables(0);
}

```

## disassembly

```asm
0x180001888  xor     ecx, ecx
0x18000188a  jmp     __scrt_initialize_onexit_tables
```
