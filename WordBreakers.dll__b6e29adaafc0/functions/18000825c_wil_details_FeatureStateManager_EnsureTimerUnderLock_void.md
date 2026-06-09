# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x18000825c`
- end: `0x180008330`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000983c`

## callees

- `0x18000825c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008282`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800082a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180008282`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800082a9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800082db`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800082e7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800082db`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800082e7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180008297`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180008297`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800082ca`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800082ca`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800082d3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800082d3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800082bc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008313`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800082bc`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180008313`

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
0x18000825c  mov     [rsp+arg_8], rbx
0x180008261  mov     [rsp+arg_10], rbp
0x180008266  push    rsi
0x180008267  push    rdi
0x180008268  push    r14
0x18000826a  sub     rsp, 20h
0x18000826e  cmp     byte ptr [rcx+41h], 0
0x180008272  mov     rdi, rcx
0x180008275  jnz     loc_18000831D
0x18000827b  cmp     qword ptr [rcx+30h], 0
0x180008280  jnz     short loc_1800082ED
0x180008282  call    cs:__imp_GetLastError
0x180008288  xor     r8d, r8d; pcbe
0x18000828b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180008292  mov     rdx, rdi; pv
0x180008295  mov     ebp, eax
0x180008297  call    cs:__imp_CreateThreadpoolTimer
0x18000829d  mov     rsi, [rdi+30h]
0x1800082a1  mov     r14, rax
0x1800082a4  test    rsi, rsi
0x1800082a7  jz      short loc_1800082E1
0x1800082a9  call    cs:__imp_GetLastError
0x1800082af  xor     r9d, r9d; msWindowLength
0x1800082b2  xor     r8d, r8d; msPeriod
0x1800082b5  xor     edx, edx; pftDueTime
0x1800082b7  mov     rcx, rsi; pti
0x1800082ba  mov     ebx, eax
0x1800082bc  call    cs:__imp_SetThreadpoolTimer
0x1800082c2  mov     edx, 1; fCancelPendingCallbacks
0x1800082c7  mov     rcx, rsi; pti
0x1800082ca  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800082d0  mov     rcx, rsi; pti
0x1800082d3  call    cs:__imp_CloseThreadpoolTimer
0x1800082d9  mov     ecx, ebx; dwErrCode
0x1800082db  call    cs:__imp_SetLastError
0x1800082e1  mov     ecx, ebp; dwErrCode
0x1800082e3  mov     [rdi+30h], r14
0x1800082e7  call    cs:__imp_SetLastError
0x1800082ed  mov     rcx, [rdi+30h]; pti
0x1800082f1  test    rcx, rcx
0x1800082f4  jz      short loc_18000831D
0x1800082f6  mov     rax, 0FFFFFFFF4D2FA200h
0x180008300  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180008305  mov     r9d, 124F8h; msWindowLength
0x18000830b  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180008310  xor     r8d, r8d; msPeriod
0x180008313  call    cs:__imp_SetThreadpoolTimer
0x180008319  mov     byte ptr [rdi+41h], 1
0x18000831d  mov     rbx, [rsp+38h+arg_8]
0x180008322  mov     rbp, [rsp+38h+arg_10]
0x180008327  add     rsp, 20h
0x18000832b  pop     r14
0x18000832d  pop     rdi
0x18000832e  pop     rsi
0x18000832f  retn
```
