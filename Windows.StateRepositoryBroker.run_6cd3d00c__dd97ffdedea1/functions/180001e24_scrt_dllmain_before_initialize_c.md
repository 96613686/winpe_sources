# __scrt_dllmain_before_initialize_c

- ea: `0x180001e24`
- end: `0x180001e2b`
- name: `__scrt_dllmain_before_initialize_c`
- size: `7`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180001a48`

## callees

- `0x180001f64`

## pseudocode

```c
__int64 _scrt_dllmain_before_initialize_c()
{
  return _scrt_initialize_onexit_tables(0);
}

```

## disassembly

```asm
0x180001e24  xor     ecx, ecx
0x180001e26  jmp     __scrt_initialize_onexit_tables
```
