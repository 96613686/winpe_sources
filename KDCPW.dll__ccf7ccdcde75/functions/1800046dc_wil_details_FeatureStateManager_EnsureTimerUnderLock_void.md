# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x1800046dc`
- end: `0x1800047b0`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180006a44`

## callees

- `0x1800046dc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004702`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004729`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004702`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004729`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000475b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004767`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000475b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004767`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000473c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004793`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000473c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004793`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004753`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004753`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000474a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000474a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180004717`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180004717`

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
0x1800046dc  mov     [rsp+arg_8], rbx
0x1800046e1  mov     [rsp+arg_10], rbp
0x1800046e6  push    rsi
0x1800046e7  push    rdi
0x1800046e8  push    r14
0x1800046ea  sub     rsp, 20h
0x1800046ee  cmp     byte ptr [rcx+41h], 0
0x1800046f2  mov     rdi, rcx
0x1800046f5  jnz     loc_18000479D
0x1800046fb  cmp     qword ptr [rcx+30h], 0
0x180004700  jnz     short loc_18000476D
0x180004702  call    cs:__imp_GetLastError
0x180004708  xor     r8d, r8d; pcbe
0x18000470b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180004712  mov     rdx, rdi; pv
0x180004715  mov     ebp, eax
0x180004717  call    cs:__imp_CreateThreadpoolTimer
0x18000471d  mov     rsi, [rdi+30h]
0x180004721  mov     r14, rax
0x180004724  test    rsi, rsi
0x180004727  jz      short loc_180004761
0x180004729  call    cs:__imp_GetLastError
0x18000472f  xor     r9d, r9d; msWindowLength
0x180004732  xor     r8d, r8d; msPeriod
0x180004735  xor     edx, edx; pftDueTime
0x180004737  mov     rcx, rsi; pti
0x18000473a  mov     ebx, eax
0x18000473c  call    cs:__imp_SetThreadpoolTimer
0x180004742  mov     edx, 1; fCancelPendingCallbacks
0x180004747  mov     rcx, rsi; pti
0x18000474a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004750  mov     rcx, rsi; pti
0x180004753  call    cs:__imp_CloseThreadpoolTimer
0x180004759  mov     ecx, ebx; dwErrCode
0x18000475b  call    cs:__imp_SetLastError
0x180004761  mov     ecx, ebp; dwErrCode
0x180004763  mov     [rdi+30h], r14
0x180004767  call    cs:__imp_SetLastError
0x18000476d  mov     rcx, [rdi+30h]; pti
0x180004771  test    rcx, rcx
0x180004774  jz      short loc_18000479D
0x180004776  mov     rax, 0FFFFFFFF4D2FA200h
0x180004780  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180004785  mov     r9d, 124F8h; msWindowLength
0x18000478b  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180004790  xor     r8d, r8d; msPeriod
0x180004793  call    cs:__imp_SetThreadpoolTimer
0x180004799  mov     byte ptr [rdi+41h], 1
0x18000479d  mov     rbx, [rsp+38h+arg_8]
0x1800047a2  mov     rbp, [rsp+38h+arg_10]
0x1800047a7  add     rsp, 20h
0x1800047ab  pop     r14
0x1800047ad  pop     rdi
0x1800047ae  pop     rsi
0x1800047af  retn
```
