# __scrt_dllmain_before_initialize_c

- ea: `0x18001078c`
- end: `0x180010793`
- name: `__scrt_dllmain_before_initialize_c`
- size: `7`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800103a8`

## callees

- `0x1800108cc`

## pseudocode

```c
__int64 _scrt_dllmain_before_initialize_c()
{
  return _scrt_initialize_onexit_tables(0);
}

```

## disassembly

```asm
0x18001078c  xor     ecx, ecx
0x18001078e  jmp     __scrt_initialize_onexit_tables
```
