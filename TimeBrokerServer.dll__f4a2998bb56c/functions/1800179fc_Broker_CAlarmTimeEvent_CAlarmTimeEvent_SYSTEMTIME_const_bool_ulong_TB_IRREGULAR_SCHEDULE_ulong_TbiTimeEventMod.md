# Broker::CAlarmTimeEvent::CAlarmTimeEvent(_SYSTEMTIME const &,bool,ulong,_TB_IRREGULAR_SCHEDULE,ulong,_TbiTimeEventModsParameters const *,bool,std::vector<uchar,std::allocator<uchar>> const &)

- ea: `0x1800179fc`
- end: `0x180017b80`
- name: `??0CAlarmTimeEvent@Broker@@QEAA@AEBU_SYSTEMTIME@@_NKU_TB_IRREGULAR_SCHEDULE@@KPEBU_TbiTimeEventModsParameters@@1AEBV?$vector@EV?$allocator@E@std@@@std@@@Z`
- size: `388`
- prototype: `__int64 __fastcall(__int64, _OWORD *, char, int, _OWORD *, int, __int64, unsigned __int8, __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000a698`

## callees

- `0x180003800`
- `0x180003840`
- `0x180009fc0`
- `0x18000a330`
- `0x1800109bc`
- `0x1800179fc`

## pseudocode

```c
__int64 __fastcall Broker::CAlarmTimeEvent::CAlarmTimeEvent(
        __int64 a1,
        _OWORD *a2,
        char a3,
        int a4,
        _OWORD *a5,
        int a6,
        __int64 a7,
        unsigned __int8 a8,
        __int64 a9)
{
  Broker::TimeEvent *v13; // rcx
  _BYTE *v14; // rax
  __int64 v15; // rax
  int v17; // [rsp+30h] [rbp-38h]

  Broker::TimeEvent::TimeEvent((Broker::TimeEvent *)a1, a7, 4, v17, a9);
  *(_QWORD *)a1 = &Broker::CAlarmTimeEvent::`vftable';
  *(_DWORD *)(a1 + 280) = a4;
  *(_OWORD *)(a1 + 284) = *a2;
  *(_BYTE *)(a1 + 322) = a3;
  *(_OWORD *)(a1 + 328) = *a5;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, &WPP_ba7c69de85b63ac04c9231a1a350be3e_Traceguids);
  v13 = (Broker::TimeEvent *)a8;
  *(_BYTE *)(a1 + 321) = a8;
  *(_BYTE *)(a1 + 320) = 0;
  v14 = WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, &WPP_ba7c69de85b63ac04c9231a1a350be3e_Traceguids, a8);
      v14 = WPP_GLOBAL_Control;
    }
    if ( (v14[28] & 1) != 0 && v14[25] >= 4u )
    {
      v15 = Broker::TimeEvent::DueDateToUtcDueTime(v13, (const struct _SYSTEMTIME *)(a1 + 284), 0);
      WPP_SF_i(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_ba7c69de85b63ac04c9231a1a350be3e_Traceguids, v15);
    }
  }
  *(_QWORD *)(a1 + 32) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 304) = 0;
  *(_QWORD *)(a1 + 312) = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, &WPP_ba7c69de85b63ac04c9231a1a350be3e_Traceguids);
  return a1;
}

```

## disassembly

```asm
0x1800179fc  mov     [rsp+arg_0], rcx
0x180017a01  push    rbx
0x180017a02  push    rsi
0x180017a03  push    rdi
0x180017a04  push    r14
0x180017a06  sub     rsp, 48h
0x180017a0a  mov     ebx, r9d
0x180017a0d  mov     sil, r8b
0x180017a10  mov     rdi, rdx
0x180017a13  mov     r14, rcx
0x180017a16  imul    r9, rbx, 989680h
0x180017a1d  mov     eax, [rsp+68h+arg_28]
0x180017a24  imul    r8, rax, 989680h
0x180017a2b  mov     rax, [rsp+68h+arg_40]
0x180017a33  mov     [rsp+68h+var_30], rax; __int64
0x180017a38  mov     [rsp+68h+var_40], 4; int
0x180017a40  mov     rax, [rsp+68h+arg_30]
0x180017a48  mov     [rsp+68h+var_48], rax; __int64
0x180017a4d  mov     rdx, 3FFFFFFFFFFFFFFFh
0x180017a57  call    ??0TimeEvent@Broker@@QEAA@_J00PEBU_TbiTimeEventModsParameters@@W4_TbiTimeEventType@@KAEBV?$vector@EV?$allocator@E@std@@@std@@@Z; Broker::TimeEvent::TimeEvent(__int64,__int64,__int64,_TbiTimeEventModsParameters const *,_TbiTimeEventType,ulong,std::vector<uchar> const &)
0x180017a5c  nop
0x180017a5d  lea     rax, ??_7CAlarmTimeEvent@Broker@@6B@; const Broker::CAlarmTimeEvent::`vftable'
0x180017a64  mov     [r14], rax
0x180017a67  mov     [r14+118h], ebx
0x180017a6e  lea     rbx, [r14+11Ch]
0x180017a75  movups  xmm0, xmmword ptr [rdi]
0x180017a78  movdqu  xmmword ptr [rbx], xmm0
0x180017a7c  mov     [r14+142h], sil
0x180017a83  mov     rax, [rsp+68h+arg_20]
0x180017a8b  movaps  xmm0, xmmword ptr [rax]
0x180017a8e  movdqu  xmmword ptr [r14+148h], xmm0
0x180017a97  mov     rcx, cs:WPP_GLOBAL_Control
0x180017a9e  lea     rsi, WPP_ba7c69de85b63ac04c9231a1a350be3e_Traceguids
0x180017aa5  test    byte ptr [rcx+1Ch], 1
0x180017aa9  jz      short loc_180017AC2
0x180017aab  cmp     byte ptr [rcx+19h], 4
0x180017aaf  jb      short loc_180017AC2
0x180017ab1  mov     edx, 0Ah
0x180017ab6  mov     r8, rsi
0x180017ab9  mov     rcx, [rcx+10h]
0x180017abd  call    WPP_SF_
0x180017ac2  movzx   ecx, [rsp+68h+arg_38]
0x180017aca  mov     [r14+141h], cl
0x180017ad1  xor     edi, edi
0x180017ad3  mov     [r14+140h], dil
0x180017ada  mov     rax, cs:WPP_GLOBAL_Control
0x180017ae1  test    byte ptr [rax+1Ch], 1
0x180017ae5  jz      short loc_180017B38
0x180017ae7  cmp     byte ptr [rax+19h], 4
0x180017aeb  jb      short loc_180017B06
0x180017aed  mov     r9d, ecx
0x180017af0  lea     edx, [rdi+0Bh]
0x180017af3  mov     r8, rsi
0x180017af6  mov     rcx, [rax+10h]
0x180017afa  call    WPP_SF_d
0x180017aff  mov     rax, cs:WPP_GLOBAL_Control
0x180017b06  test    byte ptr [rax+1Ch], 1
0x180017b0a  jz      short loc_180017B38
0x180017b0c  cmp     byte ptr [rax+19h], 4
0x180017b10  jb      short loc_180017B38
0x180017b12  xor     r8d, r8d; bool
0x180017b15  mov     rdx, rbx; struct _SYSTEMTIME *
0x180017b18  call    ?DueDateToUtcDueTime@TimeEvent@Broker@@IEAA_JAEBU_SYSTEMTIME@@_N@Z; Broker::TimeEvent::DueDateToUtcDueTime(_SYSTEMTIME const &,bool)
0x180017b1d  mov     edx, 0Ch
0x180017b22  mov     r9, rax
0x180017b25  mov     r8, rsi
0x180017b28  mov     rcx, cs:WPP_GLOBAL_Control
0x180017b2f  mov     rcx, [rcx+10h]
0x180017b33  call    WPP_SF_i
0x180017b38  mov     [r14+20h], rdi
0x180017b3c  mov     [r14+18h], rdi
0x180017b40  mov     [r14+130h], rdi
0x180017b47  mov     [r14+138h], rdi
0x180017b4e  mov     rcx, cs:WPP_GLOBAL_Control
0x180017b55  test    byte ptr [rcx+1Ch], 1
0x180017b59  jz      short loc_180017B73
0x180017b5b  cmp     byte ptr [rcx+19h], 4
0x180017b5f  jb      short loc_180017B73
0x180017b61  mov     edx, 0Dh
0x180017b66  mov     r8, rsi
0x180017b69  mov     rcx, [rcx+10h]
0x180017b6d  call    WPP_SF_
0x180017b72  nop
0x180017b73  mov     rax, r14
0x180017b76  add     rsp, 48h
0x180017b7a  pop     r14
0x180017b7c  pop     rdi
0x180017b7d  pop     rsi
0x180017b7e  pop     rbx
0x180017b7f  retn
```
