# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180001c60`
- end: `0x180001c63`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800015b4`
- `0x1800015e4`
- `0x180001688`
- `0x1800016a4`
- `0x180001844`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180001c60  mov     al, 1
0x180001c62  retn
```
