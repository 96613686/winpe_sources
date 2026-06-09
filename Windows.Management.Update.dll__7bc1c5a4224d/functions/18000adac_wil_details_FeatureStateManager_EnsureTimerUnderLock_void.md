# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x18000adac`
- end: `0x18000ae80`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d1a4`

## callees

- `0x18000adac`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ae2b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ae37`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ae2b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ae37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000add2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000adf9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000add2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000adf9`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ae0c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ae63`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ae0c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ae63`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000ae23`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000ae23`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000ade7`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000ade7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ae1a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ae1a`

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
0x18000adac  mov     [rsp+arg_8], rbx
0x18000adb1  mov     [rsp+arg_10], rbp
0x18000adb6  push    rsi
0x18000adb7  push    rdi
0x18000adb8  push    r14
0x18000adba  sub     rsp, 20h
0x18000adbe  cmp     byte ptr [rcx+41h], 0
0x18000adc2  mov     rdi, rcx
0x18000adc5  jnz     loc_18000AE6D
0x18000adcb  cmp     qword ptr [rcx+30h], 0
0x18000add0  jnz     short loc_18000AE3D
0x18000add2  call    cs:__imp_GetLastError
0x18000add8  xor     r8d, r8d; pcbe
0x18000addb  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000ade2  mov     rdx, rdi; pv
0x18000ade5  mov     ebp, eax
0x18000ade7  call    cs:__imp_CreateThreadpoolTimer
0x18000aded  mov     rsi, [rdi+30h]
0x18000adf1  mov     r14, rax
0x18000adf4  test    rsi, rsi
0x18000adf7  jz      short loc_18000AE31
0x18000adf9  call    cs:__imp_GetLastError
0x18000adff  xor     r9d, r9d; msWindowLength
0x18000ae02  xor     r8d, r8d; msPeriod
0x18000ae05  xor     edx, edx; pftDueTime
0x18000ae07  mov     rcx, rsi; pti
0x18000ae0a  mov     ebx, eax
0x18000ae0c  call    cs:__imp_SetThreadpoolTimer
0x18000ae12  mov     edx, 1; fCancelPendingCallbacks
0x18000ae17  mov     rcx, rsi; pti
0x18000ae1a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000ae20  mov     rcx, rsi; pti
0x18000ae23  call    cs:__imp_CloseThreadpoolTimer
0x18000ae29  mov     ecx, ebx; dwErrCode
0x18000ae2b  call    cs:__imp_SetLastError
0x18000ae31  mov     ecx, ebp; dwErrCode
0x18000ae33  mov     [rdi+30h], r14
0x18000ae37  call    cs:__imp_SetLastError
0x18000ae3d  mov     rcx, [rdi+30h]; pti
0x18000ae41  test    rcx, rcx
0x18000ae44  jz      short loc_18000AE6D
0x18000ae46  mov     rax, 0FFFFFFFF4D2FA200h
0x18000ae50  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x18000ae55  mov     r9d, 124F8h; msWindowLength
0x18000ae5b  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x18000ae60  xor     r8d, r8d; msPeriod
0x18000ae63  call    cs:__imp_SetThreadpoolTimer
0x18000ae69  mov     byte ptr [rdi+41h], 1
0x18000ae6d  mov     rbx, [rsp+38h+arg_8]
0x18000ae72  mov     rbp, [rsp+38h+arg_10]
0x18000ae77  add     rsp, 20h
0x18000ae7b  pop     r14
0x18000ae7d  pop     rdi
0x18000ae7e  pop     rsi
0x18000ae7f  retn
```
