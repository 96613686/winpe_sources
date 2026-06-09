# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180001e20`
- end: `0x180001e23`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800015b8`
- `0x1800015e8`
- `0x18000168c`
- `0x1800016a8`
- `0x180001848`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180001e20  mov     al, 1
0x180001e22  retn
```
