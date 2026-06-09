# av_thread_message_queue_set_free_func

- ea: `0x180039ae0`
- end: `0x180039ae5`
- name: `av_thread_message_queue_set_free_func`
- size: `5`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## pseudocode

```c
void __fastcall av_thread_message_queue_set_free_func(__int64 a1, __int64 a2)
{
  *(_QWORD *)(a1 + 48) = a2;
}

```

## disassembly

```asm
0x180039ae0  mov     [rcx+30h], rdx; av_fifo_auto_grow_limit
0x180039ae4  retn
```
