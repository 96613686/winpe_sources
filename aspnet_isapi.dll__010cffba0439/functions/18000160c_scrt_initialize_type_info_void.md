# __scrt_initialize_type_info(void)

- ea: `0x18000160c`
- end: `0x18000161a`
- name: `?__scrt_initialize_type_info@@YAXXZ`
- size: `14`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `0`
- tags: ``

## callers

- `0x1800011a0`

## import_xrefs

- `KERNEL32!InitializeSListHead` at `0x180001613`

## pseudocode

```c
void __scrt_initialize_type_info(void)
{
  InitializeSListHead((PSLIST_HEADER)&__type_info_root_node);
}

```

## disassembly

```asm
0x18000160c  lea     rcx, ?__type_info_root_node@@3U__type_info_node@@A
0x180001613  jmp     cs:__imp_InitializeSListHead
```
