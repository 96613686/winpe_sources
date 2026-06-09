# __scrt_stub_for_acrt_uninitialize

- ea: `0x140001988`
- end: `0x14000198b`
- name: `__scrt_stub_for_acrt_uninitialize`
- size: `3`
- prototype: `char()`
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x140001360`
- `0x140001664`
- `0x140001804`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize()
{
  return 1;
}

```

## disassembly

```asm
0x140001988  mov     al, 1
0x14000198a  retn
```
