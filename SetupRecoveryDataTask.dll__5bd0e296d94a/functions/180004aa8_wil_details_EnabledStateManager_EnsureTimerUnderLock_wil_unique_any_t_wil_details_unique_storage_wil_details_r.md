# wil::details::EnabledStateManager::EnsureTimerUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x180004aa8`
- end: `0x180004b98`
- name: `?EnsureTimerUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `240`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180008784`

## callees

- `0x180004aa8`
- `0x18000c610`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004add`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004add`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b04`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004b36`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004b42`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004b36`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004b42`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004b25`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004b25`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004b2e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004b2e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180004af2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180004af2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004b17`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004b6e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004b17`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004b6e`

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
0x180004aa8  mov     [rsp+arg_8], rbx
0x180004aad  mov     [rsp+arg_10], rbp
0x180004ab2  push    rsi
0x180004ab3  push    rdi
0x180004ab4  push    r14
0x180004ab6  sub     rsp, 30h
0x180004aba  mov     rax, cs:__security_cookie
0x180004ac1  xor     rax, rsp
0x180004ac4  mov     [rsp+48h+var_20], rax
0x180004ac9  cmp     byte ptr [rcx+18h], 0
0x180004acd  mov     rdi, rcx
0x180004ad0  jnz     loc_180004B78
0x180004ad6  cmp     qword ptr [rcx+10h], 0
0x180004adb  jnz     short loc_180004B48
0x180004add  call    cs:__imp_GetLastError
0x180004ae3  xor     r8d, r8d; pcbe
0x180004ae6  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180004aed  mov     rdx, rdi; pv
0x180004af0  mov     ebp, eax
0x180004af2  call    cs:__imp_CreateThreadpoolTimer
0x180004af8  mov     rsi, [rdi+10h]
0x180004afc  mov     r14, rax
0x180004aff  test    rsi, rsi
0x180004b02  jz      short loc_180004B3C
0x180004b04  call    cs:__imp_GetLastError
0x180004b0a  xor     r9d, r9d; msWindowLength
0x180004b0d  xor     r8d, r8d; msPeriod
0x180004b10  xor     edx, edx; pftDueTime
0x180004b12  mov     rcx, rsi; pti
0x180004b15  mov     ebx, eax
0x180004b17  call    cs:__imp_SetThreadpoolTimer
0x180004b1d  mov     edx, 1; fCancelPendingCallbacks
0x180004b22  mov     rcx, rsi; pti
0x180004b25  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004b2b  mov     rcx, rsi; pti
0x180004b2e  call    cs:__imp_CloseThreadpoolTimer
0x180004b34  mov     ecx, ebx; dwErrCode
0x180004b36  call    cs:__imp_SetLastError
0x180004b3c  mov     ecx, ebp; dwErrCode
0x180004b3e  mov     [rdi+10h], r14
0x180004b42  call    cs:__imp_SetLastError
0x180004b48  mov     rcx, [rdi+10h]; pti
0x180004b4c  test    rcx, rcx
0x180004b4f  jz      short loc_180004B78
0x180004b51  mov     rax, 0FFFFFFFF4D2FA200h
0x180004b5b  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x180004b60  mov     r9d, 124F8h; msWindowLength
0x180004b66  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x180004b6b  xor     r8d, r8d; msPeriod
0x180004b6e  call    cs:__imp_SetThreadpoolTimer
0x180004b74  mov     byte ptr [rdi+18h], 1
0x180004b78  mov     rcx, [rsp+48h+var_20]
0x180004b7d  xor     rcx, rsp; StackCookie
0x180004b80  call    __security_check_cookie
0x180004b85  mov     rbx, [rsp+48h+arg_8]
0x180004b8a  mov     rbp, [rsp+48h+arg_10]
0x180004b8f  add     rsp, 30h
0x180004b93  pop     r14
0x180004b95  pop     rdi
0x180004b96  pop     rsi
0x180004b97  retn
```
