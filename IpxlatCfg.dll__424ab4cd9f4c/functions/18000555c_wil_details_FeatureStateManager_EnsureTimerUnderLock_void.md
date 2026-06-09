# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x18000555c`
- end: `0x180005630`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007364`

## callees

- `0x18000555c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800055db`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800055e7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800055db`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800055e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005582`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800055a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005582`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800055a9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800055ca`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800055ca`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800055d3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800055d3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800055bc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005613`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800055bc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180005613`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180005597`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180005597`

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
0x18000555c  mov     [rsp+arg_8], rbx
0x180005561  mov     [rsp+arg_10], rbp
0x180005566  push    rsi
0x180005567  push    rdi
0x180005568  push    r14
0x18000556a  sub     rsp, 20h
0x18000556e  cmp     byte ptr [rcx+41h], 0
0x180005572  mov     rdi, rcx
0x180005575  jnz     loc_18000561D
0x18000557b  cmp     qword ptr [rcx+30h], 0
0x180005580  jnz     short loc_1800055ED
0x180005582  call    cs:__imp_GetLastError
0x180005588  xor     r8d, r8d; pcbe
0x18000558b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180005592  mov     rdx, rdi; pv
0x180005595  mov     ebp, eax
0x180005597  call    cs:__imp_CreateThreadpoolTimer
0x18000559d  mov     rsi, [rdi+30h]
0x1800055a1  mov     r14, rax
0x1800055a4  test    rsi, rsi
0x1800055a7  jz      short loc_1800055E1
0x1800055a9  call    cs:__imp_GetLastError
0x1800055af  xor     r9d, r9d; msWindowLength
0x1800055b2  xor     r8d, r8d; msPeriod
0x1800055b5  xor     edx, edx; pftDueTime
0x1800055b7  mov     rcx, rsi; pti
0x1800055ba  mov     ebx, eax
0x1800055bc  call    cs:__imp_SetThreadpoolTimer
0x1800055c2  mov     edx, 1; fCancelPendingCallbacks
0x1800055c7  mov     rcx, rsi; pti
0x1800055ca  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800055d0  mov     rcx, rsi; pti
0x1800055d3  call    cs:__imp_CloseThreadpoolTimer
0x1800055d9  mov     ecx, ebx; dwErrCode
0x1800055db  call    cs:__imp_SetLastError
0x1800055e1  mov     ecx, ebp; dwErrCode
0x1800055e3  mov     [rdi+30h], r14
0x1800055e7  call    cs:__imp_SetLastError
0x1800055ed  mov     rcx, [rdi+30h]; pti
0x1800055f1  test    rcx, rcx
0x1800055f4  jz      short loc_18000561D
0x1800055f6  mov     rax, 0FFFFFFFF4D2FA200h
0x180005600  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180005605  mov     r9d, 124F8h; msWindowLength
0x18000560b  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180005610  xor     r8d, r8d; msPeriod
0x180005613  call    cs:__imp_SetThreadpoolTimer
0x180005619  mov     byte ptr [rdi+41h], 1
0x18000561d  mov     rbx, [rsp+38h+arg_8]
0x180005622  mov     rbp, [rsp+38h+arg_10]
0x180005627  add     rsp, 20h
0x18000562b  pop     r14
0x18000562d  pop     rdi
0x18000562e  pop     rsi
0x18000562f  retn
```
