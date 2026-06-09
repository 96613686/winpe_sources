# __scrt_stub_for_acrt_uninitialize

- ea: `0x1400016dc`
- end: `0x1400016df`
- name: `__scrt_stub_for_acrt_uninitialize`
- size: `3`
- prototype: `char()`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140001090`
- `0x1400013c4`
- `0x140001564`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize()
{
  return 1;
}

```

## disassembly

```asm
0x1400016dc  mov     al, 1
0x1400016de  retn
```
