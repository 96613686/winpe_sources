# __scrt_dllmain_before_initialize_c

- ea: `0x18000217c`
- end: `0x180002183`
- name: `__scrt_dllmain_before_initialize_c`
- size: `7`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001d18`

## callees

- `0x1800022bc`

## pseudocode

```c
__int64 _scrt_dllmain_before_initialize_c()
{
  return _scrt_initialize_onexit_tables(0);
}

```

## disassembly

```asm
0x18000217c  xor     ecx, ecx
0x18000217e  jmp     __scrt_initialize_onexit_tables
```
