# Broker::ConvenientTimeEvent::`scalar deleting destructor'(uint)

- ea: `0x180004ab0`
- end: `0x180004af5`
- name: `??_GConvenientTimeEvent@Broker@@UEAAPEAXI@Z`
- size: `69`
- prototype: `Broker::ConvenientTimeEvent *__fastcall(Broker::ConvenientTimeEvent *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180004ab0`
- `0x180004b70`
- `0x1800131e4`

## pseudocode

```c
Broker::ConvenientTimeEvent *__fastcall Broker::ConvenientTimeEvent::`scalar deleting destructor'(
        Broker::ConvenientTimeEvent *this,
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
0x180004ab0  mov     [rsp+arg_0], rbx
0x180004ab5  push    rdi
0x180004ab6  sub     rsp, 20h
0x180004aba  lea     rax, ??_7TimeEvent@Broker@@6B@; const Broker::TimeEvent::`vftable'
0x180004ac1  mov     rdi, rcx
0x180004ac4  mov     [rcx], rax
0x180004ac7  mov     ebx, edx
0x180004ac9  add     rcx, 100h
0x180004ad0  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180004ad5  test    bl, 1
0x180004ad8  jz      short loc_180004AE7
0x180004ada  mov     edx, 138h; unsigned __int64
0x180004adf  mov     rcx, rdi; void *
0x180004ae2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180004ae7  mov     rbx, [rsp+28h+arg_0]
0x180004aec  mov     rax, rdi
0x180004aef  add     rsp, 20h
0x180004af3  pop     rdi
0x180004af4  retn
```
