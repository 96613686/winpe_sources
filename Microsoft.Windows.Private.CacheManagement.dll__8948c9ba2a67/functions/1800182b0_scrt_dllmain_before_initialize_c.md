# __scrt_dllmain_before_initialize_c

- ea: `0x1800182b0`
- end: `0x1800182c5`
- name: `__scrt_dllmain_before_initialize_c`
- size: `21`
- prototype: `bool()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180018620`

## callees

- `0x1800183e8`

## pseudocode

```c
bool _scrt_dllmain_before_initialize_c()
{
  return (unsigned __int8)_scrt_initialize_onexit_tables(0) != 0;
}

```

## disassembly

```asm
0x1800182b0  sub     rsp, 28h
0x1800182b4  xor     ecx, ecx
0x1800182b6  call    __scrt_initialize_onexit_tables
0x1800182bb  test    al, al
0x1800182bd  setnz   al
0x1800182c0  add     rsp, 28h
0x1800182c4  retn
```
