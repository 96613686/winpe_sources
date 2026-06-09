# __scrt_dllmain_before_initialize_c

- ea: `0x180002104`
- end: `0x18000210b`
- name: `__scrt_dllmain_before_initialize_c`
- size: `7`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001d08`

## callees

- `0x180002244`

## pseudocode

```c
__int64 _scrt_dllmain_before_initialize_c()
{
  return _scrt_initialize_onexit_tables(0);
}

```

## disassembly

```asm
0x180002104  xor     ecx, ecx
0x180002106  jmp     __scrt_initialize_onexit_tables
```
