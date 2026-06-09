# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x18000b834`
- end: `0x18000b837`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180007378`
- `0x1800073a0`
- `0x180007448`
- `0x18000745c`
- `0x1800075e0`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x18000b834  mov     al, 1
0x18000b836  retn
```
