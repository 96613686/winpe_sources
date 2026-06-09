# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180039704`
- end: `0x1800397d8`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18003a880`

## callees

- `0x180039704`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003972a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039751`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003972a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180039751`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039783`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003978f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180039783`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18003978f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003973f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003973f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180039764`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800397bb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180039764`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800397bb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180039772`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180039772`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003977b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18003977b`

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
0x180039704  mov     [rsp+arg_8], rbx
0x180039709  mov     [rsp+arg_10], rbp
0x18003970e  push    rsi
0x18003970f  push    rdi
0x180039710  push    r14
0x180039712  sub     rsp, 20h
0x180039716  cmp     byte ptr [rcx+41h], 0
0x18003971a  mov     rdi, rcx
0x18003971d  jnz     loc_1800397C5
0x180039723  cmp     qword ptr [rcx+30h], 0
0x180039728  jnz     short loc_180039795
0x18003972a  call    cs:__imp_GetLastError
0x180039730  xor     r8d, r8d; pcbe
0x180039733  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18003973a  mov     rdx, rdi; pv
0x18003973d  mov     ebp, eax
0x18003973f  call    cs:__imp_CreateThreadpoolTimer
0x180039745  mov     rsi, [rdi+30h]
0x180039749  mov     r14, rax
0x18003974c  test    rsi, rsi
0x18003974f  jz      short loc_180039789
0x180039751  call    cs:__imp_GetLastError
0x180039757  xor     r9d, r9d; msWindowLength
0x18003975a  xor     r8d, r8d; msPeriod
0x18003975d  xor     edx, edx; pftDueTime
0x18003975f  mov     rcx, rsi; pti
0x180039762  mov     ebx, eax
0x180039764  call    cs:__imp_SetThreadpoolTimer
0x18003976a  mov     edx, 1; fCancelPendingCallbacks
0x18003976f  mov     rcx, rsi; pti
0x180039772  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180039778  mov     rcx, rsi; pti
0x18003977b  call    cs:__imp_CloseThreadpoolTimer
0x180039781  mov     ecx, ebx; dwErrCode
0x180039783  call    cs:__imp_SetLastError
0x180039789  mov     ecx, ebp; dwErrCode
0x18003978b  mov     [rdi+30h], r14
0x18003978f  call    cs:__imp_SetLastError
0x180039795  mov     rcx, [rdi+30h]; pti
0x180039799  test    rcx, rcx
0x18003979c  jz      short loc_1800397C5
0x18003979e  mov     rax, 0FFFFFFFF4D2FA200h
0x1800397a8  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x1800397ad  mov     r9d, 124F8h; msWindowLength
0x1800397b3  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x1800397b8  xor     r8d, r8d; msPeriod
0x1800397bb  call    cs:__imp_SetThreadpoolTimer
0x1800397c1  mov     byte ptr [rdi+41h], 1
0x1800397c5  mov     rbx, [rsp+38h+arg_8]
0x1800397ca  mov     rbp, [rsp+38h+arg_10]
0x1800397cf  add     rsp, 20h
0x1800397d3  pop     r14
0x1800397d5  pop     rdi
0x1800397d6  pop     rsi
0x1800397d7  retn
```
