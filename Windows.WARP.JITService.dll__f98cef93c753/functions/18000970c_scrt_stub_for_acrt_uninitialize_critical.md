# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x18000970c`
- end: `0x18000970f`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180008b30`
- `0x180008b60`
- `0x180008c04`
- `0x180008c20`
- `0x180008dc0`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x18000970c  mov     al, 1
0x18000970e  retn
```
