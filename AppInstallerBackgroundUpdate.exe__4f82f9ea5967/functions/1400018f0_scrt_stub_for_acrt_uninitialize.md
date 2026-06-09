# __scrt_stub_for_acrt_uninitialize

- ea: `0x1400018f0`
- end: `0x1400018f3`
- name: `__scrt_stub_for_acrt_uninitialize`
- size: `3`
- prototype: `char()`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140001290`
- `0x140001594`
- `0x140001734`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize()
{
  return 1;
}

```

## disassembly

```asm
0x1400018f0  mov     al, 1
0x1400018f2  retn
```
