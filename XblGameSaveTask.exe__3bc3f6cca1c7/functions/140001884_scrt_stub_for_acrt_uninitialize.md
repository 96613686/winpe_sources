# __scrt_stub_for_acrt_uninitialize

- ea: `0x140001884`
- end: `0x140001887`
- name: `__scrt_stub_for_acrt_uninitialize`
- size: `3`
- prototype: `char()`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1400011d0`
- `0x1400014e4`
- `0x140001684`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize()
{
  return 1;
}

```

## disassembly

```asm
0x140001884  mov     al, 1
0x140001886  retn
```
