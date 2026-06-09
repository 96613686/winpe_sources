# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180004b0c`
- end: `0x180004be0`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800068e4`

## callees

- `0x180004b0c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004b8b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004b97`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004b8b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180004b97`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b32`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180004b59`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004b6c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004bc3`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004b6c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180004bc3`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004b83`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180004b83`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004b7a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180004b7a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180004b47`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180004b47`

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
0x180004b0c  mov     [rsp+arg_8], rbx
0x180004b11  mov     [rsp+arg_10], rbp
0x180004b16  push    rsi
0x180004b17  push    rdi
0x180004b18  push    r14
0x180004b1a  sub     rsp, 20h
0x180004b1e  cmp     byte ptr [rcx+41h], 0
0x180004b22  mov     rdi, rcx
0x180004b25  jnz     loc_180004BCD
0x180004b2b  cmp     qword ptr [rcx+30h], 0
0x180004b30  jnz     short loc_180004B9D
0x180004b32  call    cs:__imp_GetLastError
0x180004b38  xor     r8d, r8d; pcbe
0x180004b3b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180004b42  mov     rdx, rdi; pv
0x180004b45  mov     ebp, eax
0x180004b47  call    cs:__imp_CreateThreadpoolTimer
0x180004b4d  mov     rsi, [rdi+30h]
0x180004b51  mov     r14, rax
0x180004b54  test    rsi, rsi
0x180004b57  jz      short loc_180004B91
0x180004b59  call    cs:__imp_GetLastError
0x180004b5f  xor     r9d, r9d; msWindowLength
0x180004b62  xor     r8d, r8d; msPeriod
0x180004b65  xor     edx, edx; pftDueTime
0x180004b67  mov     rcx, rsi; pti
0x180004b6a  mov     ebx, eax
0x180004b6c  call    cs:__imp_SetThreadpoolTimer
0x180004b72  mov     edx, 1; fCancelPendingCallbacks
0x180004b77  mov     rcx, rsi; pti
0x180004b7a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180004b80  mov     rcx, rsi; pti
0x180004b83  call    cs:__imp_CloseThreadpoolTimer
0x180004b89  mov     ecx, ebx; dwErrCode
0x180004b8b  call    cs:__imp_SetLastError
0x180004b91  mov     ecx, ebp; dwErrCode
0x180004b93  mov     [rdi+30h], r14
0x180004b97  call    cs:__imp_SetLastError
0x180004b9d  mov     rcx, [rdi+30h]; pti
0x180004ba1  test    rcx, rcx
0x180004ba4  jz      short loc_180004BCD
0x180004ba6  mov     rax, 0FFFFFFFF4D2FA200h
0x180004bb0  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180004bb5  mov     r9d, 124F8h; msWindowLength
0x180004bbb  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180004bc0  xor     r8d, r8d; msPeriod
0x180004bc3  call    cs:__imp_SetThreadpoolTimer
0x180004bc9  mov     byte ptr [rdi+41h], 1
0x180004bcd  mov     rbx, [rsp+38h+arg_8]
0x180004bd2  mov     rbp, [rsp+38h+arg_10]
0x180004bd7  add     rsp, 20h
0x180004bdb  pop     r14
0x180004bdd  pop     rdi
0x180004bde  pop     rsi
0x180004bdf  retn
```
