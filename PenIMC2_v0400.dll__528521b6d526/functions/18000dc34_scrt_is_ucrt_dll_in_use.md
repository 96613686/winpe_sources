# __scrt_is_ucrt_dll_in_use

- ea: `0x18000dc34`
- end: `0x18000dc40`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000d0b8`
- `0x18000d0f4`
- `0x18000d180`
- `0x18000d1e0`
- `0x18000d270`
- `0x18000d394`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x18000dc34  xor     eax, eax
0x18000dc36  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x18000dc3c  setnz   al
0x18000dc3f  retn
```
