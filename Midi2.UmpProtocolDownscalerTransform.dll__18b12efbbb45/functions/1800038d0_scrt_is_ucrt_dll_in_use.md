# __scrt_is_ucrt_dll_in_use

- ea: `0x1800038d0`
- end: `0x1800038dc`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180002fd4`
- `0x180003014`
- `0x1800030ac`
- `0x1800030fc`
- `0x180003190`
- `0x1800032c4`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x1800038d0  xor     eax, eax
0x1800038d2  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x1800038d8  setnz   al
0x1800038db  retn
```
