# __scrt_stub_for_acrt_uninitialize

- ea: `0x140001d34`
- end: `0x140001d37`
- name: `__scrt_stub_for_acrt_uninitialize`
- size: `3`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140001cf8`
- `0x140001d40`
- `0x1400024c0`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize()
{
  return 1;
}

```

## disassembly

```asm
0x140001d34  mov     al, 1
0x140001d36  retn
```
