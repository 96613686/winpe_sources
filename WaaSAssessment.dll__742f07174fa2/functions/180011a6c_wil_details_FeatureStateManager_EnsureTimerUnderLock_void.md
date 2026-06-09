# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180011a6c`
- end: `0x180011b40`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180014558`

## callees

- `0x180011a6c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011aeb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011af7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011aeb`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180011af7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011a92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011ab9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011a92`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011ab9`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180011ada`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180011ada`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180011ae3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180011ae3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180011aa7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180011aa7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011acc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011b23`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011acc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011b23`

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
0x180011a6c  mov     [rsp+arg_8], rbx
0x180011a71  mov     [rsp+arg_10], rbp
0x180011a76  push    rsi
0x180011a77  push    rdi
0x180011a78  push    r14
0x180011a7a  sub     rsp, 20h
0x180011a7e  cmp     byte ptr [rcx+41h], 0
0x180011a82  mov     rdi, rcx
0x180011a85  jnz     loc_180011B2D
0x180011a8b  cmp     qword ptr [rcx+30h], 0
0x180011a90  jnz     short loc_180011AFD
0x180011a92  call    cs:__imp_GetLastError
0x180011a98  xor     r8d, r8d; pcbe
0x180011a9b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180011aa2  mov     rdx, rdi; pv
0x180011aa5  mov     ebp, eax
0x180011aa7  call    cs:__imp_CreateThreadpoolTimer
0x180011aad  mov     rsi, [rdi+30h]
0x180011ab1  mov     r14, rax
0x180011ab4  test    rsi, rsi
0x180011ab7  jz      short loc_180011AF1
0x180011ab9  call    cs:__imp_GetLastError
0x180011abf  xor     r9d, r9d; msWindowLength
0x180011ac2  xor     r8d, r8d; msPeriod
0x180011ac5  xor     edx, edx; pftDueTime
0x180011ac7  mov     rcx, rsi; pti
0x180011aca  mov     ebx, eax
0x180011acc  call    cs:__imp_SetThreadpoolTimer
0x180011ad2  mov     edx, 1; fCancelPendingCallbacks
0x180011ad7  mov     rcx, rsi; pti
0x180011ada  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180011ae0  mov     rcx, rsi; pti
0x180011ae3  call    cs:__imp_CloseThreadpoolTimer
0x180011ae9  mov     ecx, ebx; dwErrCode
0x180011aeb  call    cs:__imp_SetLastError
0x180011af1  mov     ecx, ebp; dwErrCode
0x180011af3  mov     [rdi+30h], r14
0x180011af7  call    cs:__imp_SetLastError
0x180011afd  mov     rcx, [rdi+30h]; pti
0x180011b01  test    rcx, rcx
0x180011b04  jz      short loc_180011B2D
0x180011b06  mov     rax, 0FFFFFFFF4D2FA200h
0x180011b10  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180011b15  mov     r9d, 124F8h; msWindowLength
0x180011b1b  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180011b20  xor     r8d, r8d; msPeriod
0x180011b23  call    cs:__imp_SetThreadpoolTimer
0x180011b29  mov     byte ptr [rdi+41h], 1
0x180011b2d  mov     rbx, [rsp+38h+arg_8]
0x180011b32  mov     rbp, [rsp+38h+arg_10]
0x180011b37  add     rsp, 20h
0x180011b3b  pop     r14
0x180011b3d  pop     rdi
0x180011b3e  pop     rsi
0x180011b3f  retn
```
