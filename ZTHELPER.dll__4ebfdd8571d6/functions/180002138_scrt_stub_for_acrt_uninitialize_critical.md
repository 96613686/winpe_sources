# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180002138`
- end: `0x18000213b`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800015b0`
- `0x1800015e0`
- `0x180001684`
- `0x1800016a0`
- `0x180001840`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180002138  mov     al, 1
0x18000213a  retn
```
