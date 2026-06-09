# __scrt_stub_for_acrt_uninitialize

- ea: `0x140001890`
- end: `0x140001893`
- name: `__scrt_stub_for_acrt_uninitialize`
- size: `3`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: ``

## callers

- `0x1400011c0`
- `0x14000152c`
- `0x1400016cc`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize()
{
  return 1;
}

```

## disassembly

```asm
0x140001890  mov     al, 1
0x140001892  retn
```
