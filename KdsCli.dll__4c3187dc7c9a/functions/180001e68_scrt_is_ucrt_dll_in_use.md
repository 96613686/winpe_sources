# __scrt_is_ucrt_dll_in_use

- ea: `0x180001e68`
- end: `0x180001e74`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000175c`
- `0x18000179c`
- `0x180001834`
- `0x180001884`
- `0x180001918`
- `0x180001a4c`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180001e68  xor     eax, eax
0x180001e6a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180001e70  setnz   al
0x180001e73  retn
```
