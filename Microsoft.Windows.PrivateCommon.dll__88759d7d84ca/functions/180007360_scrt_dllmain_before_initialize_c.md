# __scrt_dllmain_before_initialize_c

- ea: `0x180007360`
- end: `0x180007375`
- name: `__scrt_dllmain_before_initialize_c`
- size: `21`
- prototype: `bool()`
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800076f0`

## callees

- `0x180007498`

## pseudocode

```c
bool _scrt_dllmain_before_initialize_c()
{
  return (unsigned __int8)_scrt_initialize_onexit_tables(0) != 0;
}

```

## disassembly

```asm
0x180007360  sub     rsp, 28h
0x180007364  xor     ecx, ecx
0x180007366  call    __scrt_initialize_onexit_tables
0x18000736b  test    al, al
0x18000736d  setnz   al
0x180007370  add     rsp, 28h
0x180007374  retn
```
