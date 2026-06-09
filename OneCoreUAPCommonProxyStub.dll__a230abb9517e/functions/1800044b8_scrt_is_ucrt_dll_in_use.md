# __scrt_is_ucrt_dll_in_use

- ea: `0x1800044b8`
- end: `0x1800044c4`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180003dac`
- `0x180003dec`
- `0x180003e84`
- `0x180003ed4`
- `0x180003f68`
- `0x18000409c`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x1800044b8  xor     eax, eax
0x1800044ba  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x1800044c0  setnz   al
0x1800044c3  retn
```
