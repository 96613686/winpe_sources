# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180002cbc`
- end: `0x180002cbf`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001e34`
- `0x180001e64`
- `0x180001f08`
- `0x180001f24`
- `0x1800020c4`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180002cbc  mov     al, 1
0x180002cbe  retn
```
