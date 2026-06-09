# __scrt_is_ucrt_dll_in_use

- ea: `0x140003a5c`
- end: `0x140003a68`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1400031d4`
- `0x140003254`
- `0x140003388`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x140003a5c  xor     eax, eax
0x140003a5e  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x140003a64  setnz   al
0x140003a67  retn
```
