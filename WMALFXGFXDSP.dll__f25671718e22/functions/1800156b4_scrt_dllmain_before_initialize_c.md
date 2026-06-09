# __scrt_dllmain_before_initialize_c

- ea: `0x1800156b4`
- end: `0x1800156bb`
- name: `__scrt_dllmain_before_initialize_c`
- size: `7`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180015218`

## callees

- `0x1800157f4`

## pseudocode

```c
__int64 _scrt_dllmain_before_initialize_c()
{
  return _scrt_initialize_onexit_tables(0);
}

```

## disassembly

```asm
0x1800156b4  xor     ecx, ecx
0x1800156b6  jmp     __scrt_initialize_onexit_tables
```
