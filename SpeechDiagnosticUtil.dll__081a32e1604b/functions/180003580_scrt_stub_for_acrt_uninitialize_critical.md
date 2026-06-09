# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180003580`
- end: `0x180003583`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x1800029c0`
- `0x1800029f0`
- `0x180002a94`
- `0x180002ab0`
- `0x180002c50`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180003580  mov     al, 1
0x180003582  retn
```
