# av_thread_message_queue_free

- ea: `0x180051bc0`
- end: `0x180051bec`
- name: `av_thread_message_queue_free`
- size: `44`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180039be0`
- `0x1800449d0`
- `0x180051aa0`
- `0x180051bc0`

## pseudocode

```c
__int64 __fastcall av_thread_message_queue_free(_QWORD *a1)
{
  _QWORD *v2; // rcx
  __int64 result; // rax

  v2 = (_QWORD *)*a1;
  if ( v2 )
  {
    av_thread_message_flush(v2);
    av_fifo_freep2(*a1);
    return av_freep(a1);
  }
  return result;
}

```

## disassembly

```asm
0x180051bc0  push    rbx
0x180051bc2  sub     rsp, 20h
0x180051bc6  mov     rbx, rcx
0x180051bc9  mov     rcx, [rcx]
0x180051bcc  test    rcx, rcx
0x180051bcf  jz      short loc_180051BE6
0x180051bd1  call    av_thread_message_flush
0x180051bd6  mov     rcx, [rbx]
0x180051bd9  call    av_fifo_freep2
0x180051bde  mov     rcx, rbx
0x180051be1  call    av_freep
0x180051be6  add     rsp, 20h
0x180051bea  pop     rbx
0x180051beb  retn
```
