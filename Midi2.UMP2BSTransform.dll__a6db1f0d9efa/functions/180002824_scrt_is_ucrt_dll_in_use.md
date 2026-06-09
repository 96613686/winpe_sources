# __scrt_is_ucrt_dll_in_use

- ea: `0x180002824`
- end: `0x180002830`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180001f84`
- `0x180001fc4`
- `0x18000205c`
- `0x1800020ac`
- `0x180002140`
- `0x180002274`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180002824  xor     eax, eax
0x180002826  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x18000282c  setnz   al
0x18000282f  retn
```
