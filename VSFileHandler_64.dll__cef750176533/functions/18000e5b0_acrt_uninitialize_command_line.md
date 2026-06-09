# __acrt_uninitialize_command_line

- ea: `0x18000e5b0`
- end: `0x18000e5b3`
- name: `__acrt_uninitialize_command_line`
- size: `3`
- prototype: `char()`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
char _acrt_uninitialize_command_line()
{
  return 1;
}

```

## disassembly

```asm
0x18000e5b0  mov     al, 1
0x18000e5b2  retn
```
