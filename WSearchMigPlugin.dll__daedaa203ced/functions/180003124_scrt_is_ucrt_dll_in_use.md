# __scrt_is_ucrt_dll_in_use

- ea: `0x180003124`
- end: `0x180003130`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800027f0`
- `0x180002830`
- `0x1800028c8`
- `0x180002918`
- `0x1800029ac`
- `0x180002ae0`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180003124  xor     eax, eax
0x180003126  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x18000312c  setnz   al
0x18000312f  retn
```
