# __scrt_stub_for_acrt_uninitialize_critical

- ea: `0x180001eb8`
- end: `0x180001ebb`
- name: `__scrt_stub_for_acrt_uninitialize_critical`
- size: `3`
- prototype: ``
- caller_count: `5`
- callee_count: `0`
- tags: ``

## callers

- `0x18000162c`
- `0x18000165c`
- `0x180001700`
- `0x18000171c`
- `0x1800018bc`

## pseudocode

```c
char _scrt_stub_for_acrt_uninitialize_critical()
{
  return 1;
}

```

## disassembly

```asm
0x180001eb8  mov     al, 1
0x180001eba  retn
```
