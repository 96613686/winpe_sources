# __scrt_is_ucrt_dll_in_use

- ea: `0x14005b824`
- end: `0x14005b830`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x14005a9d4`
- `0x14005aa4c`
- `0x14005ab70`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return dword_14007608C != 0;
}

```

## disassembly

```asm
0x14005b824  xor     eax, eax
0x14005b826  cmp     cs:dword_14007608C, eax
0x14005b82c  setnz   al
0x14005b82f  retn
```
