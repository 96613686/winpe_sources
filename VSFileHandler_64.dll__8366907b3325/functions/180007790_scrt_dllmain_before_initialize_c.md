# __scrt_dllmain_before_initialize_c

- ea: `0x180007790`
- end: `0x1800077a5`
- name: `__scrt_dllmain_before_initialize_c`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800073e0`

## callees

- `0x1800078c8`

## pseudocode

```c
bool _scrt_dllmain_before_initialize_c()
{
  return (unsigned __int8)_scrt_initialize_onexit_tables(0) != 0;
}

```

## disassembly

```asm
0x180007790  sub     rsp, 28h
0x180007794  xor     ecx, ecx
0x180007796  call    __scrt_initialize_onexit_tables
0x18000779b  test    al, al
0x18000779d  setnz   al
0x1800077a0  add     rsp, 28h
0x1800077a4  retn
```
