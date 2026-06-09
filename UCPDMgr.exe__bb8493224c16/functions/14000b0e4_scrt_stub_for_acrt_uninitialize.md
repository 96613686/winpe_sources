# __scrt_stub_for_acrt_uninitialize

- ea: `0x14000b0e4`
- end: `0x14000b0e7`
- name: `__scrt_stub_for_acrt_uninitialize`
- size: `3`
- prototype: `char()`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x14000a3f4`
- `0x14000a594`
- `0x14000a660`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize()
{
  return 1;
}

```

## disassembly

```asm
0x14000b0e4  mov     al, 1
0x14000b0e6  retn
```
