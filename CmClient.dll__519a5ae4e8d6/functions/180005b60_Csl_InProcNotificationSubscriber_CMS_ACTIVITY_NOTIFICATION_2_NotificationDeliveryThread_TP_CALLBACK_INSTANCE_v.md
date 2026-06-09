# Csl::InProcNotificationSubscriber<_CMS_ACTIVITY_NOTIFICATION,2>::NotificationDeliveryThread(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x180005b60`
- end: `0x180005cfd`
- name: `?NotificationDeliveryThread@?$InProcNotificationSubscriber@U_CMS_ACTIVITY_NOTIFICATION@@$01@Csl@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `413`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x1800048a0`
- `0x180005b60`
- `0x180006f7c`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005b99`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005bef`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005c92`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005b99`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005bef`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180005c92`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005bc8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005c61`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005cb0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005bc8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005c61`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180005cb0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005bbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c17`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005bbd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005c17`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005bd0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180005bd0`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x180005c6b`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x180005c6b`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180005c09`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x180005c09`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005b89`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005b89`

## string_xrefs

- `0x180005cea`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall Csl::InProcNotificationSubscriber<_CMS_ACTIVITY_NOTIFICATION,2>::NotificationDeliveryThread(
        PTP_CALLBACK_INSTANCE Instance,
        _QWORD *Context,
        PTP_WORK Work)
{
  __int64 v3; // rsi
  volatile signed __int32 *v4; // r14
  RTL_SRWLOCK *v5; // rbx
  DWORD LastError; // edi
  const char *v7; // r9
  char v8; // al
  const char *v9; // r9
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v11; // [rsp+58h] [rbp+10h] BYREF
  __int64 v12; // [rsp+68h] [rbp+20h]

  v3 = Context[1];
  v4 = (volatile signed __int32 *)Context[2];
  if ( v4 )
    _InterlockedIncrement(v4 + 2);
  *(_DWORD *)(v3 + 108) = GetCurrentThreadId();
  v5 = (RTL_SRWLOCK *)(v3 + 16);
  AcquireSRWLockExclusive((PSRWLOCK)(v3 + 16));
  while ( *(_QWORD *)(v3 + 80) && !*(_BYTE *)(v3 + 112) )
  {
    if ( v5 )
    {
      LastError = GetLastError();
      ReleaseSRWLockExclusive(v5);
      SetLastError(LastError);
    }
    v12 = 0;
    v11 = 0;
    AcquireSRWLockExclusive((PSRWLOCK)(v3 + 40));
    while ( !*(_QWORD *)(v3 + 80) )
    {
      if ( SleepConditionVariableSRW((PCONDITION_VARIABLE)(v3 + 24), (PSRWLOCK)(v3 + 40), 0, 0) )
      {
        v8 = 0;
      }
      else
      {
        if ( GetLastError() != 1460 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xF46,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v7);
        v8 = 1;
      }
      if ( v8 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xB0,
          (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslBuffer.h",
          v7);
    }
    v11 = *(_QWORD *)(v3 + 8LL * *(_QWORD *)(v3 + 64) + 48);
    *(_QWORD *)(v3 + 64) = ((unsigned __int8)*(_QWORD *)(v3 + 64) - 1) & 1;
    --*(_QWORD *)(v3 + 80);
    if ( v3 != -40 )
      ReleaseSRWLockExclusive((PSRWLOCK)(v3 + 40));
    WakeConditionVariable((PCONDITION_VARIABLE)(v3 + 32));
    try
    {
      (*(void (__fastcall **)(__int64 *, _QWORD))v3)(&v11, *(_QWORD *)(v3 + 8));
    }
    catch ( ... )
    {
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x148,
        (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslNotification.h",
        v9);
    }
    if ( *(_BYTE *)(v3 + 113) )
      goto LABEL_23;
    v5 = (RTL_SRWLOCK *)(v3 + 16);
    AcquireSRWLockExclusive((PSRWLOCK)(v3 + 16));
  }
  *(_DWORD *)(v3 + 108) = -1;
  *(_BYTE *)(v3 + 104) = 0;
  if ( v5 )
    ReleaseSRWLockExclusive(v5);
LABEL_23:
  if ( v4 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v4);
}

```

## disassembly

```asm
0x180005b60  mov     [rsp+arg_0], rbx
0x180005b65  push    rsi
0x180005b66  push    rdi
0x180005b67  push    r14
0x180005b69  sub     rsp, 30h
0x180005b6d  mov     rsi, [rdx+8]
0x180005b71  mov     r14, [rdx+10h]
0x180005b75  mov     [rsp+48h+var_28], rsi
0x180005b7a  mov     [rsp+48h+var_20], r14
0x180005b7f  test    r14, r14
0x180005b82  jz      short loc_180005B89
0x180005b84  lock inc dword ptr [r14+8]
0x180005b89  call    cs:__imp_GetCurrentThreadId
0x180005b8f  mov     [rsi+6Ch], eax
0x180005b92  lea     rbx, [rsi+10h]
0x180005b96  mov     rcx, rbx; SRWLock
0x180005b99  call    cs:__imp_AcquireSRWLockExclusive
0x180005b9f  nop
0x180005ba0  mov     rax, rbx
0x180005ba3  cmp     qword ptr [rsi+50h], 0
0x180005ba8  jz      loc_180005C9D
0x180005bae  cmp     byte ptr [rsi+70h], 0
0x180005bb2  jnz     loc_180005C9D
0x180005bb8  test    rax, rax
0x180005bbb  jz      short loc_180005BD6
0x180005bbd  call    cs:__imp_GetLastError
0x180005bc3  mov     edi, eax
0x180005bc5  mov     rcx, rbx; SRWLock
0x180005bc8  call    cs:__imp_ReleaseSRWLockExclusive
0x180005bce  mov     ecx, edi; dwErrCode
0x180005bd0  call    cs:__imp_SetLastError
0x180005bd6  mov     [rsp+48h+arg_18], 0
0x180005bdf  mov     [rsp+48h+arg_8], 0
0x180005be8  lea     rdi, [rsi+28h]
0x180005bec  mov     rcx, rdi; SRWLock
0x180005bef  call    cs:__imp_AcquireSRWLockExclusive
0x180005bf5  cmp     qword ptr [rsi+50h], 0
0x180005bfa  jnz     short loc_180005C39
0x180005bfc  xor     r9d, r9d; Flags
0x180005bff  xor     r8d, r8d; dwMilliseconds
0x180005c02  mov     rdx, rdi; SRWLock
0x180005c05  lea     rcx, [rsi+18h]; ConditionVariable
0x180005c09  call    cs:__imp_SleepConditionVariableSRW
0x180005c0f  test    eax, eax
0x180005c11  jz      short loc_180005C17
0x180005c13  xor     al, al
0x180005c15  jmp     short loc_180005C2A
0x180005c17  call    cs:__imp_GetLastError
0x180005c1d  cmp     eax, 5B4h
0x180005c22  jnz     loc_180005CE5
0x180005c28  mov     al, 1
0x180005c2a  mov     rcx, [rsp+48h]; this
0x180005c2f  test    al, al
0x180005c31  jnz     loc_180005CD3
0x180005c37  jmp     short loc_180005BF5
0x180005c39  mov     rax, [rsi+40h]
0x180005c3d  mov     rdx, [rsi+rax*8+30h]
0x180005c42  mov     [rsp+48h+arg_8], rdx
0x180005c47  mov     rax, [rsi+40h]
0x180005c4b  dec     rax
0x180005c4e  and     eax, 1
0x180005c51  mov     [rsi+40h], rax
0x180005c55  dec     qword ptr [rsi+50h]
0x180005c59  test    rdi, rdi
0x180005c5c  jz      short loc_180005C67
0x180005c5e  mov     rcx, rdi; SRWLock
0x180005c61  call    cs:__imp_ReleaseSRWLockExclusive
0x180005c67  lea     rcx, [rsi+20h]; ConditionVariable
0x180005c6b  call    cs:__imp_WakeConditionVariable
0x180005c71  mov     rdx, [rsi+8]
0x180005c75  lea     rcx, [rsp+48h+arg_8]
0x180005c7a  mov     rax, [rsi]
0x180005c7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c82  nop
0x180005c83  cmp     byte ptr [rsi+71h], 0
0x180005c87  jz      short loc_180005C8B
0x180005c89  jmp     short loc_180005CB7
0x180005c8b  lea     rbx, [rsi+10h]
0x180005c8f  mov     rcx, rbx; SRWLock
0x180005c92  call    cs:__imp_AcquireSRWLockExclusive
0x180005c98  jmp     loc_180005BA0
0x180005c9d  mov     dword ptr [rsi+6Ch], 0FFFFFFFFh
0x180005ca4  mov     byte ptr [rsi+68h], 0
0x180005ca8  test    rax, rax
0x180005cab  jz      short loc_180005CB7
0x180005cad  mov     rcx, rbx; SRWLock
0x180005cb0  call    cs:__imp_ReleaseSRWLockExclusive
0x180005cb6  nop
0x180005cb7  test    r14, r14
0x180005cba  jz      short loc_180005CC5
0x180005cbc  mov     rcx, r14; this
0x180005cbf  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180005cc4  nop
0x180005cc5  mov     rbx, [rsp+48h+arg_0]
0x180005cca  add     rsp, 30h
0x180005cce  pop     r14
0x180005cd0  pop     rdi
0x180005cd1  pop     rsi
0x180005cd2  retn
0x180005cd3  lea     r8, aOnecoreBaseGen_1; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180005cda  mov     edx, 0B0h; void *
0x180005cdf  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180005ce5  mov     rcx, [rsp+48h]; this
0x180005cea  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180005cf1  mov     edx, 0F46h; void *
0x180005cf6  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
