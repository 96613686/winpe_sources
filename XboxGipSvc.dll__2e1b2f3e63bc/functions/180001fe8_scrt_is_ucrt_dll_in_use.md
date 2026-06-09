# __scrt_is_ucrt_dll_in_use

- ea: `0x180001fe8`
- end: `0x180001ff4`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800017c0`
- `0x180001800`
- `0x180001898`
- `0x1800018e8`
- `0x18000197c`
- `0x180001ab0`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180001fe8  xor     eax, eax
0x180001fea  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180001ff0  setnz   al
0x180001ff3  retn
```
