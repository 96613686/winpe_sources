# __scrt_is_ucrt_dll_in_use

- ea: `0x180004670`
- end: `0x18000467c`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180003b64`
- `0x180003ba0`
- `0x180003c2c`
- `0x180003c90`
- `0x180003d20`
- `0x180003e88`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180004670  xor     eax, eax
0x180004672  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180004678  setnz   al
0x18000467b  retn
```
