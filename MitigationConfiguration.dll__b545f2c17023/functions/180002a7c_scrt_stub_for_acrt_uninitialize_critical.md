# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180002a7c`
- end: `0x180002a7f`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001cf4`
- `0x180001d24`
- `0x180001dc8`
- `0x180001de4`
- `0x180001f84`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180002a7c  mov     al, 1
0x180002a7e  retn
```
