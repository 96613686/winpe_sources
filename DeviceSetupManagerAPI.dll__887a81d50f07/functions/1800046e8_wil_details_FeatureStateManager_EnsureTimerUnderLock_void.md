# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x1800046e8`
- end: `0x1800047bc`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180006164`

## callees

- `0x1800046e8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000470e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004735`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000470e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004735`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004767`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004773`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004767`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004773`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000475f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000475f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004756`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004756`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004748`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000479f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004748`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000479f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180004723`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180004723`

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
      ThreadpoolTimer = CreateThreadpoolTimer(_lambda_d51448ba32f8ef42e59400edd4566183_::_lambda_invoker_cdecl_, pv, 0);
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
0x1800046e8  mov     [rsp+arg_8], rbx
0x1800046ed  mov     [rsp+arg_10], rbp
0x1800046f2  push    rsi
0x1800046f3  push    rdi
0x1800046f4  push    r14
0x1800046f6  sub     rsp, 20h
0x1800046fa  cmp     byte ptr [rcx+41h], 0
0x1800046fe  mov     rdi, rcx
0x180004701  jnz     loc_1800047A9
0x180004707  cmp     qword ptr [rcx+30h], 0
0x18000470c  jnz     short loc_180004779
0x18000470e  call    cs:__imp_GetLastError
0x180004714  xor     r8d, r8d; pcbe
0x180004717  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000471e  mov     rdx, rdi; pv
0x180004721  mov     ebp, eax
0x180004723  call    cs:__imp_CreateThreadpoolTimer
0x180004729  mov     rsi, [rdi+30h]
0x18000472d  mov     r14, rax
0x180004730  test    rsi, rsi
0x180004733  jz      short loc_18000476D
0x180004735  call    cs:__imp_GetLastError
0x18000473b  xor     r9d, r9d; msWindowLength
0x18000473e  xor     r8d, r8d; msPeriod
0x180004741  xor     edx, edx; pftDueTime
0x180004743  mov     rcx, rsi; pti
0x180004746  mov     ebx, eax
0x180004748  call    cs:__imp_SetThreadpoolTimer
0x18000474e  mov     edx, 1; fCancelPendingCallbacks
0x180004753  mov     rcx, rsi; pti
0x180004756  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000475c  mov     rcx, rsi; pti
0x18000475f  call    cs:__imp_CloseThreadpoolTimer
0x180004765  mov     ecx, ebx; dwErrCode
0x180004767  call    cs:__imp_SetLastError
0x18000476d  mov     ecx, ebp; dwErrCode
0x18000476f  mov     [rdi+30h], r14
0x180004773  call    cs:__imp_SetLastError
0x180004779  mov     rcx, [rdi+30h]; pti
0x18000477d  test    rcx, rcx
0x180004780  jz      short loc_1800047A9
0x180004782  mov     rax, 0FFFFFFFF4D2FA200h
0x18000478c  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180004791  mov     r9d, 124F8h; msWindowLength
0x180004797  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x18000479c  xor     r8d, r8d; msPeriod
0x18000479f  call    cs:__imp_SetThreadpoolTimer
0x1800047a5  mov     byte ptr [rdi+41h], 1
0x1800047a9  mov     rbx, [rsp+38h+arg_8]
0x1800047ae  mov     rbp, [rsp+38h+arg_10]
0x1800047b3  add     rsp, 20h
0x1800047b7  pop     r14
0x1800047b9  pop     rdi
0x1800047ba  pop     rsi
0x1800047bb  retn
```
