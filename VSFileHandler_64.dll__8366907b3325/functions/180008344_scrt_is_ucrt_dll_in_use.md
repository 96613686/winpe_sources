# __scrt_is_ucrt_dll_in_use

- ea: `0x180008344`
- end: `0x180008350`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180007720`
- `0x18000775c`
- `0x1800077e8`
- `0x180007848`
- `0x1800078c8`
- `0x1800079ec`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180008344  xor     eax, eax
0x180008346  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x18000834c  setnz   al
0x18000834f  retn
```
