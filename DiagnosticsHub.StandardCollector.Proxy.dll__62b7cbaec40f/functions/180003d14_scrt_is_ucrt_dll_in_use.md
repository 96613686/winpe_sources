# __scrt_is_ucrt_dll_in_use

- ea: `0x180003d14`
- end: `0x180003d20`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180003178`
- `0x1800031b4`
- `0x180003240`
- `0x1800032a0`
- `0x180003320`
- `0x180003444`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180003d14  xor     eax, eax
0x180003d16  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180003d1c  setnz   al
0x180003d1f  retn
```
