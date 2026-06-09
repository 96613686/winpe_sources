# __std_init_once_link_alternate_names_and_abort

- ea: `0x180001c18`
- end: `0x180001c23`
- name: `__std_init_once_link_alternate_names_and_abort`
- size: `11`
- prototype: `void __noreturn()`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180012e78`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180001c1c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180001c1c`

## pseudocode

```c
void __noreturn _std_init_once_link_alternate_names_and_abort()
{
  abort();
}

```

## disassembly

```asm
0x180001c18  sub     rsp, 28h
0x180001c1c  call    cs:__imp_abort
```
