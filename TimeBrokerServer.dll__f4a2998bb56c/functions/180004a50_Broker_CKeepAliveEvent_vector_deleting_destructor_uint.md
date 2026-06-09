# Broker::CKeepAliveEvent::`vector deleting destructor'(uint)

- ea: `0x180004a50`
- end: `0x180004a95`
- name: `??_ECKeepAliveEvent@Broker@@UEAAPEAXI@Z`
- size: `69`
- prototype: `Broker::CKeepAliveEvent *__fastcall(Broker::CKeepAliveEvent *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180004a50`
- `0x180004b70`
- `0x1800131e4`

## pseudocode

```c
Broker::CKeepAliveEvent *__fastcall Broker::CKeepAliveEvent::`vector deleting destructor'(
        Broker::CKeepAliveEvent *this,
        char a2)
{
  *(_QWORD *)this = &Broker::TimeEvent::`vftable';
  std::vector<unsigned char>::_Tidy((char *)this + 256);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180004a50  mov     [rsp+arg_0], rbx
0x180004a55  push    rdi
0x180004a56  sub     rsp, 20h
0x180004a5a  lea     rax, ??_7TimeEvent@Broker@@6B@; const Broker::TimeEvent::`vftable'
0x180004a61  mov     rdi, rcx
0x180004a64  mov     [rcx], rax
0x180004a67  mov     ebx, edx
0x180004a69  add     rcx, 100h
0x180004a70  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180004a75  test    bl, 1
0x180004a78  jz      short loc_180004A87
0x180004a7a  mov     edx, 140h; unsigned __int64
0x180004a7f  mov     rcx, rdi; void *
0x180004a82  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004a87  mov     rbx, [rsp+28h+arg_0]
0x180004a8c  mov     rax, rdi
0x180004a8f  add     rsp, 20h
0x180004a93  pop     rdi
0x180004a94  retn
```
