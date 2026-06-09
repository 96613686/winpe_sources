# _ParseCreateParams_::_1_::dtor$1

- ea: `0x140012250`
- end: `0x14001225c`
- name: `_ParseCreateParams_::_1_::dtor$1`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140001af0`

## pseudocode

```c
__int64 ParseCreateParams_::_1_::dtor_1()
{
  return Init_thread_abort(&dword_14001A740);
}

```

## disassembly

```asm
0x140012250  lea     rcx, dword_14001A740
0x140012257  jmp     _Init_thread_abort
```
