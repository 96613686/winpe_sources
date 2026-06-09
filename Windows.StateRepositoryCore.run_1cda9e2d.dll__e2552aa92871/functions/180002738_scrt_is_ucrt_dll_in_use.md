# __scrt_is_ucrt_dll_in_use

- ea: `0x180002738`
- end: `0x180002744`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001ef4`
- `0x180001f34`
- `0x180001fcc`
- `0x18000201c`
- `0x1800020b0`
- `0x1800021e4`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180002738  xor     eax, eax
0x18000273a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180002740  setnz   al
0x180002743  retn
```
