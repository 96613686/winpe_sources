# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x18002b5d8`
- end: `0x18002b5db`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x18002ac84`
- `0x18002acb4`
- `0x18002ad58`
- `0x18002ad74`
- `0x18002af14`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x18002b5d8  mov     al, 1
0x18002b5da  retn
```
