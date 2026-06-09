# _ParseCreateParams_::_1_::dtor$4

- ea: `0x140012286`
- end: `0x140012292`
- name: `_ParseCreateParams_::_1_::dtor$4`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140001af0`

## pseudocode

```c
__int64 ParseCreateParams_::_1_::dtor_4()
{
  return Init_thread_abort(&dword_14001A7D0);
}

```

## disassembly

```asm
0x140012286  lea     rcx, dword_14001A7D0
0x14001228d  jmp     _Init_thread_abort
```
