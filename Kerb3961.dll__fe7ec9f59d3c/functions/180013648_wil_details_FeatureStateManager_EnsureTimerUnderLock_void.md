# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180013648`
- end: `0x18001371c`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180015598`

## callees

- `0x180013648`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800136c7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800136d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800136c7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800136d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001366e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013695`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001366e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180013695`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800136bf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800136bf`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800136b6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800136b6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800136a8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800136ff`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800136a8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800136ff`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180013683`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180013683`

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
0x180013648  mov     [rsp+arg_8], rbx
0x18001364d  mov     [rsp+arg_10], rbp
0x180013652  push    rsi
0x180013653  push    rdi
0x180013654  push    r14
0x180013656  sub     rsp, 20h
0x18001365a  cmp     byte ptr [rcx+41h], 0
0x18001365e  mov     rdi, rcx
0x180013661  jnz     loc_180013709
0x180013667  cmp     qword ptr [rcx+30h], 0
0x18001366c  jnz     short loc_1800136D9
0x18001366e  call    cs:__imp_GetLastError
0x180013674  xor     r8d, r8d; pcbe
0x180013677  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimer@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001367e  mov     rdx, rdi; pv
0x180013681  mov     ebp, eax
0x180013683  call    cs:__imp_CreateThreadpoolTimer
0x180013689  mov     rsi, [rdi+30h]
0x18001368d  mov     r14, rax
0x180013690  test    rsi, rsi
0x180013693  jz      short loc_1800136CD
0x180013695  call    cs:__imp_GetLastError
0x18001369b  xor     r9d, r9d; msWindowLength
0x18001369e  xor     r8d, r8d; msPeriod
0x1800136a1  xor     edx, edx; pftDueTime
0x1800136a3  mov     rcx, rsi; pti
0x1800136a6  mov     ebx, eax
0x1800136a8  call    cs:__imp_SetThreadpoolTimer
0x1800136ae  mov     edx, 1; fCancelPendingCallbacks
0x1800136b3  mov     rcx, rsi; pti
0x1800136b6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800136bc  mov     rcx, rsi; pti
0x1800136bf  call    cs:__imp_CloseThreadpoolTimer
0x1800136c5  mov     ecx, ebx; dwErrCode
0x1800136c7  call    cs:__imp_SetLastError
0x1800136cd  mov     ecx, ebp; dwErrCode
0x1800136cf  mov     [rdi+30h], r14
0x1800136d3  call    cs:__imp_SetLastError
0x1800136d9  mov     rcx, [rdi+30h]; pti
0x1800136dd  test    rcx, rcx
0x1800136e0  jz      short loc_180013709
0x1800136e2  mov     rax, 0FFFFFFFF4D2FA200h
0x1800136ec  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x1800136f1  mov     r9d, 124F8h; msWindowLength
0x1800136f7  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x1800136fc  xor     r8d, r8d; msPeriod
0x1800136ff  call    cs:__imp_SetThreadpoolTimer
0x180013705  mov     byte ptr [rdi+41h], 1
0x180013709  mov     rbx, [rsp+38h+arg_8]
0x18001370e  mov     rbp, [rsp+38h+arg_10]
0x180013713  add     rsp, 20h
0x180013717  pop     r14
0x180013719  pop     rdi
0x18001371a  pop     rsi
0x18001371b  retn
```
