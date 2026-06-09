# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x1800037ec`
- end: `0x1800037ef`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180002c70`
- `0x180002ca0`
- `0x180002d44`
- `0x180002d60`
- `0x180002f00`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x1800037ec  mov     al, 1
0x1800037ee  retn
```
