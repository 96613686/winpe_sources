# __scrt_stub_for_acrt_uninitialize

- ea: `0x140002058`
- end: `0x14000205b`
- name: `__scrt_stub_for_acrt_uninitialize`
- size: `3`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140001a30`
- `0x140001d34`
- `0x140001ed4`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize()
{
  return 1;
}

```

## disassembly

```asm
0x140002058  mov     al, 1
0x14000205a  retn
```
