# __std_init_once_link_alternate_names_and_abort

- ea: `0x180002168`
- end: `0x180002173`
- name: `__std_init_once_link_alternate_names_and_abort`
- size: `11`
- prototype: `void __noreturn()`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x18000bff4`
- `0x18000c01c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000216c`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x18000216c`

## pseudocode

```c
void __noreturn _std_init_once_link_alternate_names_and_abort()
{
  abort();
}

```

## disassembly

```asm
0x180002168  sub     rsp, 28h
0x18000216c  call    cs:__imp_abort
```
