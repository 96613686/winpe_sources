# __scrt_is_ucrt_dll_in_use

- ea: `0x180004550`
- end: `0x18000455c`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180003984`
- `0x1800039c4`
- `0x180003a5c`
- `0x180003aac`
- `0x180003b40`
- `0x180003c74`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180004550  xor     eax, eax
0x180004552  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180004558  setnz   al
0x18000455b  retn
```
