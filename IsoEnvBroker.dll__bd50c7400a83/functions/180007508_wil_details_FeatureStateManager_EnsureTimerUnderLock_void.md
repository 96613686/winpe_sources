# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180007508`
- end: `0x1800075dc`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800093c4`

## callees

- `0x180007508`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000752e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007555`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000752e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007555`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007587`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007593`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007587`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007593`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007568`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800075bf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007568`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800075bf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000757f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000757f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007576`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007576`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180007543`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180007543`

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
0x180007508  mov     [rsp+arg_8], rbx
0x18000750d  mov     [rsp+arg_10], rbp
0x180007512  push    rsi
0x180007513  push    rdi
0x180007514  push    r14
0x180007516  sub     rsp, 20h
0x18000751a  cmp     byte ptr [rcx+41h], 0
0x18000751e  mov     rdi, rcx
0x180007521  jnz     loc_1800075C9
0x180007527  cmp     qword ptr [rcx+30h], 0
0x18000752c  jnz     short loc_180007599
0x18000752e  call    cs:__imp_GetLastError
0x180007534  xor     r8d, r8d; pcbe
0x180007537  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000753e  mov     rdx, rdi; pv
0x180007541  mov     ebp, eax
0x180007543  call    cs:__imp_CreateThreadpoolTimer
0x180007549  mov     rsi, [rdi+30h]
0x18000754d  mov     r14, rax
0x180007550  test    rsi, rsi
0x180007553  jz      short loc_18000758D
0x180007555  call    cs:__imp_GetLastError
0x18000755b  xor     r9d, r9d; msWindowLength
0x18000755e  xor     r8d, r8d; msPeriod
0x180007561  xor     edx, edx; pftDueTime
0x180007563  mov     rcx, rsi; pti
0x180007566  mov     ebx, eax
0x180007568  call    cs:__imp_SetThreadpoolTimer
0x18000756e  mov     edx, 1; fCancelPendingCallbacks
0x180007573  mov     rcx, rsi; pti
0x180007576  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000757c  mov     rcx, rsi; pti
0x18000757f  call    cs:__imp_CloseThreadpoolTimer
0x180007585  mov     ecx, ebx; dwErrCode
0x180007587  call    cs:__imp_SetLastError
0x18000758d  mov     ecx, ebp; dwErrCode
0x18000758f  mov     [rdi+30h], r14
0x180007593  call    cs:__imp_SetLastError
0x180007599  mov     rcx, [rdi+30h]; pti
0x18000759d  test    rcx, rcx
0x1800075a0  jz      short loc_1800075C9
0x1800075a2  mov     rax, 0FFFFFFFF4D2FA200h
0x1800075ac  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x1800075b1  mov     r9d, 124F8h; msWindowLength
0x1800075b7  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x1800075bc  xor     r8d, r8d; msPeriod
0x1800075bf  call    cs:__imp_SetThreadpoolTimer
0x1800075c5  mov     byte ptr [rdi+41h], 1
0x1800075c9  mov     rbx, [rsp+38h+arg_8]
0x1800075ce  mov     rbp, [rsp+38h+arg_10]
0x1800075d3  add     rsp, 20h
0x1800075d7  pop     r14
0x1800075d9  pop     rdi
0x1800075da  pop     rsi
0x1800075db  retn
```
