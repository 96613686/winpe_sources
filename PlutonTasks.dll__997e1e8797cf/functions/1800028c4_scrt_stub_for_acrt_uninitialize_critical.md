# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x1800028c4`
- end: `0x1800028c7`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001ef4`
- `0x180001f24`
- `0x180001fc8`
- `0x180001fe4`
- `0x180002184`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x1800028c4  mov     al, 1
0x1800028c6  retn
```
