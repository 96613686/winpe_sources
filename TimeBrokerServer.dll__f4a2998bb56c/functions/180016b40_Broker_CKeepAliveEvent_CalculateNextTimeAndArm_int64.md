# Broker::CKeepAliveEvent::CalculateNextTimeAndArm(__int64)

- ea: `0x180016b40`
- end: `0x180016d18`
- name: `?CalculateNextTimeAndArm@CKeepAliveEvent@Broker@@MEAAX_J@Z`
- size: `472`
- prototype: `void __fastcall(Broker::CKeepAliveEvent *this, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x180009cf0`
- `0x180009ea0`
- `0x180009f70`
- `0x18000a330`
- `0x18000a674`
- `0x180016b40`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180016c01`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180016c3a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180016c81`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180016c01`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180016c3a`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180016c81`

## pseudocode

```c
void __fastcall Broker::CKeepAliveEvent::CalculateNextTimeAndArm(Broker::CKeepAliveEvent *this, __int64 a2)
{
  __int64 v4; // rbx
  Broker::TimeEvent *v5; // rcx
  __int64 v6; // rax
  Broker::TimeEvent *v7; // rcx
  __int64 v8; // rdi
  ULONGLONG TickCount64; // rax
  __int64 v10; // r8
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // r14
  ULONGLONG v14; // r8

  v4 = *(_QWORD *)(*((_QWORD *)this + 31) + 16LL);
  v5 = (Broker::TimeEvent *)WPP_GLOBAL_Control;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_DD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      14,
      &WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids,
      (unsigned int)v4,
      HIDWORD(v4));
  if ( *((_BYTE *)this + 92) )
  {
    Broker::TimeEvent::SetState(this, 0);
  }
  else
  {
    v6 = Broker::TimeEvent::DueDateToUtcDueTime(v5, (const struct _SYSTEMTIME *)((char *)this + 280), 0);
    if ( *((_BYTE *)this + 312) )
    {
      *((_QWORD *)this + 3) = *((_QWORD *)this + 4);
      Broker::TimeEvent::SetState(this, 1);
    }
    else
    {
      if ( *((_DWORD *)this + 22) == 4 || !*((_QWORD *)this + 37) )
      {
        v13 = *((_QWORD *)this + 8);
        if ( v6 < a2 )
        {
          *((_QWORD *)this + 37) = Broker::TimeEvent::NextPeriodicDueTime(v7, v6, a2, *((_QWORD *)this + 8)) - v13;
          v14 = GetTickCount64() - v13 / 10000;
        }
        else
        {
          *((_QWORD *)this + 37) = v6;
          v14 = (v6 - v13 - a2) / 10000 + GetTickCount64();
        }
        *((_QWORD *)this + 38) = v14;
        v12 = *((_QWORD *)this + 37);
      }
      else
      {
        v8 = *((_QWORD *)this + 38);
        TickCount64 = GetTickCount64();
        v10 = *((_QWORD *)this + 8);
        v11 = 10000 * (TickCount64 - v8);
        if ( v10 > v11 )
          v10 = *((_QWORD *)this + 8) - v11;
        v12 = a2 + v10;
      }
      Broker::TimeEvent::ArmTimeEvent((__int64)this, v12 - *((_QWORD *)this + 7) / 2LL);
    }
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      WPP_SF_DD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        15,
        &WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids,
        (unsigned int)v4,
        HIDWORD(v4));
  }
}

```

## disassembly

```asm
0x180016b40  mov     [rsp+arg_8], rbx
0x180016b45  mov     [rsp+arg_10], rbp
0x180016b4a  push    rsi
0x180016b4b  push    rdi
0x180016b4c  push    r14
0x180016b4e  sub     rsp, 30h
0x180016b52  mov     rbx, [rcx+0F8h]
0x180016b59  mov     rbp, rdx
0x180016b5c  mov     rsi, rcx
0x180016b5f  mov     rbx, [rbx+10h]
0x180016b63  mov     [rsp+48h+arg_0], rbx
0x180016b68  mov     rcx, cs:WPP_GLOBAL_Control
0x180016b6f  test    byte ptr [rcx+1Ch], 1
0x180016b73  jz      short loc_180016B9E
0x180016b75  cmp     byte ptr [rcx+19h], 4
0x180016b79  jb      short loc_180016B9E
0x180016b7b  mov     rcx, [rcx+10h]
0x180016b7f  lea     r8, WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids
0x180016b86  mov     rax, rbx
0x180016b89  mov     edx, 0Eh
0x180016b8e  shr     rax, 20h
0x180016b92  mov     r9d, ebx
0x180016b95  mov     [rsp+48h+var_28], eax
0x180016b99  call    WPP_SF_DD
0x180016b9e  xor     r14d, r14d
0x180016ba1  cmp     [rsi+5Ch], r14b
0x180016ba5  jz      short loc_180016BB6
0x180016ba7  xor     edx, edx
0x180016ba9  mov     rcx, rsi
0x180016bac  call    ?SetState@TimeEvent@Broker@@IEAAXW4States@12@@Z; Broker::TimeEvent::SetState(Broker::TimeEvent::States)
0x180016bb1  jmp     loc_180016D05
0x180016bb6  lea     rdx, [rsi+118h]; struct _SYSTEMTIME *
0x180016bbd  xor     r8d, r8d; bool
0x180016bc0  call    ?DueDateToUtcDueTime@TimeEvent@Broker@@IEAA_JAEBU_SYSTEMTIME@@_N@Z; Broker::TimeEvent::DueDateToUtcDueTime(_SYSTEMTIME const &,bool)
0x180016bc5  mov     rdi, rax
0x180016bc8  cmp     [rsi+138h], r14b
0x180016bcf  jz      short loc_180016BEB
0x180016bd1  mov     rax, [rsi+20h]
0x180016bd5  mov     edx, 1
0x180016bda  mov     rcx, rsi
0x180016bdd  mov     [rsi+18h], rax
0x180016be1  call    ?SetState@TimeEvent@Broker@@IEAAXW4States@12@@Z; Broker::TimeEvent::SetState(Broker::TimeEvent::States)
0x180016be6  jmp     loc_180016CD2
0x180016beb  cmp     dword ptr [rsi+58h], 4
0x180016bef  jz      short loc_180016C2A
0x180016bf1  cmp     [rsi+128h], r14
0x180016bf8  jz      short loc_180016C2A
0x180016bfa  mov     rdi, [rsi+130h]
0x180016c01  call    cs:__imp_GetTickCount64
0x180016c07  mov     r8, [rsi+40h]
0x180016c0b  sub     rax, rdi
0x180016c0e  imul    rcx, rax, 2710h
0x180016c15  mov     rax, r8
0x180016c18  sub     rax, rcx
0x180016c1b  cmp     r8, rcx
0x180016c1e  cmovg   r8, rax
0x180016c22  add     r8, rbp
0x180016c25  jmp     loc_180016CB6
0x180016c2a  mov     r14, [rsi+40h]
0x180016c2e  cmp     rdi, rbp
0x180016c31  jl      short loc_180016C69
0x180016c33  mov     [rsi+128h], rdi
0x180016c3a  call    cs:__imp_GetTickCount64
0x180016c40  mov     rcx, rax
0x180016c43  sub     rdi, r14
0x180016c46  sub     rdi, rbp
0x180016c49  mov     rax, 346DC5D63886594Bh
0x180016c53  imul    rdi
0x180016c56  sar     rdx, 0Bh
0x180016c5a  mov     r8, rdx
0x180016c5d  add     rdx, rcx
0x180016c60  shr     r8, 3Fh
0x180016c64  add     r8, rdx
0x180016c67  jmp     short loc_180016CA8
0x180016c69  mov     r9, r14; __int64
0x180016c6c  mov     r8, rbp; __int64
0x180016c6f  mov     rdx, rdi; __int64
0x180016c72  call    ?NextPeriodicDueTime@TimeEvent@Broker@@IEAA_J_J00@Z; Broker::TimeEvent::NextPeriodicDueTime(__int64,__int64,__int64)
0x180016c77  sub     rax, r14
0x180016c7a  mov     [rsi+128h], rax
0x180016c81  call    cs:__imp_GetTickCount64
0x180016c87  mov     r8, rax
0x180016c8a  mov     rax, 346DC5D63886594Bh
0x180016c94  imul    r14
0x180016c97  sar     rdx, 0Bh
0x180016c9b  mov     rcx, rdx
0x180016c9e  shr     rcx, 3Fh
0x180016ca2  add     rdx, rcx
0x180016ca5  sub     r8, rdx
0x180016ca8  mov     [rsi+130h], r8
0x180016caf  mov     r8, [rsi+128h]
0x180016cb6  mov     rax, [rsi+38h]
0x180016cba  mov     ecx, 2
0x180016cbf  cqo
0x180016cc1  idiv    rcx
0x180016cc4  mov     rcx, rsi
0x180016cc7  sub     r8, rax
0x180016cca  mov     rdx, r8
0x180016ccd  call    ?ArmTimeEvent@TimeEvent@Broker@@IEAAX_JW4States@12@@Z; Broker::TimeEvent::ArmTimeEvent(__int64,Broker::TimeEvent::States)
0x180016cd2  mov     rcx, cs:WPP_GLOBAL_Control
0x180016cd9  test    byte ptr [rcx+1Ch], 1
0x180016cdd  jz      short loc_180016D05
0x180016cdf  cmp     byte ptr [rcx+19h], 4
0x180016ce3  jb      short loc_180016D05
0x180016ce5  mov     eax, dword ptr [rsp+48h+arg_0+4]
0x180016ce9  lea     r8, WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids
0x180016cf0  mov     rcx, [rcx+10h]
0x180016cf4  mov     edx, 0Fh
0x180016cf9  mov     r9d, ebx
0x180016cfc  mov     [rsp+48h+var_28], eax
0x180016d00  call    WPP_SF_DD
0x180016d05  mov     rbx, [rsp+48h+arg_8]
0x180016d0a  mov     rbp, [rsp+48h+arg_10]
0x180016d0f  add     rsp, 30h
0x180016d13  pop     r14
0x180016d15  pop     rdi
0x180016d16  pop     rsi
0x180016d17  retn
```
