# _ParseCreateParams_::_1_::dtor$8

- ea: `0x1400122ce`
- end: `0x1400122da`
- name: `_ParseCreateParams_::_1_::dtor$8`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140001af0`

## pseudocode

```c
__int64 ParseCreateParams_::_1_::dtor_8()
{
  return Init_thread_abort(&dword_14001A890);
}

```

## disassembly

```asm
0x1400122ce  lea     rcx, dword_14001A890
0x1400122d5  jmp     _Init_thread_abort
```
