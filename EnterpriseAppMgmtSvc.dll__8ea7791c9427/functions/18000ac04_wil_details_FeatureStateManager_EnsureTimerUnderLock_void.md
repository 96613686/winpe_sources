# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x18000ac04`
- end: `0x18000acd8`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000c0e0`

## callees

- `0x18000ac04`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac51`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac2a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ac51`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ac83`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ac8f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ac83`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ac8f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000ac7b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000ac7b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000ac3f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000ac3f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ac64`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000acbb`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000ac64`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000acbb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ac72`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000ac72`

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
0x18000ac04  mov     [rsp+arg_8], rbx
0x18000ac09  mov     [rsp+arg_10], rbp
0x18000ac0e  push    rsi
0x18000ac0f  push    rdi
0x18000ac10  push    r14
0x18000ac12  sub     rsp, 20h
0x18000ac16  cmp     byte ptr [rcx+41h], 0
0x18000ac1a  mov     rdi, rcx
0x18000ac1d  jnz     loc_18000ACC5
0x18000ac23  cmp     qword ptr [rcx+30h], 0
0x18000ac28  jnz     short loc_18000AC95
0x18000ac2a  call    cs:__imp_GetLastError
0x18000ac30  xor     r8d, r8d; pcbe
0x18000ac33  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000ac3a  mov     rdx, rdi; pv
0x18000ac3d  mov     ebp, eax
0x18000ac3f  call    cs:__imp_CreateThreadpoolTimer
0x18000ac45  mov     rsi, [rdi+30h]
0x18000ac49  mov     r14, rax
0x18000ac4c  test    rsi, rsi
0x18000ac4f  jz      short loc_18000AC89
0x18000ac51  call    cs:__imp_GetLastError
0x18000ac57  xor     r9d, r9d; msWindowLength
0x18000ac5a  xor     r8d, r8d; msPeriod
0x18000ac5d  xor     edx, edx; pftDueTime
0x18000ac5f  mov     rcx, rsi; pti
0x18000ac62  mov     ebx, eax
0x18000ac64  call    cs:__imp_SetThreadpoolTimer
0x18000ac6a  mov     edx, 1; fCancelPendingCallbacks
0x18000ac6f  mov     rcx, rsi; pti
0x18000ac72  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000ac78  mov     rcx, rsi; pti
0x18000ac7b  call    cs:__imp_CloseThreadpoolTimer
0x18000ac81  mov     ecx, ebx; dwErrCode
0x18000ac83  call    cs:__imp_SetLastError
0x18000ac89  mov     ecx, ebp; dwErrCode
0x18000ac8b  mov     [rdi+30h], r14
0x18000ac8f  call    cs:__imp_SetLastError
0x18000ac95  mov     rcx, [rdi+30h]; pti
0x18000ac99  test    rcx, rcx
0x18000ac9c  jz      short loc_18000ACC5
0x18000ac9e  mov     rax, 0FFFFFFFF4D2FA200h
0x18000aca8  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x18000acad  mov     r9d, 124F8h; msWindowLength
0x18000acb3  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x18000acb8  xor     r8d, r8d; msPeriod
0x18000acbb  call    cs:__imp_SetThreadpoolTimer
0x18000acc1  mov     byte ptr [rdi+41h], 1
0x18000acc5  mov     rbx, [rsp+38h+arg_8]
0x18000acca  mov     rbp, [rsp+38h+arg_10]
0x18000accf  add     rsp, 20h
0x18000acd3  pop     r14
0x18000acd5  pop     rdi
0x18000acd6  pop     rsi
0x18000acd7  retn
```
