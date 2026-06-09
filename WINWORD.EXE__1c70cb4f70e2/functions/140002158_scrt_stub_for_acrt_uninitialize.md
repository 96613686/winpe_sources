# __scrt_stub_for_acrt_uninitialize

- ea: `0x140002158`
- end: `0x14000215b`
- name: `__scrt_stub_for_acrt_uninitialize`
- size: `3`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1400017f0`
- `0x140001abc`
- `0x140001c40`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize()
{
  return 1;
}

```

## disassembly

```asm
0x140002158  mov     al, 1
0x14000215a  retn
```
