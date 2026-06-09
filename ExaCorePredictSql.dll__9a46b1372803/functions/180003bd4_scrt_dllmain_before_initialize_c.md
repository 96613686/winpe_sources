# __scrt_dllmain_before_initialize_c

- ea: `0x180003bd4`
- end: `0x180003be9`
- name: `__scrt_dllmain_before_initialize_c`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180003fd0`

## callees

- `0x180003d20`

## pseudocode

```c
bool _scrt_dllmain_before_initialize_c()
{
  return (unsigned __int8)_scrt_initialize_onexit_tables(0) != 0;
}

```

## disassembly

```asm
0x180003bd4  sub     rsp, 28h
0x180003bd8  xor     ecx, ecx
0x180003bda  call    __scrt_initialize_onexit_tables
0x180003bdf  test    al, al
0x180003be1  setnz   al
0x180003be4  add     rsp, 28h
0x180003be8  retn
```
