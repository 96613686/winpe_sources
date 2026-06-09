# _ParseCreateParams_::_1_::dtor$11

- ea: `0x140012304`
- end: `0x140012310`
- name: `_ParseCreateParams_::_1_::dtor$11`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140001af0`

## pseudocode

```c
__int64 ParseCreateParams_::_1_::dtor_11()
{
  return Init_thread_abort(&dword_14001A920);
}

```

## disassembly

```asm
0x140012304  lea     rcx, dword_14001A920
0x14001230b  jmp     _Init_thread_abort
```
