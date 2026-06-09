# __scrt_is_ucrt_dll_in_use

- ea: `0x180010f34`
- end: `0x180010f40`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x180010710`
- `0x180010750`
- `0x1800107e8`
- `0x180010838`
- `0x1800108cc`
- `0x180010a00`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x180010f34  xor     eax, eax
0x180010f36  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x180010f3c  setnz   al
0x180010f3f  retn
```
