# Broker::CKeepAliveEvent::OnUpdateEvent(_TbiTimeEventCreationParameters &,__int64)

- ea: `0x180017040`
- end: `0x180017176`
- name: `?OnUpdateEvent@CKeepAliveEvent@Broker@@UEAAXAEAU_TbiTimeEventCreationParameters@@_J@Z`
- size: `310`
- prototype: `void __fastcall(Broker::CKeepAliveEvent *__hidden this, struct _TbiTimeEventCreationParameters *, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180009ea0`
- `0x180009f70`
- `0x180017040`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800170d2`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x1800170d2`
- `BrokerLib!BrGetBrokeredEventState` at `0x180017108`
- `BrokerLib!BrGetBrokeredEventState` at `0x180017108`

## pseudocode

```c
void __fastcall Broker::CKeepAliveEvent::OnUpdateEvent(
        Broker::CKeepAliveEvent *this,
        struct _TbiTimeEventCreationParameters *a2,
        __int64 a3)
{
  __int64 v6; // rbx
  __int128 v7; // xmm0
  ULONGLONG TickCount64; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  int v11; // [rsp+50h] [rbp+8h] BYREF
  __int64 v12; // [rsp+58h] [rbp+10h]

  v6 = *(_QWORD *)(*((_QWORD *)this + 31) + 16LL);
  v12 = v6;
  v11 = 0;
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_DD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      16,
      &WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids,
      (unsigned int)v6,
      HIDWORD(v6));
  *((_QWORD *)this + 8) = 10000000LL * *((unsigned int *)a2 + 6);
  *((_QWORD *)this + 7) = 10000000LL * *((unsigned int *)a2 + 7);
  v7 = *(_OWORD *)((char *)a2 + 8);
  *((_QWORD *)this + 37) = a3;
  *(_OWORD *)((char *)this + 280) = v7;
  TickCount64 = GetTickCount64();
  v9 = *((_QWORD *)this + 31);
  v10 = *((_QWORD *)this + 30);
  *((_QWORD *)this + 38) = TickCount64;
  *((_WORD *)this + 156) = 0;
  *((_BYTE *)this + 314) = *((_DWORD *)a2 + 8) != 0;
  if ( !(unsigned int)BrGetBrokeredEventState(v10, v9, &v11) && v11 == 1 )
  {
    Broker::TimeEvent::SetState(this, 4);
    (*(void (__fastcall **)(Broker::CKeepAliveEvent *, __int64))(*(_QWORD *)this + 72LL))(this, a3);
  }
  if ( (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    WPP_SF_DD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      17,
      &WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids,
      (unsigned int)v6,
      HIDWORD(v12));
}

```

## disassembly

```asm
0x180017040  mov     [rsp+arg_10], rbx
0x180017045  push    rbp
0x180017046  push    rsi
0x180017047  push    rdi
0x180017048  sub     rsp, 30h
0x18001704c  mov     rbx, [rcx+0F8h]
0x180017053  mov     rbp, r8
0x180017056  mov     rsi, rdx
0x180017059  mov     rdi, rcx
0x18001705c  mov     rbx, [rbx+10h]
0x180017060  mov     [rsp+48h+arg_8], rbx
0x180017065  mov     [rsp+48h+arg_0], 0
0x18001706d  mov     rcx, cs:WPP_GLOBAL_Control
0x180017074  test    byte ptr [rcx+1Ch], 1
0x180017078  jz      short loc_1800170A3
0x18001707a  cmp     byte ptr [rcx+19h], 4
0x18001707e  jb      short loc_1800170A3
0x180017080  mov     rcx, [rcx+10h]
0x180017084  lea     r8, WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids
0x18001708b  mov     rax, rbx
0x18001708e  mov     edx, 10h
0x180017093  shr     rax, 20h
0x180017097  mov     r9d, ebx
0x18001709a  mov     [rsp+48h+var_28], eax
0x18001709e  call    WPP_SF_DD
0x1800170a3  mov     eax, [rsi+18h]
0x1800170a6  imul    rcx, rax, 989680h
0x1800170ad  mov     [rdi+40h], rcx
0x1800170b1  mov     eax, [rsi+1Ch]
0x1800170b4  imul    rcx, rax, 989680h
0x1800170bb  mov     [rdi+38h], rcx
0x1800170bf  movups  xmm0, xmmword ptr [rsi+8]
0x1800170c3  mov     [rdi+128h], rbp
0x1800170ca  movdqu  xmmword ptr [rdi+118h], xmm0
0x1800170d2  call    cs:__imp_GetTickCount64
0x1800170d8  mov     rdx, [rdi+0F8h]
0x1800170df  lea     r8, [rsp+48h+arg_0]
0x1800170e4  mov     rcx, [rdi+0F0h]
0x1800170eb  mov     [rdi+130h], rax
0x1800170f2  mov     word ptr [rdi+138h], 0
0x1800170fb  cmp     dword ptr [rsi+20h], 0
0x1800170ff  setnz   al
0x180017102  mov     [rdi+13Ah], al
0x180017108  call    cs:__imp_BrGetBrokeredEventState
0x18001710e  test    eax, eax
0x180017110  jnz     short loc_180017136
0x180017112  cmp     [rsp+48h+arg_0], 1
0x180017117  jnz     short loc_180017136
0x180017119  lea     edx, [rax+4]
0x18001711c  mov     rcx, rdi
0x18001711f  call    ?SetState@TimeEvent@Broker@@IEAAXW4States@12@@Z; Broker::TimeEvent::SetState(Broker::TimeEvent::States)
0x180017124  mov     rax, [rdi]
0x180017127  mov     rdx, rbp
0x18001712a  mov     rcx, rdi
0x18001712d  mov     rax, [rax+48h]
0x180017131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017136  mov     rcx, cs:WPP_GLOBAL_Control
0x18001713d  test    byte ptr [rcx+1Ch], 1
0x180017141  jz      short loc_180017169
0x180017143  cmp     byte ptr [rcx+19h], 4
0x180017147  jb      short loc_180017169
0x180017149  mov     eax, dword ptr [rsp+48h+arg_8+4]
0x18001714d  lea     r8, WPP_e06fee0b4bc233e7950f0333fe9fb133_Traceguids
0x180017154  mov     rcx, [rcx+10h]
0x180017158  mov     edx, 11h
0x18001715d  mov     r9d, ebx
0x180017160  mov     [rsp+48h+var_28], eax
0x180017164  call    WPP_SF_DD
0x180017169  mov     rbx, [rsp+48h+arg_10]
0x18001716e  add     rsp, 30h
0x180017172  pop     rdi
0x180017173  pop     rsi
0x180017174  pop     rbp
0x180017175  retn
```
