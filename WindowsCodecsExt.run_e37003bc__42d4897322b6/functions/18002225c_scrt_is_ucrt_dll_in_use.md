# __scrt_is_ucrt_dll_in_use

- ea: `0x18002225c`
- end: `0x180022268`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180021b68`
- `0x180021ba8`
- `0x180021c40`
- `0x180021c90`
- `0x180021d24`
- `0x180021e58`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x18002225c  xor     eax, eax
0x18002225e  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180022264  setnz   al
0x180022267  retn
```
