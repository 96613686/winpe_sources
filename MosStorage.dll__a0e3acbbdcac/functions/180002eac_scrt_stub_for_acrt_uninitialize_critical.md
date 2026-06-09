# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180002eac`
- end: `0x180002eaf`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001d30`
- `0x180001d60`
- `0x180001e04`
- `0x180001e20`
- `0x180001fc0`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180002eac  mov     al, 1
0x180002eae  retn
```
