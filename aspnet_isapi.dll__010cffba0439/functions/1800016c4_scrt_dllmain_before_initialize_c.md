# __scrt_dllmain_before_initialize_c

- ea: `0x1800016c4`
- end: `0x1800016d9`
- name: `__scrt_dllmain_before_initialize_c`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800011a0`

## callees

- `0x18000180c`

## pseudocode

```c
bool _scrt_dllmain_before_initialize_c()
{
  return (unsigned __int8)_scrt_initialize_onexit_tables(0) != 0;
}

```

## disassembly

```asm
0x1800016c4  sub     rsp, 28h
0x1800016c8  xor     ecx, ecx
0x1800016ca  call    __scrt_initialize_onexit_tables
0x1800016cf  test    al, al
0x1800016d1  setnz   al
0x1800016d4  add     rsp, 28h
0x1800016d8  retn
```
