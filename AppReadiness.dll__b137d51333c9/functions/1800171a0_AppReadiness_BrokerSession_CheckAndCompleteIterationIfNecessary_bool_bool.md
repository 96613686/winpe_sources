# AppReadiness::BrokerSession::CheckAndCompleteIterationIfNecessary(bool,bool *)

- ea: `0x1800171a0`
- end: `0x1800173be`
- name: `?CheckAndCompleteIterationIfNecessary@BrokerSession@AppReadiness@@QEAAX_NPEA_N@Z`
- size: `542`
- prototype: `void __fastcall(AppReadiness::BrokerSession *__hidden this, bool, bool *)`
- caller_count: `3`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18000c750`
- `0x1800266f8`
- `0x180061ab0`

## callees

- `0x1800148b0`
- `0x1800171a0`
- `0x1800173c4`
- `0x18002639c`
- `0x180026954`
- `0x18002a970`
- `0x180038f14`
- `0x18003e210`
- `0x180079010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017232`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017391`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017232`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180017391`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800171de`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800171de`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180017349`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180017349`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall AppReadiness::BrokerSession::CheckAndCompleteIterationIfNecessary(
        AppReadiness::BrokerSession *this,
        char a2,
        bool *a3)
{
  __int64 v6; // rcx
  _BYTE *v7; // rdi
  char v8; // r15
  char v9; // r13
  _QWORD *v10; // rdx
  bool v11; // [rsp+40h] [rbp-49h] BYREF
  PSRWLOCK SRWLock; // [rsp+48h] [rbp-41h] BYREF
  int v13; // [rsp+51h] [rbp-38h]
  __int16 v14; // [rsp+55h] [rbp-34h]
  char v15; // [rsp+57h] [rbp-32h]
  _QWORD v16[2]; // [rsp+60h] [rbp-29h] BYREF
  char v17; // [rsp+70h] [rbp-19h]
  int v18; // [rsp+71h] [rbp-18h]
  __int16 v19; // [rsp+75h] [rbp-14h]
  char v20; // [rsp+77h] [rbp-12h]
  _QWORD *v21; // [rsp+98h] [rbp+Fh]

  if ( a3 )
    *a3 = 0;
  AcquireSRWLockExclusive((PSRWLOCK)this);
  SRWLock = (PSRWLOCK)this;
  v7 = (char *)this + 51;
  if ( *((_QWORD *)this + 1) == *((_QWORD *)this + 2) && !*v7 || a2 )
  {
    v8 = 1;
    v9 = *((_DWORD *)this + 13) == 0;
    if ( !*v7 && a2 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v6);
    *v7 = 1;
  }
  else
  {
    v8 = 0;
    v9 = 0;
  }
  if ( this )
    ReleaseSRWLockExclusive((PSRWLOCK)this);
  if ( v8 )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_a1c8be1db95b3070d34fb44c5344dbe6_Traceguids);
    v11 = 0;
    AppReadiness::BrokerSession::CheckIfBISessionStarted(this, &v11);
    if ( v11 )
    {
      v16[0] = off_18007C320;
      v16[1] = this;
      v17 = v9;
      v18 = v13;
      v19 = v14;
      v20 = v15;
      v21 = v16;
      AppReadiness::User::ExecuteUnderContext(*((_QWORD *)this + 4), (__int64)v16);
      if ( v21 )
      {
        v10 = v16;
        LOBYTE(v10) = v21 != v16;
        (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v21 + 32LL))(v21, v10);
      }
      if ( a3 )
        *a3 = 1;
      AppReadiness::BrokerSession::CheckAndClearUpgradeOrPBRSession(this, v9);
    }
    else
    {
      *((_BYTE *)this + 49) = 1;
      Microsoft::WRL::Wrappers::SRWLock::LockExclusive(&SRWLock, this);
      if ( !*((_QWORD *)this + 5) )
        CreateTimerQueueTimer(
          (PHANDLE)this + 5,
          0,
          AppReadiness::BrokerSession::OnCompleteIteration,
          this,
          0x7530u,
          0,
          8u);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 11, WPP_a1c8be1db95b3070d34fb44c5344dbe6_Traceguids);
      if ( SRWLock )
        ReleaseSRWLockExclusive(SRWLock);
    }
  }
}

```

## disassembly

```asm
0x1800171a0  mov     [rsp-8+arg_8], rbx
0x1800171a5  push    rbp
0x1800171a6  push    rsi
0x1800171a7  push    rdi
0x1800171a8  push    r12
0x1800171aa  push    r13
0x1800171ac  push    r14
0x1800171ae  push    r15
0x1800171b0  lea     rbp, [rsp-27h]
0x1800171b5  sub     rsp, 0B0h
0x1800171bc  mov     rax, cs:__security_cookie
0x1800171c3  xor     rax, rsp
0x1800171c6  mov     [rbp+57h+var_40], rax
0x1800171ca  mov     r14, r8
0x1800171cd  mov     r12b, dl
0x1800171d0  mov     rbx, rcx
0x1800171d3  xor     r13d, r13d
0x1800171d6  test    r8, r8
0x1800171d9  jz      short loc_1800171DE
0x1800171db  mov     [r8], r13b
0x1800171de  call    cs:__imp_AcquireSRWLockExclusive
0x1800171e4  mov     [rbp+57h+SRWLock], rbx
0x1800171e8  mov     rax, [rbx+10h]
0x1800171ec  mov     esi, 1
0x1800171f1  lea     rdi, [rbx+33h]
0x1800171f5  cmp     [rbx+8], rax
0x1800171f9  jnz     short loc_180017200
0x1800171fb  cmp     [rdi], r13b
0x1800171fe  jz      short loc_18001720D
0x180017200  test    r12b, r12b
0x180017203  jnz     short loc_18001720D
0x180017205  xor     r15b, r15b
0x180017208  xor     r13b, r13b
0x18001720b  jmp     short loc_18001722A
0x18001720d  mov     r15b, sil
0x180017210  cmp     [rbx+34h], r13d
0x180017214  setz    r13b
0x180017218  cmp     byte ptr [rdi], 0
0x18001721b  jnz     short loc_180017227
0x18001721d  test    r12b, r12b
0x180017220  jz      short loc_180017227
0x180017222  call    MicrosoftTelemetryAssertTriggeredNoArgs; __annotation("Debug", "TelemetryAssert", "m_complete || !forceRun")
0x180017227  mov     [rdi], sil
0x18001722a  test    rbx, rbx
0x18001722d  jz      short loc_180017238
0x18001722f  mov     rcx, rbx; SRWLock
0x180017232  call    cs:__imp_ReleaseSRWLockExclusive
0x180017238  test    r15b, r15b
0x18001723b  jz      loc_180017397
0x180017241  lea     rdi, WPP_GLOBAL_Control
0x180017248  mov     rcx, cs:WPP_GLOBAL_Control
0x18001724f  cmp     rcx, rdi
0x180017252  jz      short loc_180017281
0x180017254  test    byte ptr [rcx+1Ch], 4
0x180017258  jz      short loc_180017281
0x18001725a  mov     r9, [rbx+20h]
0x18001725e  add     r9, 40h ; '@'
0x180017262  cmp     qword ptr [r9+18h], 7
0x180017267  jbe     short loc_18001726C
0x180017269  mov     r9, [r9]
0x18001726c  mov     edx, 0Ah
0x180017271  lea     r8, WPP_a1c8be1db95b3070d34fb44c5344dbe6_Traceguids
0x180017278  mov     rcx, [rcx+10h]
0x18001727c  call    WPP_SF_S
0x180017281  mov     [rbp+57h+var_A0], 0
0x180017285  lea     rdx, [rbp+57h+var_A0]; bool *
0x180017289  mov     rcx, rbx; this
0x18001728c  call    ?CheckIfBISessionStarted@BrokerSession@AppReadiness@@AEAAXPEA_N@Z; AppReadiness::BrokerSession::CheckIfBISessionStarted(bool *)
0x180017291  cmp     [rbp+57h+var_A0], 0
0x180017295  jz      short loc_18001730B
0x180017297  lea     rax, off_18007C320
0x18001729e  mov     [rbp+57h+var_80], rax
0x1800172a2  mov     [rbp+57h+var_78], rbx
0x1800172a6  mov     [rbp+57h+var_70], r13b
0x1800172aa  mov     eax, [rbp+57h+var_8F]
0x1800172ad  mov     [rbp+57h+var_6F], eax
0x1800172b0  movzx   eax, [rbp+57h+var_8B]
0x1800172b4  mov     [rbp+57h+var_6B], ax
0x1800172b8  mov     al, [rbp+57h+var_89]
0x1800172bb  mov     [rbp+57h+var_69], al
0x1800172be  lea     rax, [rbp+57h+var_80]
0x1800172c2  mov     [rbp+57h+var_48], rax
0x1800172c6  lea     rdx, [rbp+57h+var_80]
0x1800172ca  mov     rcx, [rbx+20h]
0x1800172ce  call    ?ExecuteUnderContext@User@AppReadiness@@QEAAJAEBV?$function@$$A6AXXZ@std@@@Z; AppReadiness::User::ExecuteUnderContext(std::function<void (void)> const &)
0x1800172d3  nop
0x1800172d4  mov     rcx, [rbp+57h+var_48]
0x1800172d8  test    rcx, rcx
0x1800172db  jz      short loc_1800172F3
0x1800172dd  mov     rax, [rcx]
0x1800172e0  lea     rdx, [rbp+57h+var_80]
0x1800172e4  cmp     rcx, rdx
0x1800172e7  setnz   dl
0x1800172ea  mov     rax, [rax+20h]
0x1800172ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800172f3  test    r14, r14
0x1800172f6  jz      short loc_1800172FB
0x1800172f8  mov     [r14], sil
0x1800172fb  mov     dl, r13b; bool
0x1800172fe  mov     rcx, rbx; this
0x180017301  call    ?CheckAndClearUpgradeOrPBRSession@BrokerSession@AppReadiness@@AEAAX_N@Z; AppReadiness::BrokerSession::CheckAndClearUpgradeOrPBRSession(bool)
0x180017306  jmp     loc_180017397
0x18001730b  xchg    sil, [rbx+31h]
0x18001730f  mov     rdx, rbx
0x180017312  lea     rcx, [rbp+57h+SRWLock]
0x180017316  call    ?LockExclusive@SRWLock@Wrappers@WRL@Microsoft@@SA?AVSyncLockExclusive@Details@234@PEAU_RTL_SRWLOCK@@@Z; Microsoft::WRL::Wrappers::SRWLock::LockExclusive(_RTL_SRWLOCK *)
0x18001731b  lea     rcx, [rbx+28h]; phNewTimer
0x18001731f  cmp     qword ptr [rcx], 0
0x180017323  jnz     short loc_18001734F
0x180017325  mov     [rsp+0E0h+Flags], 8; Flags
0x18001732d  mov     [rsp+0E0h+Period], 0; Period
0x180017335  mov     [rsp+0E0h+DueTime], 7530h; DueTime
0x18001733d  mov     r9, rbx; Parameter
0x180017340  lea     r8, ?OnCompleteIteration@BrokerSession@AppReadiness@@CAXPEAXE@Z; Callback
0x180017347  xor     edx, edx; TimerQueue
0x180017349  call    cs:__imp_CreateTimerQueueTimer
0x18001734f  mov     rcx, cs:WPP_GLOBAL_Control
0x180017356  cmp     rcx, rdi
0x180017359  jz      short loc_180017388
0x18001735b  test    byte ptr [rcx+1Ch], 4
0x18001735f  jz      short loc_180017388
0x180017361  mov     r9, [rbx+20h]
0x180017365  add     r9, 40h ; '@'
0x180017369  cmp     qword ptr [r9+18h], 7
0x18001736e  jbe     short loc_180017373
0x180017370  mov     r9, [r9]
0x180017373  mov     edx, 0Bh
0x180017378  lea     r8, WPP_a1c8be1db95b3070d34fb44c5344dbe6_Traceguids
0x18001737f  mov     rcx, [rcx+10h]
0x180017383  call    WPP_SF_S
0x180017388  mov     rcx, [rbp+57h+SRWLock]; SRWLock
0x18001738c  test    rcx, rcx
0x18001738f  jz      short loc_180017397
0x180017391  call    cs:__imp_ReleaseSRWLockExclusive
0x180017397  mov     rcx, [rbp+57h+var_40]
0x18001739b  xor     rcx, rsp; StackCookie
0x18001739e  call    __security_check_cookie
0x1800173a3  mov     rbx, [rsp+0E0h+arg_8]
0x1800173ab  add     rsp, 0B0h
0x1800173b2  pop     r15
0x1800173b4  pop     r14
0x1800173b6  pop     r13
0x1800173b8  pop     r12
0x1800173ba  pop     rdi
0x1800173bb  pop     rsi
0x1800173bc  pop     rbp
0x1800173bd  retn
```
