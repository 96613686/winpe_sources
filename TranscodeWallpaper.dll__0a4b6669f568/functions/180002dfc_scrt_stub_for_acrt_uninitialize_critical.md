# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180002dfc`
- end: `0x180002dff`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: `char()`
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x180002220`
- `0x180002250`
- `0x1800022f4`
- `0x180002310`
- `0x1800024b0`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180002dfc  mov     al, 1
0x180002dfe  retn
```
