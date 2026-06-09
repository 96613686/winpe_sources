# _ParseCreateParams_::_1_::dtor$2

- ea: `0x140012262`
- end: `0x14001226e`
- name: `_ParseCreateParams_::_1_::dtor$2`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140001af0`

## pseudocode

```c
__int64 ParseCreateParams_::_1_::dtor_2()
{
  return Init_thread_abort(&dword_14001A770);
}

```

## disassembly

```asm
0x140012262  lea     rcx, dword_14001A770
0x140012269  jmp     _Init_thread_abort
```
