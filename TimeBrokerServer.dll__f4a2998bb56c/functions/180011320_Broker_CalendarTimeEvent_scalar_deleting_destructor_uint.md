# Broker::CalendarTimeEvent::`scalar deleting destructor'(uint)

- ea: `0x180011320`
- end: `0x180011365`
- name: `??_GCalendarTimeEvent@Broker@@UEAAPEAXI@Z`
- size: `69`
- prototype: `Broker::CalendarTimeEvent *__fastcall(Broker::CalendarTimeEvent *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180004b70`
- `0x180011320`
- `0x1800131e4`

## pseudocode

```c
Broker::CalendarTimeEvent *__fastcall Broker::CalendarTimeEvent::`scalar deleting destructor'(
        Broker::CalendarTimeEvent *this,
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
0x180011320  mov     [rsp+arg_0], rbx
0x180011325  push    rdi
0x180011326  sub     rsp, 20h
0x18001132a  lea     rax, ??_7TimeEvent@Broker@@6B@; const Broker::TimeEvent::`vftable'
0x180011331  mov     rdi, rcx
0x180011334  mov     [rcx], rax
0x180011337  mov     ebx, edx
0x180011339  add     rcx, 100h
0x180011340  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180011345  test    bl, 1
0x180011348  jz      short loc_180011357
0x18001134a  mov     edx, 130h; unsigned __int64
0x18001134f  mov     rcx, rdi; void *
0x180011352  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180011357  mov     rbx, [rsp+28h+arg_0]
0x18001135c  mov     rax, rdi
0x18001135f  add     rsp, 20h
0x180011363  pop     rdi
0x180011364  retn
```
