# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x1800037e0`
- end: `0x1800037e3`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180002c58`
- `0x180002c88`
- `0x180002d2c`
- `0x180002d48`
- `0x180002ee8`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x1800037e0  mov     al, 1
0x1800037e2  retn
```
