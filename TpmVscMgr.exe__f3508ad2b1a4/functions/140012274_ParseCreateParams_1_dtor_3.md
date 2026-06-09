# _ParseCreateParams_::_1_::dtor$3

- ea: `0x140012274`
- end: `0x140012280`
- name: `_ParseCreateParams_::_1_::dtor$3`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140001af0`

## pseudocode

```c
__int64 ParseCreateParams_::_1_::dtor_3()
{
  return Init_thread_abort(&dword_14001A7A0);
}

```

## disassembly

```asm
0x140012274  lea     rcx, dword_14001A7A0
0x14001227b  jmp     _Init_thread_abort
```
