# Broker::KeepAliveEvent::`scalar deleting destructor'(uint)

- ea: `0x18000ed80`
- end: `0x18000edc5`
- name: `??_GKeepAliveEvent@Broker@@UEAAPEAXI@Z`
- size: `69`
- prototype: `Broker::KeepAliveEvent *__fastcall(Broker::KeepAliveEvent *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180004b70`
- `0x18000ed80`
- `0x1800131e4`

## pseudocode

```c
Broker::KeepAliveEvent *__fastcall Broker::KeepAliveEvent::`scalar deleting destructor'(
        Broker::KeepAliveEvent *this,
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
0x18000ed80  mov     [rsp+arg_0], rbx
0x18000ed85  push    rdi
0x18000ed86  sub     rsp, 20h
0x18000ed8a  lea     rax, ??_7TimeEvent@Broker@@6B@; const Broker::TimeEvent::`vftable'
0x18000ed91  mov     rdi, rcx
0x18000ed94  mov     [rcx], rax
0x18000ed97  mov     ebx, edx
0x18000ed99  add     rcx, 100h
0x18000eda0  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x18000eda5  test    bl, 1
0x18000eda8  jz      short loc_18000EDB7
0x18000edaa  mov     edx, 120h; unsigned __int64
0x18000edaf  mov     rcx, rdi; void *
0x18000edb2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000edb7  mov     rbx, [rsp+28h+arg_0]
0x18000edbc  mov     rax, rdi
0x18000edbf  add     rsp, 20h
0x18000edc3  pop     rdi
0x18000edc4  retn
```
