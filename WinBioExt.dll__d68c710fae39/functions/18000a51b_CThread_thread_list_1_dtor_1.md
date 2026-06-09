# _CThread::thread_list_::_1_::dtor$1

- ea: `0x18000a51b`
- end: `0x18000a527`
- name: `_CThread::thread_list_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: ``

## callees

- `0x180002200`

## pseudocode

```c
int CThread::thread_list_::_1_::dtor_1()
{
  return Init_thread_abort(&dword_180010620);
}

```

## disassembly

```asm
0x18000a51b  lea     rcx, dword_180010620
0x18000a522  jmp     _Init_thread_abort
```
