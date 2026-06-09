# _ParseCreateParams_::_1_::dtor$10

- ea: `0x1400122f2`
- end: `0x1400122fe`
- name: `_ParseCreateParams_::_1_::dtor$10`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140001af0`

## pseudocode

```c
__int64 ParseCreateParams_::_1_::dtor_10()
{
  return Init_thread_abort(&dword_14001A8F0);
}

```

## disassembly

```asm
0x1400122f2  lea     rcx, dword_14001A8F0
0x1400122f9  jmp     _Init_thread_abort
```
