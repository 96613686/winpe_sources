# wil::details::FeatureStateManager::EnsureSRUMTimerUnderLock(void)

- ea: `0x180006c74`
- end: `0x180006d5e`
- name: `?EnsureSRUMTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `234`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180008adc`

## callees

- `0x180003870`
- `0x180006c74`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ca9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006cd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006ca9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180006cd0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006d02`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006d0e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006d02`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180006d0e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180006cbe`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180006cbe`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006ce3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006d34`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006ce3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180006d34`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006cfa`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180006cfa`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006cf1`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180006cf1`

## pseudocode

```c
void __fastcall wil::details::FeatureStateManager::EnsureSRUMTimerUnderLock(struct _TP_TIMER **pv)
{
  DWORD LastError; // ebp
  PTP_TIMER ThreadpoolTimer; // rax
  struct _TP_TIMER *v4; // rsi
  PTP_TIMER v5; // r14
  DWORD v6; // ebx
  struct _TP_TIMER *v7; // rcx
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-28h] BYREF

  if ( !*((_BYTE *)pv + 64) )
  {
    if ( !pv[7] )
    {
      LastError = GetLastError();
      ThreadpoolTimer = CreateThreadpoolTimer(
                          (PTP_TIMER_CALLBACK)`wil::details::EnsureCoalescedTimerSRUM<wil::details::FeatureStateManager>'::`8'::_lambda_1_::_lambda_invoker_cdecl_,
                          pv,
                          0);
      v4 = pv[7];
      v5 = ThreadpoolTimer;
      if ( v4 )
      {
        v6 = GetLastError();
        SetThreadpoolTimer(v4, 0, 0, 0);
        WaitForThreadpoolTimerCallbacks(v4, 1);
        CloseThreadpoolTimer(v4);
        SetLastError(v6);
      }
      pv[7] = v5;
      SetLastError(LastError);
    }
    v7 = pv[7];
    if ( v7 )
    {
      pftDueTime = (struct _FILETIME)-50000000LL;
      SetThreadpoolTimer(v7, &pftDueTime, 0, 0x4E2u);
      *((_BYTE *)pv + 64) = 1;
    }
  }
}

```

## disassembly

```asm
0x180006c74  mov     [rsp+arg_8], rbx
0x180006c79  mov     [rsp+arg_10], rbp
0x180006c7e  push    rsi
0x180006c7f  push    rdi
0x180006c80  push    r14
0x180006c82  sub     rsp, 30h
0x180006c86  mov     rax, cs:__security_cookie
0x180006c8d  xor     rax, rsp
0x180006c90  mov     [rsp+48h+var_20], rax
0x180006c95  cmp     byte ptr [rcx+40h], 0
0x180006c99  mov     rdi, rcx
0x180006c9c  jnz     loc_180006D3E
0x180006ca2  cmp     qword ptr [rcx+38h], 0
0x180006ca7  jnz     short loc_180006D14
0x180006ca9  call    cs:__imp_GetLastError
0x180006caf  xor     r8d, r8d; pcbe
0x180006cb2  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_1_@?7???$EnsureCoalescedTimerSRUM@VFeatureStateManager@details@wil@@@details@wil@@YAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@3@AEA_NPEAVFeatureStateManager@23@@Z@SA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180006cb9  mov     rdx, rdi; pv
0x180006cbc  mov     ebp, eax
0x180006cbe  call    cs:__imp_CreateThreadpoolTimer
0x180006cc4  mov     rsi, [rdi+38h]
0x180006cc8  mov     r14, rax
0x180006ccb  test    rsi, rsi
0x180006cce  jz      short loc_180006D08
0x180006cd0  call    cs:__imp_GetLastError
0x180006cd6  xor     r9d, r9d; msWindowLength
0x180006cd9  xor     r8d, r8d; msPeriod
0x180006cdc  xor     edx, edx; pftDueTime
0x180006cde  mov     rcx, rsi; pti
0x180006ce1  mov     ebx, eax
0x180006ce3  call    cs:__imp_SetThreadpoolTimer
0x180006ce9  mov     edx, 1; fCancelPendingCallbacks
0x180006cee  mov     rcx, rsi; pti
0x180006cf1  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180006cf7  mov     rcx, rsi; pti
0x180006cfa  call    cs:__imp_CloseThreadpoolTimer
0x180006d00  mov     ecx, ebx; dwErrCode
0x180006d02  call    cs:__imp_SetLastError
0x180006d08  mov     ecx, ebp; dwErrCode
0x180006d0a  mov     [rdi+38h], r14
0x180006d0e  call    cs:__imp_SetLastError
0x180006d14  mov     rcx, [rdi+38h]; pti
0x180006d18  test    rcx, rcx
0x180006d1b  jz      short loc_180006D3E
0x180006d1d  mov     r9d, 4E2h; msWindowLength
0x180006d23  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], 0FFFFFFFFFD050F80h
0x180006d2c  xor     r8d, r8d; msPeriod
0x180006d2f  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x180006d34  call    cs:__imp_SetThreadpoolTimer
0x180006d3a  mov     byte ptr [rdi+40h], 1
0x180006d3e  mov     rcx, [rsp+48h+var_20]
0x180006d43  xor     rcx, rsp; StackCookie
0x180006d46  call    __security_check_cookie
0x180006d4b  mov     rbx, [rsp+48h+arg_8]
0x180006d50  mov     rbp, [rsp+48h+arg_10]
0x180006d55  add     rsp, 30h
0x180006d59  pop     r14
0x180006d5b  pop     rdi
0x180006d5c  pop     rsi
0x180006d5d  retn
```
