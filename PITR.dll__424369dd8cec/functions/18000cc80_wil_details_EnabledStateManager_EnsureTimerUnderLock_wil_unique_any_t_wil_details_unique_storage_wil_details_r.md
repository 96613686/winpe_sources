# wil::details::EnabledStateManager::EnsureTimerUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x18000cc80`
- end: `0x18000cd70`
- name: `?EnsureTimerUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `240`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18001585c`

## callees

- `0x18000cc80`
- `0x180050300`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cd0e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cd1a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cd0e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000cd1a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ccb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ccdc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ccb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ccdc`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ccfd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ccfd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000ccca`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000ccca`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000cd06`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000cd06`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ccef`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000cd46`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ccef`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000cd46`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::EnsureTimerUnderLock(struct _TP_TIMER **pv)
{
  DWORD LastError; // ebp
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v4; // rsi
  PTP_TIMER v5; // r14
  DWORD v6; // ebx
  struct _TP_TIMER *v7; // rcx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-28h] BYREF

  if ( !*((_BYTE *)pv + 24) )
  {
    if ( !pv[2] )
    {
      LastError = GetLastError();
      ThreadpoolTimer = CreateThreadpoolTimer(_lambda_0374aa0a5d1201b2358c6bce99369c58_::_lambda_invoker_cdecl_, pv, 0);
      v4 = pv[2];
      v5 = ThreadpoolTimer;
      if ( v4 )
      {
        v6 = GetLastError();
        SetThreadpoolTimer(v4, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v4, 1);
        CloseThreadpoolTimer(v4);
        SetLastError(v6);
      }
      pv[2] = v5;
      SetLastError(LastError);
    }
    v7 = pv[2];
    if ( v7 )
    {
      pftDueTime = (struct _FILETIME)-3000000000LL;
      SetThreadpoolTimer(v7, &pftDueTime, 0, 0x124F8u);
      *((_BYTE *)pv + 24) = 1;
    }
  }
}

```

## disassembly

```asm
0x18000cc80  mov     [rsp+arg_8], rbx
0x18000cc85  mov     [rsp+arg_10], rbp
0x18000cc8a  push    rsi
0x18000cc8b  push    rdi
0x18000cc8c  push    r14
0x18000cc8e  sub     rsp, 30h
0x18000cc92  mov     rax, cs:__security_cookie
0x18000cc99  xor     rax, rsp
0x18000cc9c  mov     [rsp+48h+var_20], rax
0x18000cca1  cmp     byte ptr [rcx+18h], 0
0x18000cca5  mov     rdi, rcx
0x18000cca8  jnz     loc_18000CD50
0x18000ccae  cmp     qword ptr [rcx+10h], 0
0x18000ccb3  jnz     short loc_18000CD20
0x18000ccb5  call    cs:__imp_GetLastError
0x18000ccbb  xor     r8d, r8d; pcbe
0x18000ccbe  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000ccc5  mov     rdx, rdi; pv
0x18000ccc8  mov     ebp, eax
0x18000ccca  call    cs:__imp_CreateThreadpoolTimer
0x18000ccd0  mov     rsi, [rdi+10h]
0x18000ccd4  mov     r14, rax
0x18000ccd7  test    rsi, rsi
0x18000ccda  jz      short loc_18000CD14
0x18000ccdc  call    cs:__imp_GetLastError
0x18000cce2  xor     r9d, r9d; msWindowLength
0x18000cce5  xor     r8d, r8d; msPeriod
0x18000cce8  xor     edx, edx; pftDueTime
0x18000ccea  mov     rcx, rsi; pti
0x18000cced  mov     ebx, eax
0x18000ccef  call    cs:__imp_SetThreadpoolTimer
0x18000ccf5  mov     edx, 1; fCancelPendingCallbacks
0x18000ccfa  mov     rcx, rsi; pti
0x18000ccfd  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000cd03  mov     rcx, rsi; pti
0x18000cd06  call    cs:__imp_CloseThreadpoolTimer
0x18000cd0c  mov     ecx, ebx; dwErrCode
0x18000cd0e  call    cs:__imp_SetLastError
0x18000cd14  mov     ecx, ebp; dwErrCode
0x18000cd16  mov     [rdi+10h], r14
0x18000cd1a  call    cs:__imp_SetLastError
0x18000cd20  mov     rcx, [rdi+10h]; pti
0x18000cd24  test    rcx, rcx
0x18000cd27  jz      short loc_18000CD50
0x18000cd29  mov     rax, 0FFFFFFFF4D2FA200h
0x18000cd33  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x18000cd38  mov     r9d, 124F8h; msWindowLength
0x18000cd3e  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x18000cd43  xor     r8d, r8d; msPeriod
0x18000cd46  call    cs:__imp_SetThreadpoolTimer
0x18000cd4c  mov     byte ptr [rdi+18h], 1
0x18000cd50  mov     rcx, [rsp+48h+var_20]
0x18000cd55  xor     rcx, rsp; StackCookie
0x18000cd58  call    __security_check_cookie
0x18000cd5d  mov     rbx, [rsp+48h+arg_8]
0x18000cd62  mov     rbp, [rsp+48h+arg_10]
0x18000cd67  add     rsp, 30h
0x18000cd6b  pop     r14
0x18000cd6d  pop     rdi
0x18000cd6e  pop     rsi
0x18000cd6f  retn
```
