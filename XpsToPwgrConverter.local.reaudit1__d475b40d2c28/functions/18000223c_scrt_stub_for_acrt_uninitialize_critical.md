# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x18000223c`
- end: `0x18000223f`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001810`
- `0x180001840`
- `0x1800018e4`
- `0x180001900`
- `0x180001aa0`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x18000223c  mov     al, 1
0x18000223e  retn
```
