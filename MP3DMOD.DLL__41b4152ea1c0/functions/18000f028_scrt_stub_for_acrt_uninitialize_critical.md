# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x18000f028`
- end: `0x18000f02b`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x18000e8d4`
- `0x18000e904`
- `0x18000e9a8`
- `0x18000e9c4`
- `0x18000eb64`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x18000f028  mov     al, 1
0x18000f02a  retn
```
