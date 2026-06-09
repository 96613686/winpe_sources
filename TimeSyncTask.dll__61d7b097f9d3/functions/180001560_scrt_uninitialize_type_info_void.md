# __scrt_uninitialize_type_info(void)

- ea: `0x180001560`
- end: `0x18000156c`
- name: `?__scrt_uninitialize_type_info@@YAXXZ`
- size: `12`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180001248`

## callees

- `0x180001c9a`

## pseudocode

```c
void __scrt_uninitialize_type_info(void)
{
  _std_type_info_destroy_list(&__type_info_root_node);
}

```

## disassembly

```asm
0x180001560  lea     rcx, ?__type_info_root_node@@3U__type_info_node@@A; __type_info_node __type_info_root_node
0x180001567  jmp     __std_type_info_destroy_list
```
