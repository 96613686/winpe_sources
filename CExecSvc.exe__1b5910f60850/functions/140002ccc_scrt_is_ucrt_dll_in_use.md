# __scrt_is_ucrt_dll_in_use

- ea: `0x140002ccc`
- end: `0x140002cd8`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140002448`
- `0x1400024c8`
- `0x1400025fc`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x140002ccc  xor     eax, eax
0x140002cce  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x140002cd4  setnz   al
0x140002cd7  retn
```
