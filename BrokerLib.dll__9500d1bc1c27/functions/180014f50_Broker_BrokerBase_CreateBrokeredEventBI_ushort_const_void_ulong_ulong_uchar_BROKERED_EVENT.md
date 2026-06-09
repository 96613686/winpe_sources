# Broker::BrokerBase::CreateBrokeredEventBI(ushort const *,void *,ulong,ulong,uchar *,_BROKERED_EVENT * *)

- ea: `0x180014f50`
- end: `0x1800150b5`
- name: `?CreateBrokeredEventBI@BrokerBase@Broker@@QEAAXPEBGPEAXKKPEAEPEAPEAU_BROKERED_EVENT@@@Z`
- size: `357`
- prototype: `void __fastcall(Broker::BrokerBase *this, const unsigned __int16 *, void *, int, size_t Size, unsigned __int8 *, struct _BROKERED_EVENT **)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180016b50`

## callees

- `0x1800035f8`
- `0x180004d70`
- `0x180005b50`
- `0x180006b30`
- `0x180008340`
- `0x18000ab90`
- `0x180014f50`
- `0x1800150bc`
- `0x180015af0`
- `0x1800165b6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Broker::BrokerBase::CreateBrokeredEventBI(
        Broker::BrokerBase *this,
        const unsigned __int16 *a2,
        void *a3,
        int a4,
        size_t Size,
        unsigned __int8 *a6,
        struct _BROKERED_EVENT **a7)
{
  struct _BROKERED_EVENT *Event; // rdi
  char *v12; // rbx
  struct _BROKERED_EVENT *v13; // [rsp+30h] [rbp-D8h]
  void *v14[2]; // [rsp+38h] [rbp-D0h] BYREF
  __int64 v15; // [rsp+48h] [rbp-C0h]
  __int128 Src; // [rsp+50h] [rbp-B8h] BYREF
  _QWORD v17[12]; // [rsp+60h] [rbp-A8h] BYREF

  *(_QWORD *)&Src = a6;
  if ( (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x800) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
    WPP_SF__guid_(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      31,
      &WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids,
      *((_QWORD *)this + 1));
  try
  {
    Event = Broker::BrokerBase::AllocateEvent(this, a2, a3);
    v13 = Event;
    Broker::ApplicationIdentity::ApplicationIdentity((Broker::ApplicationIdentity *)v17, a3, a2);
    *(_OWORD *)v14 = 0;
    v15 = 0;
    if ( (_DWORD)Size )
    {
      std::vector<unsigned char>::_Buy_nonzero(v14, (unsigned int)Size);
      v12 = (char *)v14[0];
      memmove_0(v14[0], (const void *)Src, (unsigned int)Size);
      v14[1] = &v12[(unsigned int)Size];
    }
    *(_OWORD *)Event = *Broker::BILayer::CreateEventW(&Src, *((_QWORD *)this + 1), v17, a4, (__int64)v14);
    *((_DWORD *)Event + 10) = 0;
    *((_DWORD *)Event + 11) = a4;
    *((_DWORD *)Event + 12) = 1;
  }
  catch ( ... )
  {
    BciHeapFree(v13);
    throw;
  }
  std::vector<unsigned char>::_Tidy(v14);
  Broker::ApplicationIdentity::~ApplicationIdentity((Broker::ApplicationIdentity *)v17);
  *a7 = Event;
}

```

## disassembly

```asm
0x180014f50  push    rbx
0x180014f52  push    rsi
0x180014f53  push    rdi
0x180014f54  push    r12
0x180014f56  push    r13
0x180014f58  push    r14
0x180014f5a  push    r15
0x180014f5c  sub     rsp, 0D0h
0x180014f63  mov     rax, cs:__security_cookie
0x180014f6a  xor     rax, rsp
0x180014f6d  mov     [rsp+108h+var_48], rax
0x180014f75  mov     r15d, r9d
0x180014f78  mov     rsi, r8
0x180014f7b  mov     rbx, rdx
0x180014f7e  mov     r14, rcx
0x180014f81  mov     r13d, dword ptr [rsp+108h+Size]
0x180014f89  mov     rax, [rsp+108h+arg_28]
0x180014f91  mov     qword ptr [rsp+108h+Src], rax
0x180014f96  mov     r12, [rsp+108h+arg_30]
0x180014f9e  mov     rcx, cs:WPP_GLOBAL_Control
0x180014fa5  test    dword ptr [rcx+1Ch], 800h
0x180014fac  jz      short loc_180014FCD
0x180014fae  cmp     byte ptr [rcx+19h], 5
0x180014fb2  jb      short loc_180014FCD
0x180014fb4  mov     edx, 1Fh
0x180014fb9  mov     r9, [r14+8]
0x180014fbd  lea     r8, WPP_4753d2a3665d3618996ed9ba7dd16268_Traceguids
0x180014fc4  mov     rcx, [rcx+10h]
0x180014fc8  call    WPP_SF__guid_
0x180014fcd  mov     [rsp+108h+var_D8], 0
0x180014fd6  mov     r8, rsi; void *
0x180014fd9  mov     rdx, rbx; unsigned __int16 *
0x180014fdc  mov     rcx, r14; this
0x180014fdf  call    ?AllocateEvent@BrokerBase@Broker@@AEAAPEAU_BROKERED_EVENT@@PEBGPEAX@Z; Broker::BrokerBase::AllocateEvent(ushort const *,void *)
0x180014fe4  mov     rdi, rax
0x180014fe7  mov     [rsp+108h+var_D8], rax
0x180014fec  mov     r8, rbx; unsigned __int16 *
0x180014fef  mov     rdx, rsi; void *
0x180014ff2  lea     rcx, [rsp+108h+var_A8]; this
0x180014ff7  call    ??0ApplicationIdentity@Broker@@QEAA@PEAXQEBG@Z; Broker::ApplicationIdentity::ApplicationIdentity(void *,ushort const * const)
0x180014ffc  nop
0x180014ffd  xorps   xmm0, xmm0
0x180015000  movdqu  xmmword ptr [rsp+108h+var_D0], xmm0
0x180015006  mov     [rsp+108h+var_C0], 0
0x18001500f  test    r13d, r13d
0x180015012  jz      short loc_18001503F
0x180015014  mov     rdx, r13
0x180015017  lea     rcx, [rsp+108h+var_D0]
0x18001501c  call    ?_Buy_nonzero@?$vector@EV?$allocator@E@std@@@std@@AEAAX_K@Z; std::vector<uchar>::_Buy_nonzero(unsigned __int64)
0x180015021  mov     rbx, [rsp+108h+var_D0]
0x180015026  mov     r8, r13; Size
0x180015029  mov     rdx, qword ptr [rsp+108h+Src]; Src
0x18001502e  mov     rcx, rbx; void *
0x180015031  call    memmove_0
0x180015036  lea     rax, [rbx+r13]
0x18001503a  mov     [rsp+108h+var_D0+8], rax
0x18001503f  lea     rax, [rsp+108h+var_D0]
0x180015044  mov     [rsp+108h+var_E8], rax; __int64
0x180015049  mov     r9d, r15d
0x18001504c  lea     r8, [rsp+108h+var_A8]
0x180015051  mov     rdx, [r14+8]
0x180015055  lea     rcx, [rsp+108h+Src]; __int64
0x18001505a  call    ?CreateEventW@BILayer@Broker@@YA?AU_GUID@@AEBU3@AEBUApplicationIdentity@2@KAEBV?$vector@EV?$allocator@E@std@@@std@@@Z; Broker::BILayer::CreateEventW(_GUID const &,Broker::ApplicationIdentity const &,ulong,std::vector<uchar> const &)
0x18001505f  movups  xmm0, xmmword ptr [rax]
0x180015062  movdqu  xmmword ptr [rdi], xmm0
0x180015066  mov     dword ptr [rdi+28h], 0
0x18001506d  mov     [rdi+2Ch], r15d
0x180015071  mov     dword ptr [rdi+30h], 1
0x180015078  lea     rcx, [rsp+108h+var_D0]
0x18001507d  call    ?_Tidy@?$vector@EV?$allocator@E@std@@@std@@AEAAXXZ; std::vector<uchar>::_Tidy(void)
0x180015082  nop
0x180015083  lea     rcx, [rsp+108h+var_A8]; this
0x180015088  call    ??1ApplicationIdentity@Broker@@QEAA@XZ; Broker::ApplicationIdentity::~ApplicationIdentity(void)
0x18001508d  nop
0x18001508e  mov     [r12], rdi
0x180015092  mov     rcx, [rsp+108h+var_48]
0x18001509a  xor     rcx, rsp; StackCookie
0x18001509d  call    __security_check_cookie
0x1800150a2  add     rsp, 0D0h
0x1800150a9  pop     r15
0x1800150ab  pop     r14
0x1800150ad  pop     r13
0x1800150af  pop     r12
0x1800150b1  pop     rdi
0x1800150b2  pop     rsi
0x1800150b3  pop     rbx
0x1800150b4  retn
```
