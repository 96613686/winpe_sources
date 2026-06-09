# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180002344`
- end: `0x180002347`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800018a8`
- `0x1800018d8`
- `0x18000197c`
- `0x180001998`
- `0x180001b38`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180002344  mov     al, 1
0x180002346  retn
```
