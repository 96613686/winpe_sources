# __scrt_initialize_type_info(void)

- ea: `0x140001140`
- end: `0x14000114e`
- name: `?__scrt_initialize_type_info@@YAXXZ`
- size: `14`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x140001d40`

## import_xrefs

- `KERNEL32!InitializeSListHead` at `0x140001147`

## pseudocode

```c
void __scrt_initialize_type_info(void)
{
  InitializeSListHead((PSLIST_HEADER)&__type_info_root_node);
}

```

## disassembly

```asm
0x140001140  lea     rcx, ?__type_info_root_node@@3U__type_info_node@@A; __type_info_node __type_info_root_node
0x140001147  jmp     cs:__imp_InitializeSListHead
```
