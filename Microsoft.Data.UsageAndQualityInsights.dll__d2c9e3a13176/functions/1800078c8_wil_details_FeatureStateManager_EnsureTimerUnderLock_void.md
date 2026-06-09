# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x1800078c8`
- end: `0x18000799c`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180009784`

## callees

- `0x1800078c8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800078ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007915`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800078ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007915`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007947`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007953`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007947`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007953`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000793f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000793f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007928`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000797f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007928`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000797f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180007903`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180007903`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007936`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007936`

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
                          `wil::details::EnsureCoalescedTimer<wil::details::FeatureStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
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
0x1800078c8  mov     [rsp+arg_8], rbx
0x1800078cd  mov     [rsp+arg_10], rbp
0x1800078d2  push    rsi
0x1800078d3  push    rdi
0x1800078d4  push    r14
0x1800078d6  sub     rsp, 20h
0x1800078da  cmp     byte ptr [rcx+41h], 0
0x1800078de  mov     rdi, rcx
0x1800078e1  jnz     loc_180007989
0x1800078e7  cmp     qword ptr [rcx+30h], 0
0x1800078ec  jnz     short loc_180007959
0x1800078ee  call    cs:__imp_GetLastError
0x1800078f4  xor     r8d, r8d; pcbe
0x1800078f7  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800078fe  mov     rdx, rdi; pv
0x180007901  mov     ebp, eax
0x180007903  call    cs:__imp_CreateThreadpoolTimer
0x180007909  mov     rsi, [rdi+30h]
0x18000790d  mov     r14, rax
0x180007910  test    rsi, rsi
0x180007913  jz      short loc_18000794D
0x180007915  call    cs:__imp_GetLastError
0x18000791b  xor     r9d, r9d; msWindowLength
0x18000791e  xor     r8d, r8d; msPeriod
0x180007921  xor     edx, edx; pftDueTime
0x180007923  mov     rcx, rsi; pti
0x180007926  mov     ebx, eax
0x180007928  call    cs:__imp_SetThreadpoolTimer
0x18000792e  mov     edx, 1; fCancelPendingCallbacks
0x180007933  mov     rcx, rsi; pti
0x180007936  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000793c  mov     rcx, rsi; pti
0x18000793f  call    cs:__imp_CloseThreadpoolTimer
0x180007945  mov     ecx, ebx; dwErrCode
0x180007947  call    cs:__imp_SetLastError
0x18000794d  mov     ecx, ebp; dwErrCode
0x18000794f  mov     [rdi+30h], r14
0x180007953  call    cs:__imp_SetLastError
0x180007959  mov     rcx, [rdi+30h]; pti
0x18000795d  test    rcx, rcx
0x180007960  jz      short loc_180007989
0x180007962  mov     rax, 0FFFFFFFF4D2FA200h
0x18000796c  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180007971  mov     r9d, 124F8h; msWindowLength
0x180007977  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x18000797c  xor     r8d, r8d; msPeriod
0x18000797f  call    cs:__imp_SetThreadpoolTimer
0x180007985  mov     byte ptr [rdi+41h], 1
0x180007989  mov     rbx, [rsp+38h+arg_8]
0x18000798e  mov     rbp, [rsp+38h+arg_10]
0x180007993  add     rsp, 20h
0x180007997  pop     r14
0x180007999  pop     rdi
0x18000799a  pop     rsi
0x18000799b  retn
```
