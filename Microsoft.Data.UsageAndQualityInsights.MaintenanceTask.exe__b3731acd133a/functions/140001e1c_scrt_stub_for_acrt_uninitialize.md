# __scrt_stub_for_acrt_uninitialize

- ea: `0x140001e1c`
- end: `0x140001e1f`
- name: `__scrt_stub_for_acrt_uninitialize`
- size: `3`
- prototype: `char()`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140001450`
- `0x140001754`
- `0x1400018f4`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize()
{
  return 1;
}

```

## disassembly

```asm
0x140001e1c  mov     al, 1
0x140001e1e  retn
```
