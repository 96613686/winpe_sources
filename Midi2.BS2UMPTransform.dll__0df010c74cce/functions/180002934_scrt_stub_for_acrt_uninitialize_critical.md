# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180002934`
- end: `0x180002937`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180001f80`
- `0x180001fb0`
- `0x180002054`
- `0x180002070`
- `0x180002210`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180002934  mov     al, 1
0x180002936  retn
```
