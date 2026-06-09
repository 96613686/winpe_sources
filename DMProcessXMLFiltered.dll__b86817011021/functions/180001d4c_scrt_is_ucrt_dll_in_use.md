# __scrt_is_ucrt_dll_in_use

- ea: `0x180001d4c`
- end: `0x180001d58`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001658`
- `0x180001698`
- `0x180001730`
- `0x180001780`
- `0x180001814`
- `0x180001948`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180001d4c  xor     eax, eax
0x180001d4e  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180001d54  setnz   al
0x180001d57  retn
```
