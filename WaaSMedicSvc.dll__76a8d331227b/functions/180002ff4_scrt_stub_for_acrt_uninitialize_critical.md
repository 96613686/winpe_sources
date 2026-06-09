# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180002ff4`
- end: `0x180002ff7`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800022b0`
- `0x1800022e0`
- `0x180002384`
- `0x1800023a0`
- `0x180002540`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180002ff4  mov     al, 1
0x180002ff6  retn
```
