# __scrt_initialize_type_info(void)

- ea: `0x180001560`
- end: `0x18000156e`
- name: `?__scrt_initialize_type_info@@YAXXZ`
- size: `14`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001168`

## import_xrefs

- `api-ms-win-core-interlocked-l1-1-0!InitializeSListHead` at `0x180001567`

## pseudocode

```c
void __scrt_initialize_type_info(void)
{
  InitializeSListHead((PSLIST_HEADER)&__type_info_root_node);
}

```

## disassembly

```asm
0x180001560  lea     rcx, ?__type_info_root_node@@3U__type_info_node@@A; __type_info_node __type_info_root_node
0x180001567  jmp     cs:__imp_InitializeSListHead
```
