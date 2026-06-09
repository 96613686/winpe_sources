# _ParseCreateParams_::_1_::dtor$9

- ea: `0x1400122e0`
- end: `0x1400122ec`
- name: `_ParseCreateParams_::_1_::dtor$9`
- size: `12`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x140001af0`

## pseudocode

```c
__int64 ParseCreateParams_::_1_::dtor_9()
{
  return Init_thread_abort(&dword_14001A8C0);
}

```

## disassembly

```asm
0x1400122e0  lea     rcx, dword_14001A8C0
0x1400122e7  jmp     _Init_thread_abort
```
