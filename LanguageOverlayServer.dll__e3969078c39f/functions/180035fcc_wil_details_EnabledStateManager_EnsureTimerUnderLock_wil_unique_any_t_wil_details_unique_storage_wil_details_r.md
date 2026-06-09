# wil::details::EnabledStateManager::EnsureTimerUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x180035fcc`
- end: `0x1800360bc`
- name: `?EnsureTimerUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `240`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1800372e4`

## callees

- `0x180003a00`
- `0x180035fcc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036001`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036028`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036001`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036028`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003605a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036066`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003605a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180036066`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003603b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180036092`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003603b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180036092`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180036016`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180036016`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180036052`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180036052`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180036049`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180036049`

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
0x180035fcc  mov     [rsp+arg_8], rbx
0x180035fd1  mov     [rsp+arg_10], rbp
0x180035fd6  push    rsi
0x180035fd7  push    rdi
0x180035fd8  push    r14
0x180035fda  sub     rsp, 30h
0x180035fde  mov     rax, cs:__security_cookie
0x180035fe5  xor     rax, rsp
0x180035fe8  mov     [rsp+48h+var_20], rax
0x180035fed  cmp     byte ptr [rcx+18h], 0
0x180035ff1  mov     rdi, rcx
0x180035ff4  jnz     loc_18003609C
0x180035ffa  cmp     qword ptr [rcx+10h], 0
0x180035fff  jnz     short loc_18003606C
0x180036001  call    cs:__imp_GetLastError
0x180036007  xor     r8d, r8d; pcbe
0x18003600a  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180036011  mov     rdx, rdi; pv
0x180036014  mov     ebp, eax
0x180036016  call    cs:__imp_CreateThreadpoolTimer
0x18003601c  mov     rsi, [rdi+10h]
0x180036020  mov     r14, rax
0x180036023  test    rsi, rsi
0x180036026  jz      short loc_180036060
0x180036028  call    cs:__imp_GetLastError
0x18003602e  xor     r9d, r9d; msWindowLength
0x180036031  xor     r8d, r8d; msPeriod
0x180036034  xor     edx, edx; pftDueTime
0x180036036  mov     rcx, rsi; pti
0x180036039  mov     ebx, eax
0x18003603b  call    cs:__imp_SetThreadpoolTimer
0x180036041  mov     edx, 1; fCancelPendingCallbacks
0x180036046  mov     rcx, rsi; pti
0x180036049  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18003604f  mov     rcx, rsi; pti
0x180036052  call    cs:__imp_CloseThreadpoolTimer
0x180036058  mov     ecx, ebx; dwErrCode
0x18003605a  call    cs:__imp_SetLastError
0x180036060  mov     ecx, ebp; dwErrCode
0x180036062  mov     [rdi+10h], r14
0x180036066  call    cs:__imp_SetLastError
0x18003606c  mov     rcx, [rdi+10h]; pti
0x180036070  test    rcx, rcx
0x180036073  jz      short loc_18003609C
0x180036075  mov     rax, 0FFFFFFFF4D2FA200h
0x18003607f  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x180036084  mov     r9d, 124F8h; msWindowLength
0x18003608a  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x18003608f  xor     r8d, r8d; msPeriod
0x180036092  call    cs:__imp_SetThreadpoolTimer
0x180036098  mov     byte ptr [rdi+18h], 1
0x18003609c  mov     rcx, [rsp+48h+var_20]
0x1800360a1  xor     rcx, rsp; StackCookie
0x1800360a4  call    __security_check_cookie
0x1800360a9  mov     rbx, [rsp+48h+arg_8]
0x1800360ae  mov     rbp, [rsp+48h+arg_10]
0x1800360b3  add     rsp, 30h
0x1800360b7  pop     r14
0x1800360b9  pop     rdi
0x1800360ba  pop     rsi
0x1800360bb  retn
```
