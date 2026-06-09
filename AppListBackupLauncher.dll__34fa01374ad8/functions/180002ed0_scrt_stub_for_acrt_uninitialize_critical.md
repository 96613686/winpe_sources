# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180002ed0`
- end: `0x180002ed3`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180002418`
- `0x180002448`
- `0x1800024ec`
- `0x180002508`
- `0x1800026a8`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180002ed0  mov     al, 1
0x180002ed2  retn
```
