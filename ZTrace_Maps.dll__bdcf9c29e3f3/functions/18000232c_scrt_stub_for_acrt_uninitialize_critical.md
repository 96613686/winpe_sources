# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x18000232c`
- end: `0x18000232f`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001824`
- `0x180001854`
- `0x1800018f8`
- `0x180001914`
- `0x180001ab4`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x18000232c  mov     al, 1
0x18000232e  retn
```
