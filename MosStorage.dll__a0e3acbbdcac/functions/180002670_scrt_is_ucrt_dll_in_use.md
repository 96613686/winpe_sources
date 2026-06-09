# __scrt_is_ucrt_dll_in_use

- ea: `0x180002670`
- end: `0x18000267c`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001ca4`
- `0x180001ce4`
- `0x180001d7c`
- `0x180001dcc`
- `0x180001e60`
- `0x180001f94`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180002670  xor     eax, eax
0x180002672  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180002678  setnz   al
0x18000267b  retn
```
