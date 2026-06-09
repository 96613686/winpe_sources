# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180003088`
- end: `0x18000308b`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180002590`
- `0x1800025c0`
- `0x180002664`
- `0x180002680`
- `0x180002820`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180003088  mov     al, 1
0x18000308a  retn
```
