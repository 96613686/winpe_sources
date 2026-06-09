# __scrt_dllmain_before_initialize_c

- ea: `0x1800016b0`
- end: `0x1800016b7`
- name: `__scrt_dllmain_before_initialize_c`
- size: `7`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800012f8`

## callees

- `0x1800017f0`

## pseudocode

```c
__int64 _scrt_dllmain_before_initialize_c()
{
  return _scrt_initialize_onexit_tables(0);
}

```

## disassembly

```asm
0x1800016b0  xor     ecx, ecx
0x1800016b2  jmp     __scrt_initialize_onexit_tables
```
