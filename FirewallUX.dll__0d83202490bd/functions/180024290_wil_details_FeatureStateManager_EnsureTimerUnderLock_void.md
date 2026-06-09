# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180024290`
- end: `0x180024364`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180024ab4`

## callees

- `0x180024290`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002430f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002431b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002430f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002431b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800242b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800242dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800242b6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800242dd`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800242fe`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800242fe`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800242cb`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800242cb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180024307`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180024307`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800242f0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180024347`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800242f0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180024347`

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
0x180024290  mov     [rsp+arg_8], rbx
0x180024295  mov     [rsp+arg_10], rbp
0x18002429a  push    rsi
0x18002429b  push    rdi
0x18002429c  push    r14
0x18002429e  sub     rsp, 20h
0x1800242a2  cmp     byte ptr [rcx+41h], 0
0x1800242a6  mov     rdi, rcx
0x1800242a9  jnz     loc_180024351
0x1800242af  cmp     qword ptr [rcx+30h], 0
0x1800242b4  jnz     short loc_180024321
0x1800242b6  call    cs:__imp_GetLastError
0x1800242bc  xor     r8d, r8d; pcbe
0x1800242bf  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800242c6  mov     rdx, rdi; pv
0x1800242c9  mov     ebp, eax
0x1800242cb  call    cs:__imp_CreateThreadpoolTimer
0x1800242d1  mov     rsi, [rdi+30h]
0x1800242d5  mov     r14, rax
0x1800242d8  test    rsi, rsi
0x1800242db  jz      short loc_180024315
0x1800242dd  call    cs:__imp_GetLastError
0x1800242e3  xor     r9d, r9d; msWindowLength
0x1800242e6  xor     r8d, r8d; msPeriod
0x1800242e9  xor     edx, edx; pftDueTime
0x1800242eb  mov     rcx, rsi; pti
0x1800242ee  mov     ebx, eax
0x1800242f0  call    cs:__imp_SetThreadpoolTimer
0x1800242f6  mov     edx, 1; fCancelPendingCallbacks
0x1800242fb  mov     rcx, rsi; pti
0x1800242fe  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180024304  mov     rcx, rsi; pti
0x180024307  call    cs:__imp_CloseThreadpoolTimer
0x18002430d  mov     ecx, ebx; dwErrCode
0x18002430f  call    cs:__imp_SetLastError
0x180024315  mov     ecx, ebp; dwErrCode
0x180024317  mov     [rdi+30h], r14
0x18002431b  call    cs:__imp_SetLastError
0x180024321  mov     rcx, [rdi+30h]; pti
0x180024325  test    rcx, rcx
0x180024328  jz      short loc_180024351
0x18002432a  mov     rax, 0FFFFFFFF4D2FA200h
0x180024334  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180024339  mov     r9d, 124F8h; msWindowLength
0x18002433f  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180024344  xor     r8d, r8d; msPeriod
0x180024347  call    cs:__imp_SetThreadpoolTimer
0x18002434d  mov     byte ptr [rdi+41h], 1
0x180024351  mov     rbx, [rsp+38h+arg_8]
0x180024356  mov     rbp, [rsp+38h+arg_10]
0x18002435b  add     rsp, 20h
0x18002435f  pop     r14
0x180024361  pop     rdi
0x180024362  pop     rsi
0x180024363  retn
```
