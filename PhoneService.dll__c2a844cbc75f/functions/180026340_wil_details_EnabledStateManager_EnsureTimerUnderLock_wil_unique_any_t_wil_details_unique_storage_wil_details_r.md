# wil::details::EnabledStateManager::EnsureTimerUnderLock(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>> const &)

- ea: `0x180026340`
- end: `0x180026430`
- name: `?EnsureTimerUnderLock@EnabledStateManager@details@wil@@AEAAXAEBV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@@Z`
- size: `240`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x18002ffe8`

## callees

- `0x180026340`
- `0x18008d9b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800263ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800263da`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800263ce`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800263da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026375`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002639c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026375`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002639c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800263af`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180026406`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800263af`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180026406`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800263c6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800263c6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800263bd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800263bd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002638a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18002638a`

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
0x180026340  mov     [rsp+arg_8], rbx
0x180026345  mov     [rsp+arg_10], rbp
0x18002634a  push    rsi
0x18002634b  push    rdi
0x18002634c  push    r14
0x18002634e  sub     rsp, 30h
0x180026352  mov     rax, cs:__security_cookie
0x180026359  xor     rax, rsp
0x18002635c  mov     [rsp+48h+var_20], rax
0x180026361  cmp     byte ptr [rcx+18h], 0
0x180026365  mov     rdi, rcx
0x180026368  jnz     loc_180026410
0x18002636e  cmp     qword ptr [rcx+10h], 0
0x180026373  jnz     short loc_1800263E0
0x180026375  call    cs:__imp_GetLastError
0x18002637b  xor     r8d, r8d; pcbe
0x18002637e  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_0374aa0a5d1201b2358c6bce99369c58_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180026385  mov     rdx, rdi; pv
0x180026388  mov     ebp, eax
0x18002638a  call    cs:__imp_CreateThreadpoolTimer
0x180026390  mov     rsi, [rdi+10h]
0x180026394  mov     r14, rax
0x180026397  test    rsi, rsi
0x18002639a  jz      short loc_1800263D4
0x18002639c  call    cs:__imp_GetLastError
0x1800263a2  xor     r9d, r9d; msWindowLength
0x1800263a5  xor     r8d, r8d; msPeriod
0x1800263a8  xor     edx, edx; pftDueTime
0x1800263aa  mov     rcx, rsi; pti
0x1800263ad  mov     ebx, eax
0x1800263af  call    cs:__imp_SetThreadpoolTimer
0x1800263b5  mov     edx, 1; fCancelPendingCallbacks
0x1800263ba  mov     rcx, rsi; pti
0x1800263bd  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800263c3  mov     rcx, rsi; pti
0x1800263c6  call    cs:__imp_CloseThreadpoolTimer
0x1800263cc  mov     ecx, ebx; dwErrCode
0x1800263ce  call    cs:__imp_SetLastError
0x1800263d4  mov     ecx, ebp; dwErrCode
0x1800263d6  mov     [rdi+10h], r14
0x1800263da  call    cs:__imp_SetLastError
0x1800263e0  mov     rcx, [rdi+10h]; pti
0x1800263e4  test    rcx, rcx
0x1800263e7  jz      short loc_180026410
0x1800263e9  mov     rax, 0FFFFFFFF4D2FA200h
0x1800263f3  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x1800263f8  mov     r9d, 124F8h; msWindowLength
0x1800263fe  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x180026403  xor     r8d, r8d; msPeriod
0x180026406  call    cs:__imp_SetThreadpoolTimer
0x18002640c  mov     byte ptr [rdi+18h], 1
0x180026410  mov     rcx, [rsp+48h+var_20]
0x180026415  xor     rcx, rsp; StackCookie
0x180026418  call    __security_check_cookie
0x18002641d  mov     rbx, [rsp+48h+arg_8]
0x180026422  mov     rbp, [rsp+48h+arg_10]
0x180026427  add     rsp, 30h
0x18002642b  pop     r14
0x18002642d  pop     rdi
0x18002642e  pop     rsi
0x18002642f  retn
```
