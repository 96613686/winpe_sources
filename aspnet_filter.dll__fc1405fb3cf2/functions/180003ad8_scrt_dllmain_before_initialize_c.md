# __scrt_dllmain_before_initialize_c

- ea: `0x180003ad8`
- end: `0x180003aed`
- name: `__scrt_dllmain_before_initialize_c`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x1800032e0`

## callees

- `0x180003c20`

## pseudocode

```c
bool _scrt_dllmain_before_initialize_c()
{
  return (unsigned __int8)_scrt_initialize_onexit_tables(0) != 0;
}

```

## disassembly

```asm
0x180003ad8  sub     rsp, 28h
0x180003adc  xor     ecx, ecx
0x180003ade  call    __scrt_initialize_onexit_tables
0x180003ae3  test    al, al
0x180003ae5  setnz   al
0x180003ae8  add     rsp, 28h
0x180003aec  retn
```
