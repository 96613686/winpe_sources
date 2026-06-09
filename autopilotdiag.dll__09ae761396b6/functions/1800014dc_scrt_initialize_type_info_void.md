# __scrt_initialize_type_info(void)

- ea: `0x1800014dc`
- end: `0x1800014ea`
- name: `?__scrt_initialize_type_info@@YAXXZ`
- size: `14`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800010e8`

## import_xrefs

- `api-ms-win-core-interlocked-l1-1-0!InitializeSListHead` at `0x1800014e3`

## pseudocode

```c
void __scrt_initialize_type_info(void)
{
  InitializeSListHead((PSLIST_HEADER)&__type_info_root_node);
}

```

## disassembly

```asm
0x1800014dc  lea     rcx, ?__type_info_root_node@@3U__type_info_node@@A; __type_info_node __type_info_root_node
0x1800014e3  jmp     cs:__imp_InitializeSListHead
```
