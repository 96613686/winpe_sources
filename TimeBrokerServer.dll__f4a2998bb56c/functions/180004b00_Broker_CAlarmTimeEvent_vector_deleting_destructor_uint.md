# Broker::CAlarmTimeEvent::`vector deleting destructor'(uint)

- ea: `0x180004b00`
- end: `0x180004b45`
- name: `??_ECAlarmTimeEvent@Broker@@UEAAPEAXI@Z`
- size: `69`
- prototype: `Broker::CAlarmTimeEvent *__fastcall(Broker::CAlarmTimeEvent *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180004b00`
- `0x180004b70`
- `0x1800131e4`

## pseudocode

```c
Broker::CAlarmTimeEvent *__fastcall Broker::CAlarmTimeEvent::`vector deleting destructor'(
        Broker::CAlarmTimeEvent *this,
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
0x180004b00  mov     [rsp+arg_0], rbx
0x180004b05  push    rdi
0x180004b06  sub     rsp, 20h
0x180004b0a  lea     rax, ??_7TimeEvent@Broker@@6B@; const Broker::TimeEvent::`vftable'
0x180004b11  mov     rdi, rcx
0x180004b14  mov     [rcx], rax
0x180004b17  mov     ebx, edx
0x180004b19  add     rcx, 100h
0x180004b20  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180004b25  test    bl, 1
0x180004b28  jz      short loc_180004B37
0x180004b2a  mov     edx, 158h; unsigned __int64
0x180004b2f  mov     rcx, rdi; void *
0x180004b32  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004b37  mov     rbx, [rsp+28h+arg_0]
0x180004b3c  mov     rax, rdi
0x180004b3f  add     rsp, 20h
0x180004b43  pop     rdi
0x180004b44  retn
```
