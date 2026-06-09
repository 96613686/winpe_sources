# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x1800046bc`
- end: `0x180004790`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180006804`

## callees

- `0x1800046bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004709`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800046e2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004709`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000473b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004747`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000473b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004747`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004733`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004733`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000472a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000472a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000471c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004773`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000471c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004773`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800046f7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800046f7`

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
  struct _FILETIME pftDueTime; // [rsp+40h] [rbp+8h] BYREF

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
0x1800046bc  mov     [rsp+arg_8], rbx
0x1800046c1  mov     [rsp+arg_10], rbp
0x1800046c6  push    rsi
0x1800046c7  push    rdi
0x1800046c8  push    r14
0x1800046ca  sub     rsp, 20h
0x1800046ce  cmp     byte ptr [rcx+41h], 0
0x1800046d2  mov     rdi, rcx
0x1800046d5  jnz     loc_18000477D
0x1800046db  cmp     qword ptr [rcx+30h], 0
0x1800046e0  jnz     short loc_18000474D
0x1800046e2  call    cs:__imp_GetLastError
0x1800046e8  xor     r8d, r8d; pcbe
0x1800046eb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800046f2  mov     rdx, rdi; pv
0x1800046f5  mov     ebp, eax
0x1800046f7  call    cs:__imp_CreateThreadpoolTimer
0x1800046fd  mov     rsi, [rdi+30h]
0x180004701  mov     r14, rax
0x180004704  test    rsi, rsi
0x180004707  jz      short loc_180004741
0x180004709  call    cs:__imp_GetLastError
0x18000470f  xor     r9d, r9d; msWindowLength
0x180004712  xor     r8d, r8d; msPeriod
0x180004715  xor     edx, edx; pftDueTime
0x180004717  mov     rcx, rsi; pti
0x18000471a  mov     ebx, eax
0x18000471c  call    cs:__imp_SetThreadpoolTimer
0x180004722  mov     edx, 1; fCancelPendingCallbacks
0x180004727  mov     rcx, rsi; pti
0x18000472a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004730  mov     rcx, rsi; pti
0x180004733  call    cs:__imp_CloseThreadpoolTimer
0x180004739  mov     ecx, ebx; dwErrCode
0x18000473b  call    cs:__imp_SetLastError
0x180004741  mov     ecx, ebp; dwErrCode
0x180004743  mov     [rdi+30h], r14
0x180004747  call    cs:__imp_SetLastError
0x18000474d  mov     rcx, [rdi+30h]; pti
0x180004751  test    rcx, rcx
0x180004754  jz      short loc_18000477D
0x180004756  mov     rax, 0FFFFFFFF4D2FA200h
0x180004760  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180004765  mov     r9d, 124F8h; msWindowLength
0x18000476b  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180004770  xor     r8d, r8d; msPeriod
0x180004773  call    cs:__imp_SetThreadpoolTimer
0x180004779  mov     byte ptr [rdi+41h], 1
0x18000477d  mov     rbx, [rsp+38h+arg_8]
0x180004782  mov     rbp, [rsp+38h+arg_10]
0x180004787  add     rsp, 20h
0x18000478b  pop     r14
0x18000478d  pop     rdi
0x18000478e  pop     rsi
0x18000478f  retn
```
