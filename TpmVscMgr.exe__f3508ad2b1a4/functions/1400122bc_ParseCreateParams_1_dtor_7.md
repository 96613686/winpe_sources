# _ParseCreateParams_::_1_::dtor$7

- ea: `0x1400122bc`
- end: `0x1400122c8`
- name: `_ParseCreateParams_::_1_::dtor$7`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140001af0`

## pseudocode

```c
__int64 ParseCreateParams_::_1_::dtor_7()
{
  return Init_thread_abort(&dword_14001A860);
}

```

## disassembly

```asm
0x1400122bc  lea     rcx, dword_14001A860
0x1400122c3  jmp     _Init_thread_abort
```
