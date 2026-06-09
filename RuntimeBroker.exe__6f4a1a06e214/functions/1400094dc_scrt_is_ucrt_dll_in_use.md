# __scrt_is_ucrt_dll_in_use

- ea: `0x1400094dc`
- end: `0x1400094e8`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140008cc8`
- `0x140008d48`
- `0x140008e7c`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x1400094dc  xor     eax, eax
0x1400094de  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x1400094e4  setnz   al
0x1400094e7  retn
```
