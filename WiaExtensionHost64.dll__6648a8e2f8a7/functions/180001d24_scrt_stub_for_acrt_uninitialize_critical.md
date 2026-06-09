# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180001d24`
- end: `0x180001d27`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001630`
- `0x180001660`
- `0x180001704`
- `0x180001720`
- `0x1800018c0`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180001d24  mov     al, 1
0x180001d26  retn
```
