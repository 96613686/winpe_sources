# __scrt_dllmain_before_initialize_c

- ea: `0x18000193c`
- end: `0x180001943`
- name: `__scrt_dllmain_before_initialize_c`
- size: `7`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800014a8`

## callees

- `0x180001a7c`

## pseudocode

```c
__int64 _scrt_dllmain_before_initialize_c()
{
  return _scrt_initialize_onexit_tables(0);
}

```

## disassembly

```asm
0x18000193c  xor     ecx, ecx
0x18000193e  jmp     __scrt_initialize_onexit_tables
```
