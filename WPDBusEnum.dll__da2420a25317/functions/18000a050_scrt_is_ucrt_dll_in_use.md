# __scrt_is_ucrt_dll_in_use

- ea: `0x18000a050`
- end: `0x18000a05c`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x1800097f4`
- `0x180009834`
- `0x1800098cc`
- `0x18000991c`
- `0x1800099b0`
- `0x180009ae4`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x18000a050  xor     eax, eax
0x18000a052  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x18000a058  setnz   al
0x18000a05b  retn
```
