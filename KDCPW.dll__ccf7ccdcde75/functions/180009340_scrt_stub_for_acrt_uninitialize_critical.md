# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180009340`
- end: `0x180009343`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800016e0`
- `0x180001710`
- `0x1800017b4`
- `0x1800017d0`
- `0x180001970`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180009340  mov     al, 1
0x180009342  retn
```
