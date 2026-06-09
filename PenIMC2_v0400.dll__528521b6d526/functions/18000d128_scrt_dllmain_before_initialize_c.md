# __scrt_dllmain_before_initialize_c

- ea: `0x18000d128`
- end: `0x18000d13d`
- name: `__scrt_dllmain_before_initialize_c`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x18000d780`

## callees

- `0x18000d270`

## pseudocode

```c
bool _scrt_dllmain_before_initialize_c()
{
  return (unsigned __int8)_scrt_initialize_onexit_tables(0) != 0;
}

```

## disassembly

```asm
0x18000d128  sub     rsp, 28h
0x18000d12c  xor     ecx, ecx
0x18000d12e  call    __scrt_initialize_onexit_tables
0x18000d133  test    al, al
0x18000d135  setnz   al
0x18000d138  add     rsp, 28h
0x18000d13c  retn
```
