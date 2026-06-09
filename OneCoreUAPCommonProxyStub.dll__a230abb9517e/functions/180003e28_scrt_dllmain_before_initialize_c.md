# __scrt_dllmain_before_initialize_c

- ea: `0x180003e28`
- end: `0x180003e2f`
- name: `__scrt_dllmain_before_initialize_c`
- size: `7`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180003968`

## callees

- `0x180003f68`

## pseudocode

```c
__int64 _scrt_dllmain_before_initialize_c()
{
  return _scrt_initialize_onexit_tables(0);
}

```

## disassembly

```asm
0x180003e28  xor     ecx, ecx
0x180003e2a  jmp     __scrt_initialize_onexit_tables
```
