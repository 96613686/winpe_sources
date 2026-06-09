# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180001fcc`
- end: `0x180001fcf`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001608`
- `0x180001638`
- `0x1800016dc`
- `0x1800016f8`
- `0x180001898`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180001fcc  mov     al, 1
0x180001fce  retn
```
