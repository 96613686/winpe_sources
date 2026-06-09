# __scrt_dllmain_before_initialize_c

- ea: `0x18000ee5c`
- end: `0x18000ee71`
- name: `__scrt_dllmain_before_initialize_c`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000f238`

## callees

- `0x18000efc0`

## pseudocode

```c
bool _scrt_dllmain_before_initialize_c()
{
  return (unsigned __int8)_scrt_initialize_onexit_tables(0) != 0;
}

```

## disassembly

```asm
0x18000ee5c  sub     rsp, 28h
0x18000ee60  xor     ecx, ecx
0x18000ee62  call    __scrt_initialize_onexit_tables
0x18000ee67  test    al, al
0x18000ee69  setnz   al
0x18000ee6c  add     rsp, 28h
0x18000ee70  retn
```
