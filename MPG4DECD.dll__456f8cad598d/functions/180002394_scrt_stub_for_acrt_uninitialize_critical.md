# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180002394`
- end: `0x180002397`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001a68`
- `0x180001a98`
- `0x180001b3c`
- `0x180001b58`
- `0x180001cf8`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180002394  mov     al, 1
0x180002396  retn
```
