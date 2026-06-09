# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x1800041e8`
- end: `0x1800041eb`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800034f0`
- `0x180003520`
- `0x1800035c4`
- `0x1800035e0`
- `0x180003780`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x1800041e8  mov     al, 1
0x1800041ea  retn
```
