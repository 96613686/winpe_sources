# __scrt_dllmain_before_initialize_c

- ea: `0x100468fac`
- end: `0x100468fc1`
- name: `__scrt_dllmain_before_initialize_c`
- size: `21`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x100468c0c`

## callees

- `0x100469120`

## pseudocode

```c
bool _scrt_dllmain_before_initialize_c()
{
  return (unsigned __int8)_scrt_initialize_onexit_tables(0) != 0;
}

```

## disassembly

```asm
0x100468fac  sub     rsp, 28h
0x100468fb0  xor     ecx, ecx
0x100468fb2  call    __scrt_initialize_onexit_tables
0x100468fb7  test    al, al
0x100468fb9  setnz   al
0x100468fbc  add     rsp, 28h
0x100468fc0  retn
```
