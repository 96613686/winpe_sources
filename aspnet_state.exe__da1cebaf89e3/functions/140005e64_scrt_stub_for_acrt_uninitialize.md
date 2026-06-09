# __scrt_stub_for_acrt_uninitialize

- ea: `0x140005e64`
- end: `0x140005e67`
- name: `__scrt_stub_for_acrt_uninitialize`
- size: `3`
- prototype: `char()`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140005810`
- `0x140005b7c`
- `0x140005d10`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize()
{
  return 1;
}

```

## disassembly

```asm
0x140005e64  mov     al, 1
0x140005e66  retn
```
