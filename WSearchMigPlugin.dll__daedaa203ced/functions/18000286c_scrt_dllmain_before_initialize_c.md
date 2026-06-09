# __scrt_dllmain_before_initialize_c

- ea: `0x18000286c`
- end: `0x180002873`
- name: `__scrt_dllmain_before_initialize_c`
- size: `7`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800023c8`

## callees

- `0x1800029ac`

## pseudocode

```c
__int64 _scrt_dllmain_before_initialize_c()
{
  return _scrt_initialize_onexit_tables(0);
}

```

## disassembly

```asm
0x18000286c  xor     ecx, ecx
0x18000286e  jmp     __scrt_initialize_onexit_tables
```
