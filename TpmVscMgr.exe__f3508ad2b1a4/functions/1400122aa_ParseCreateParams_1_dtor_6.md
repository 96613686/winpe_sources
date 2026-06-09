# _ParseCreateParams_::_1_::dtor$6

- ea: `0x1400122aa`
- end: `0x1400122b6`
- name: `_ParseCreateParams_::_1_::dtor$6`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140001af0`

## pseudocode

```c
__int64 ParseCreateParams_::_1_::dtor_6()
{
  return Init_thread_abort(&dword_14001A830);
}

```

## disassembly

```asm
0x1400122aa  lea     rcx, dword_14001A830
0x1400122b1  jmp     _Init_thread_abort
```
