# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x18000225c`
- end: `0x18000225f`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001750`
- `0x180001780`
- `0x180001824`
- `0x180001840`
- `0x1800019e0`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x18000225c  mov     al, 1
0x18000225e  retn
```
