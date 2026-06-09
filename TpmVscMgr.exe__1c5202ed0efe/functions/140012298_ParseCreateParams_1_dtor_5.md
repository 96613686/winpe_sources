# _ParseCreateParams_::_1_::dtor$5

- ea: `0x140012298`
- end: `0x1400122a4`
- name: `_ParseCreateParams_::_1_::dtor$5`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140001af0`

## pseudocode

```c
__int64 ParseCreateParams_::_1_::dtor_5()
{
  return Init_thread_abort(&dword_14001A800);
}

```

## disassembly

```asm
0x140012298  lea     rcx, dword_14001A800
0x14001229f  jmp     _Init_thread_abort
```
