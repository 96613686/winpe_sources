# __scrt_is_ucrt_dll_in_use

- ea: `0x14001cd40`
- end: `0x14001cd4c`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x14001c940`
- `0x14001c9c8`
- `0x14001caec`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return dword_1400D8048 != 0;
}

```

## disassembly

```asm
0x14001cd40  xor     eax, eax
0x14001cd42  cmp     cs:dword_1400D8048, eax
0x14001cd48  setnz   al
0x14001cd4b  retn
```
