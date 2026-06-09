# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x1800097b4`
- end: `0x180009888`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000ab7c`

## callees

- `0x1800097b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800097da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009801`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800097da`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009801`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009833`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000983f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180009833`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000983f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009822`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180009822`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800097ef`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1800097ef`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009814`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000986b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180009814`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000986b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000982b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000982b`

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
0x1800097b4  mov     [rsp+arg_8], rbx
0x1800097b9  mov     [rsp+arg_10], rbp
0x1800097be  push    rsi
0x1800097bf  push    rdi
0x1800097c0  push    r14
0x1800097c2  sub     rsp, 20h
0x1800097c6  cmp     byte ptr [rcx+41h], 0
0x1800097ca  mov     rdi, rcx
0x1800097cd  jnz     loc_180009875
0x1800097d3  cmp     qword ptr [rcx+30h], 0
0x1800097d8  jnz     short loc_180009845
0x1800097da  call    cs:__imp_GetLastError
0x1800097e0  xor     r8d, r8d; pcbe
0x1800097e3  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1800097ea  mov     rdx, rdi; pv
0x1800097ed  mov     ebp, eax
0x1800097ef  call    cs:__imp_CreateThreadpoolTimer
0x1800097f5  mov     rsi, [rdi+30h]
0x1800097f9  mov     r14, rax
0x1800097fc  test    rsi, rsi
0x1800097ff  jz      short loc_180009839
0x180009801  call    cs:__imp_GetLastError
0x180009807  xor     r9d, r9d; msWindowLength
0x18000980a  xor     r8d, r8d; msPeriod
0x18000980d  xor     edx, edx; pftDueTime
0x18000980f  mov     rcx, rsi; pti
0x180009812  mov     ebx, eax
0x180009814  call    cs:__imp_SetThreadpoolTimer
0x18000981a  mov     edx, 1; fCancelPendingCallbacks
0x18000981f  mov     rcx, rsi; pti
0x180009822  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180009828  mov     rcx, rsi; pti
0x18000982b  call    cs:__imp_CloseThreadpoolTimer
0x180009831  mov     ecx, ebx; dwErrCode
0x180009833  call    cs:__imp_SetLastError
0x180009839  mov     ecx, ebp; dwErrCode
0x18000983b  mov     [rdi+30h], r14
0x18000983f  call    cs:__imp_SetLastError
0x180009845  mov     rcx, [rdi+30h]; pti
0x180009849  test    rcx, rcx
0x18000984c  jz      short loc_180009875
0x18000984e  mov     rax, 0FFFFFFFF4D2FA200h
0x180009858  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x18000985d  mov     r9d, 124F8h; msWindowLength
0x180009863  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180009868  xor     r8d, r8d; msPeriod
0x18000986b  call    cs:__imp_SetThreadpoolTimer
0x180009871  mov     byte ptr [rdi+41h], 1
0x180009875  mov     rbx, [rsp+38h+arg_8]
0x18000987a  mov     rbp, [rsp+38h+arg_10]
0x18000987f  add     rsp, 20h
0x180009883  pop     r14
0x180009885  pop     rdi
0x180009886  pop     rsi
0x180009887  retn
```
