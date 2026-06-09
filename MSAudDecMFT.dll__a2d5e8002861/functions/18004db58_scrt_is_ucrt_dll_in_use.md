# __scrt_is_ucrt_dll_in_use

- ea: `0x18004db58`
- end: `0x18004db64`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: ``
- caller_count: `6`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x18004d44c`
- `0x18004d48c`
- `0x18004d524`
- `0x18004d574`
- `0x18004d608`
- `0x18004d73c`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x18004db58  xor     eax, eax
0x18004db5a  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x18004db60  setnz   al
0x18004db63  retn
```
