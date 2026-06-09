# __scrt_is_ucrt_dll_in_use

- ea: `0x180002730`
- end: `0x18000273c`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001f3c`
- `0x180001f7c`
- `0x180002014`
- `0x180002064`
- `0x1800020f8`
- `0x18000222c`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180002730  xor     eax, eax
0x180002732  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180002738  setnz   al
0x18000273b  retn
```
