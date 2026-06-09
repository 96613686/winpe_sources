# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180006ee4`
- end: `0x180006fd4`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `240`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180009044`

## callees

- `0x180003870`
- `0x180006ee4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f40`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f19`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006f40`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006f72`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006f7e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006f72`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006f7e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180006f2e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180006f2e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006f53`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006faa`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006f53`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006faa`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006f6a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006f6a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006f61`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006f61`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::EnsureTimerUnderLock(struct _TP_TIMER **pv)
{
  DWORD LastError; // ebp
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v4; // rsi
  PTP_TIMER v5; // r14
  DWORD v6; // ebx
  struct _TP_TIMER *v7; // rcx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-28h] BYREF

  if ( !*((_BYTE *)pv + 65) )
  {
    if ( !pv[6] )
    {
      LastError = GetLastError();
      ThreadpoolTimer = CreateThreadpoolTimer(
                          (PTP_TIMER_CALLBACK)`wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
                          pv,
                          0);
      v4 = pv[6];
      v5 = ThreadpoolTimer;
      if ( v4 )
      {
        v6 = GetLastError();
        SetThreadpoolTimer(v4, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v4, 1);
        CloseThreadpoolTimer(v4);
        SetLastError(v6);
      }
      pv[6] = v5;
      SetLastError(LastError);
    }
    v7 = pv[6];
    if ( v7 )
    {
      pftDueTime = (struct _FILETIME)-3000000000LL;
      SetThreadpoolTimer(v7, &pftDueTime, 0, 0x124F8u);
      *((_BYTE *)pv + 65) = 1;
    }
  }
}

```

## disassembly

```asm
0x180006ee4  mov     [rsp+arg_8], rbx
0x180006ee9  mov     [rsp+arg_10], rbp
0x180006eee  push    rsi
0x180006eef  push    rdi
0x180006ef0  push    r14
0x180006ef2  sub     rsp, 30h
0x180006ef6  mov     rax, cs:__security_cookie
0x180006efd  xor     rax, rsp
0x180006f00  mov     [rsp+48h+var_20], rax
0x180006f05  cmp     byte ptr [rcx+41h], 0
0x180006f09  mov     rdi, rcx
0x180006f0c  jnz     loc_180006FB4
0x180006f12  cmp     qword ptr [rcx+30h], 0
0x180006f17  jnz     short loc_180006F84
0x180006f19  call    cs:__imp_GetLastError
0x180006f1f  xor     r8d, r8d; pcbe
0x180006f22  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180006f29  mov     rdx, rdi; pv
0x180006f2c  mov     ebp, eax
0x180006f2e  call    cs:__imp_CreateThreadpoolTimer
0x180006f34  mov     rsi, [rdi+30h]
0x180006f38  mov     r14, rax
0x180006f3b  test    rsi, rsi
0x180006f3e  jz      short loc_180006F78
0x180006f40  call    cs:__imp_GetLastError
0x180006f46  xor     r9d, r9d; msWindowLength
0x180006f49  xor     r8d, r8d; msPeriod
0x180006f4c  xor     edx, edx; pftDueTime
0x180006f4e  mov     rcx, rsi; pti
0x180006f51  mov     ebx, eax
0x180006f53  call    cs:__imp_SetThreadpoolTimer
0x180006f59  mov     edx, 1; fCancelPendingCallbacks
0x180006f5e  mov     rcx, rsi; pti
0x180006f61  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180006f67  mov     rcx, rsi; pti
0x180006f6a  call    cs:__imp_CloseThreadpoolTimer
0x180006f70  mov     ecx, ebx; dwErrCode
0x180006f72  call    cs:__imp_SetLastError
0x180006f78  mov     ecx, ebp; dwErrCode
0x180006f7a  mov     [rdi+30h], r14
0x180006f7e  call    cs:__imp_SetLastError
0x180006f84  mov     rcx, [rdi+30h]; pti
0x180006f88  test    rcx, rcx
0x180006f8b  jz      short loc_180006FB4
0x180006f8d  mov     rax, 0FFFFFFFF4D2FA200h
0x180006f97  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x180006f9c  mov     r9d, 124F8h; msWindowLength
0x180006fa2  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x180006fa7  xor     r8d, r8d; msPeriod
0x180006faa  call    cs:__imp_SetThreadpoolTimer
0x180006fb0  mov     byte ptr [rdi+41h], 1
0x180006fb4  mov     rcx, [rsp+48h+var_20]
0x180006fb9  xor     rcx, rsp; StackCookie
0x180006fbc  call    __security_check_cookie
0x180006fc1  mov     rbx, [rsp+48h+arg_8]
0x180006fc6  mov     rbp, [rsp+48h+arg_10]
0x180006fcb  add     rsp, 30h
0x180006fcf  pop     r14
0x180006fd1  pop     rdi
0x180006fd2  pop     rsi
0x180006fd3  retn
```
