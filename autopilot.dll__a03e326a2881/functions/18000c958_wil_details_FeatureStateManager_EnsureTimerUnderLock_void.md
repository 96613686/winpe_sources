# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x18000c958`
- end: `0x18000ca2c`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000f0a4`

## callees

- `0x18000c958`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c97e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c9a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c97e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c9a5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c9d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c9e3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c9d7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000c9e3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000c993`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000c993`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000c9c6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000c9c6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000c9cf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000c9cf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c9b8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ca0f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000c9b8`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ca0f`

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
0x18000c958  mov     [rsp+arg_8], rbx
0x18000c95d  mov     [rsp+arg_10], rbp
0x18000c962  push    rsi
0x18000c963  push    rdi
0x18000c964  push    r14
0x18000c966  sub     rsp, 20h
0x18000c96a  cmp     byte ptr [rcx+41h], 0
0x18000c96e  mov     rdi, rcx
0x18000c971  jnz     loc_18000CA19
0x18000c977  cmp     qword ptr [rcx+30h], 0
0x18000c97c  jnz     short loc_18000C9E9
0x18000c97e  call    cs:__imp_GetLastError
0x18000c984  xor     r8d, r8d; pcbe
0x18000c987  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000c98e  mov     rdx, rdi; pv
0x18000c991  mov     ebp, eax
0x18000c993  call    cs:__imp_CreateThreadpoolTimer
0x18000c999  mov     rsi, [rdi+30h]
0x18000c99d  mov     r14, rax
0x18000c9a0  test    rsi, rsi
0x18000c9a3  jz      short loc_18000C9DD
0x18000c9a5  call    cs:__imp_GetLastError
0x18000c9ab  xor     r9d, r9d; msWindowLength
0x18000c9ae  xor     r8d, r8d; msPeriod
0x18000c9b1  xor     edx, edx; pftDueTime
0x18000c9b3  mov     rcx, rsi; pti
0x18000c9b6  mov     ebx, eax
0x18000c9b8  call    cs:__imp_SetThreadpoolTimer
0x18000c9be  mov     edx, 1; fCancelPendingCallbacks
0x18000c9c3  mov     rcx, rsi; pti
0x18000c9c6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000c9cc  mov     rcx, rsi; pti
0x18000c9cf  call    cs:__imp_CloseThreadpoolTimer
0x18000c9d5  mov     ecx, ebx; dwErrCode
0x18000c9d7  call    cs:__imp_SetLastError
0x18000c9dd  mov     ecx, ebp; dwErrCode
0x18000c9df  mov     [rdi+30h], r14
0x18000c9e3  call    cs:__imp_SetLastError
0x18000c9e9  mov     rcx, [rdi+30h]; pti
0x18000c9ed  test    rcx, rcx
0x18000c9f0  jz      short loc_18000CA19
0x18000c9f2  mov     rax, 0FFFFFFFF4D2FA200h
0x18000c9fc  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x18000ca01  mov     r9d, 124F8h; msWindowLength
0x18000ca07  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x18000ca0c  xor     r8d, r8d; msPeriod
0x18000ca0f  call    cs:__imp_SetThreadpoolTimer
0x18000ca15  mov     byte ptr [rdi+41h], 1
0x18000ca19  mov     rbx, [rsp+38h+arg_8]
0x18000ca1e  mov     rbp, [rsp+38h+arg_10]
0x18000ca23  add     rsp, 20h
0x18000ca27  pop     r14
0x18000ca29  pop     rdi
0x18000ca2a  pop     rsi
0x18000ca2b  retn
```
