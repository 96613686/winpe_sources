# _CThread::thread_list_::_1_::dtor$0

- ea: `0x18000a509`
- end: `0x18000a515`
- name: `_CThread::thread_list_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002200`

## pseudocode

```c
int CThread::thread_list_::_1_::dtor_0()
{
  return Init_thread_abort(&dword_180010608);
}

```

## disassembly

```asm
0x18000a509  lea     rcx, dword_180010608
0x18000a510  jmp     _Init_thread_abort
```
