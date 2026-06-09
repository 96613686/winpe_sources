# __scrt_is_ucrt_dll_in_use

- ea: `0x18000f9e0`
- end: `0x18000f9ec`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18000ede0`
- `0x18000ee20`
- `0x18000eec4`
- `0x18000ef2c`
- `0x18000efc0`
- `0x18000f0f4`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x18000f9e0  xor     eax, eax
0x18000f9e2  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x18000f9e8  setnz   al
0x18000f9eb  retn
```
