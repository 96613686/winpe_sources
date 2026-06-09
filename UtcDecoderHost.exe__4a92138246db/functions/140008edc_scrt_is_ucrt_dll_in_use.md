# __scrt_is_ucrt_dll_in_use

- ea: `0x140008edc`
- end: `0x140008ee8`
- name: `__scrt_is_ucrt_dll_in_use`
- size: `12`
- prototype: `_BOOL8()`
- caller_count: `3`
- callee_count: `0`
- tags: `loader_planting`

## callers

- `0x140008684`
- `0x140008704`
- `0x140008838`

## pseudocode

```c
_BOOL8 _scrt_is_ucrt_dll_in_use()
{
  return _scrt_ucrt_dll_is_in_use != 0;
}

```

## disassembly

```asm
0x140008edc  xor     eax, eax
0x140008ede  cmp     cs:__scrt_ucrt_dll_is_in_use, eax
0x140008ee4  setnz   al
0x140008ee7  retn
```
