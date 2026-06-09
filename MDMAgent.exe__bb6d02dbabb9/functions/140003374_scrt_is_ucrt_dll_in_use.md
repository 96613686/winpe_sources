# __scrt_is_ucrt_dll_in_use

- ea: `0x140003374`
- end: `0x140003380`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140002b04`
- `0x140002b84`
- `0x140002cb8`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x140003374  xor     eax, eax
0x140003376  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x14000337c  setnz   al
0x14000337f  retn
```
