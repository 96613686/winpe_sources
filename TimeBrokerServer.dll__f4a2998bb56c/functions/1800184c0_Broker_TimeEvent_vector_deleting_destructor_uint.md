# Broker::TimeEvent::`vector deleting destructor'(uint)

- ea: `0x1800184c0`
- end: `0x180018505`
- name: `??_ETimeEvent@Broker@@UEAAPEAXI@Z`
- size: `69`
- prototype: `Broker::TimeEvent *__fastcall(Broker::TimeEvent *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180004b70`
- `0x1800131e4`
- `0x1800184c0`

## pseudocode

```c
Broker::TimeEvent *__fastcall Broker::TimeEvent::`vector deleting destructor'(Broker::TimeEvent *this, char a2)
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
0x1800184c0  mov     [rsp+arg_0], rbx
0x1800184c5  push    rdi
0x1800184c6  sub     rsp, 20h
0x1800184ca  lea     rax, ??_7TimeEvent@Broker@@6B@; const Broker::TimeEvent::`vftable'
0x1800184d1  mov     rdi, rcx
0x1800184d4  mov     [rcx], rax
0x1800184d7  mov     ebx, edx
0x1800184d9  add     rcx, 100h
0x1800184e0  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x1800184e5  test    bl, 1
0x1800184e8  jz      short loc_1800184F7
0x1800184ea  mov     edx, 118h; unsigned __int64
0x1800184ef  mov     rcx, rdi; void *
0x1800184f2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800184f7  mov     rbx, [rsp+28h+arg_0]
0x1800184fc  mov     rax, rdi
0x1800184ff  add     rsp, 20h
0x180018503  pop     rdi
0x180018504  retn
```
