# Broker::TimeEvent::TimeEvent(__int64,__int64,__int64,_TbiTimeEventModsParameters const *,_TbiTimeEventType,ulong,std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x1800109bc`
- end: `0x180010b2d`
- name: `??0TimeEvent@Broker@@QEAA@_J00PEBU_TbiTimeEventModsParameters@@W4_TbiTimeEventType@@KAEBV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `369`
- prototype: `Broker::TimeEvent *__fastcall(Broker::TimeEvent *this, __int64, __int64, __int64, _OWORD *, int, int, _QWORD *)`
- caller_count: `6`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18000a9e4`
- `0x1800169bc`
- `0x1800179fc`
- `0x18001811c`
- `0x180018320`
- `0x180018b0c`

## callees

- `0x18000c900`
- `0x18000d220`
- `0x1800109bc`
- `0x18001396c`
- `0x180017910`

## pseudocode

```c
Broker::TimeEvent *__fastcall Broker::TimeEvent::TimeEvent(
        Broker::TimeEvent *this,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        _OWORD *a5,
        int a6,
        int a7,
        _QWORD *a8)
{
  _QWORD *v9; // rcx
  bool WakeEnabled; // al
  Broker::TimeEvent *result; // rax

  *((_QWORD *)this + 7) = a3;
  *(_QWORD *)this = &Broker::TimeEvent::`vftable';
  *((_QWORD *)this + 8) = a4;
  *((_DWORD *)this + 18) = a6;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = a2;
  *((_DWORD *)this + 19) = 1;
  *((_QWORD *)this + 10) = 0;
  *((_DWORD *)this + 22) = 0;
  *((_WORD *)this + 46) = 0;
  *((_QWORD *)this + 30) = 0;
  *((_QWORD *)this + 31) = 0;
  v9 = (_QWORD *)((char *)this + 256);
  *v9 = 0;
  v9[1] = 0;
  v9[2] = 0;
  std::vector<unsigned char>::_Construct_n<unsigned char * const &,unsigned char * const &>(v9, a8[1] - *a8);
  if ( a5 )
    *(_OWORD *)((char *)this + 8) = *a5;
  else
    *(_OWORD *)((char *)this + 8) = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WakeEnabled = Broker::TimeEvent::GetWakeEnabled(this);
    WPP_SF_Ldddd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      *((_QWORD *)this + 7) / 10000000LL,
      *((_QWORD *)this + 6) / 600000000LL,
      *((unsigned int *)this + 18),
      (int)*((_QWORD *)this + 7) / 10000000,
      *((_QWORD *)this + 6) / 600000000LL,
      (int)*((_QWORD *)this + 8) / 10000000,
      WakeEnabled);
  }
  memset_0((char *)this + 94, 0, 0x80u);
  result = this;
  *((_OWORD *)this + 14) = 0;
  return result;
}

```

## disassembly

```asm
0x1800109bc  mov     [rsp+arg_0], rbx
0x1800109c1  push    rdi
0x1800109c2  sub     rsp, 40h
0x1800109c6  xor     edi, edi
0x1800109c8  mov     [rcx+38h], r8
0x1800109cc  mov     r8, [rsp+48h+arg_38]
0x1800109d4  lea     rax, ??_7TimeEvent@Broker@@6B@; const Broker::TimeEvent::`vftable'
0x1800109db  mov     [rcx], rax
0x1800109de  mov     rbx, rcx
0x1800109e1  mov     eax, [rsp+48h+arg_28]
0x1800109e5  mov     [rcx+40h], r9
0x1800109e9  mov     [rcx+48h], eax
0x1800109ec  lea     r9, [r8+8]
0x1800109f0  mov     [rcx+18h], rdi
0x1800109f4  mov     [rcx+20h], rdi
0x1800109f8  mov     [rcx+28h], rdi
0x1800109fc  mov     [rcx+30h], rdx
0x180010a00  mov     dword ptr [rcx+4Ch], 1
0x180010a07  mov     [rcx+50h], rdi
0x180010a0b  mov     [rcx+58h], edi
0x180010a0e  mov     [rcx+5Ch], di
0x180010a12  mov     [rcx+0F0h], rdi
0x180010a19  mov     [rcx+0F8h], rdi
0x180010a20  add     rcx, 100h
0x180010a27  mov     [rcx], rdi
0x180010a2a  mov     [rcx+8], rdi
0x180010a2e  mov     [rcx+10h], rdi
0x180010a32  mov     rdx, [r9]
0x180010a35  sub     rdx, [r8]
0x180010a38  call    ??$_Construct_n@AEBQEAEAEBQEAE@?$vector@EV?$allocator@E@std@@@std@@AEAAX_KAEBQEAE1@Z; std::vector<uchar>::_Construct_n<uchar * const &,uchar * const &>(unsigned __int64,uchar * const &,uchar * const &)
0x180010a3d  mov     rax, [rsp+48h+arg_20]
0x180010a42  test    rax, rax
0x180010a45  jz      short loc_180010A51
0x180010a47  movups  xmm0, xmmword ptr [rax]
0x180010a4a  movdqu  xmmword ptr [rbx+8], xmm0
0x180010a4f  jmp     short loc_180010A58
0x180010a51  xorps   xmm0, xmm0
0x180010a54  movups  xmmword ptr [rbx+8], xmm0
0x180010a58  mov     rax, cs:WPP_GLOBAL_Control
0x180010a5f  test    byte ptr [rax+1Ch], 40h
0x180010a63  jz      loc_180010B04
0x180010a69  cmp     byte ptr [rax+19h], 5
0x180010a6d  jb      loc_180010B04
0x180010a73  mov     rcx, rbx; this
0x180010a76  call    ?GetWakeEnabled@TimeEvent@Broker@@UEAA_NXZ; Broker::TimeEvent::GetWakeEnabled(void)
0x180010a7b  movzx   r10d, al
0x180010a7f  mov     r11, 0D6BF94D5E57A42BDh
0x180010a89  mov     [rsp+48h+var_10], r10d
0x180010a8e  mov     rax, r11
0x180010a91  imul    qword ptr [rbx+40h]
0x180010a95  mov     rax, 1CA213D840BAF7D5h
0x180010a9f  mov     r9, rdx
0x180010aa2  imul    qword ptr [rbx+30h]
0x180010aa6  add     r9, [rbx+40h]
0x180010aaa  mov     rax, r11
0x180010aad  mov     r8, rdx
0x180010ab0  sar     r9, 17h
0x180010ab4  imul    qword ptr [rbx+38h]
0x180010ab8  mov     rcx, r9
0x180010abb  sar     r8, 1Ah
0x180010abf  add     rdx, [rbx+38h]
0x180010ac3  shr     rcx, 3Fh
0x180010ac7  add     r9, rcx
0x180010aca  sar     rdx, 17h
0x180010ace  mov     [rsp+48h+var_18], r9d
0x180010ad3  mov     rcx, r8
0x180010ad6  mov     r9d, [rbx+48h]
0x180010ada  mov     rax, rdx
0x180010add  shr     rcx, 3Fh
0x180010ae1  add     r8, rcx
0x180010ae4  shr     rax, 3Fh
0x180010ae8  mov     rcx, cs:WPP_GLOBAL_Control
0x180010aef  add     rdx, rax
0x180010af2  mov     [rsp+48h+var_20], r8d
0x180010af7  mov     [rsp+48h+var_28], edx
0x180010afb  mov     rcx, [rcx+10h]
0x180010aff  call    WPP_SF_Ldddd
0x180010b04  lea     rcx, [rbx+5Eh]; void *
0x180010b08  xor     edx, edx; Val
0x180010b0a  mov     r8d, 80h; Size
0x180010b10  call    memset_0
0x180010b15  xorps   xmm0, xmm0
0x180010b18  mov     rax, rbx
0x180010b1b  movups  xmmword ptr [rbx+0E0h], xmm0
0x180010b22  mov     rbx, [rsp+48h+arg_0]
0x180010b27  add     rsp, 40h
0x180010b2b  pop     rdi
0x180010b2c  retn
```
