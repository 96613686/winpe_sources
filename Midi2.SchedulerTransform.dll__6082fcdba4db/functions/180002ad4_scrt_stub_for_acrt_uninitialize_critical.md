# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180002ad4`
- end: `0x180002ad7`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180002120`
- `0x180002150`
- `0x1800021f4`
- `0x180002210`
- `0x1800023b0`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180002ad4  mov     al, 1
0x180002ad6  retn
```
