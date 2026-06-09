# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x1800022b0`
- end: `0x1800022b3`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001898`
- `0x1800018c8`
- `0x18000196c`
- `0x180001988`
- `0x180001b28`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x1800022b0  mov     al, 1
0x1800022b2  retn
```
