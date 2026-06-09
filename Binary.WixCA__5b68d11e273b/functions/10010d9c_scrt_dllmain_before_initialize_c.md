# ___scrt_dllmain_before_initialize_c

- ea: `0x10010d9c`
- end: `0x10010daa`
- name: `___scrt_dllmain_before_initialize_c`
- size: `14`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x10010784`

## callees

- `0x10010e73`

## pseudocode

```c
bool __scrt_dllmain_before_initialize_c()
{
  return (unsigned __int8)__scrt_initialize_onexit_tables(0) != 0;
}

```

## disassembly

```asm
0x10010d9c  push    0
0x10010d9e  call    ___scrt_initialize_onexit_tables
0x10010da3  test    al, al
0x10010da5  pop     ecx
0x10010da6  setnz   al
0x10010da9  retn
```
