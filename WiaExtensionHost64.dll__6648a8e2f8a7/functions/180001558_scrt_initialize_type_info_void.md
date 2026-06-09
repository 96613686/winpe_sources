# __scrt_initialize_type_info(void)

- ea: `0x180001558`
- end: `0x180001566`
- name: `?__scrt_initialize_type_info@@YAXXZ`
- size: `14`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x180001128`

## import_xrefs

- `KERNEL32!InitializeSListHead` at `0x18000155f`

## pseudocode

```c
void __scrt_initialize_type_info(void)
{
  InitializeSListHead((PSLIST_HEADER)&__type_info_root_node);
}

```

## disassembly

```asm
0x180001558  lea     rcx, ?__type_info_root_node@@3U__type_info_node@@A; __type_info_node __type_info_root_node
0x18000155f  jmp     cs:__imp_InitializeSListHead
```
