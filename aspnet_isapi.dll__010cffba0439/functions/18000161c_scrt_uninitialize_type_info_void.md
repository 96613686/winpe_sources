# __scrt_uninitialize_type_info(void)

- ea: `0x18000161c`
- end: `0x180001628`
- name: `?__scrt_uninitialize_type_info@@YAXXZ`
- size: `12`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800012b8`

## callees

- `0x180001ea6`

## pseudocode

```c
void __scrt_uninitialize_type_info(void)
{
  _std_type_info_destroy_list_0(&__type_info_root_node);
}

```

## disassembly

```asm
0x18000161c  lea     rcx, ?__type_info_root_node@@3U__type_info_node@@A
0x180001623  jmp     __std_type_info_destroy_list_0
```
