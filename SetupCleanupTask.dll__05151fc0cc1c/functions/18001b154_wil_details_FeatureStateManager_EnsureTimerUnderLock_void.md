# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x18001b154`
- end: `0x18001b228`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180020e44`

## callees

- `0x18001b154`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b1d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b1df`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b1d3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001b1df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b17a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b1a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b17a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b1a1`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001b1b4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001b20b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001b1b4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001b20b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001b1c2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18001b1c2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001b18f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001b18f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001b1cb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001b1cb`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
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
0x18001b154  mov     [rsp+arg_8], rbx
0x18001b159  mov     [rsp+arg_10], rbp
0x18001b15e  push    rsi
0x18001b15f  push    rdi
0x18001b160  push    r14
0x18001b162  sub     rsp, 20h
0x18001b166  cmp     byte ptr [rcx+41h], 0
0x18001b16a  mov     rdi, rcx
0x18001b16d  jnz     loc_18001B215
0x18001b173  cmp     qword ptr [rcx+30h], 0
0x18001b178  jnz     short loc_18001B1E5
0x18001b17a  call    cs:__imp_GetLastError
0x18001b180  xor     r8d, r8d; pcbe
0x18001b183  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001b18a  mov     rdx, rdi; pv
0x18001b18d  mov     ebp, eax
0x18001b18f  call    cs:__imp_CreateThreadpoolTimer
0x18001b195  mov     rsi, [rdi+30h]
0x18001b199  mov     r14, rax
0x18001b19c  test    rsi, rsi
0x18001b19f  jz      short loc_18001B1D9
0x18001b1a1  call    cs:__imp_GetLastError
0x18001b1a7  xor     r9d, r9d; msWindowLength
0x18001b1aa  xor     r8d, r8d; msPeriod
0x18001b1ad  xor     edx, edx; pftDueTime
0x18001b1af  mov     rcx, rsi; pti
0x18001b1b2  mov     ebx, eax
0x18001b1b4  call    cs:__imp_SetThreadpoolTimer
0x18001b1ba  mov     edx, 1; fCancelPendingCallbacks
0x18001b1bf  mov     rcx, rsi; pti
0x18001b1c2  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001b1c8  mov     rcx, rsi; pti
0x18001b1cb  call    cs:__imp_CloseThreadpoolTimer
0x18001b1d1  mov     ecx, ebx; dwErrCode
0x18001b1d3  call    cs:__imp_SetLastError
0x18001b1d9  mov     ecx, ebp; dwErrCode
0x18001b1db  mov     [rdi+30h], r14
0x18001b1df  call    cs:__imp_SetLastError
0x18001b1e5  mov     rcx, [rdi+30h]; pti
0x18001b1e9  test    rcx, rcx
0x18001b1ec  jz      short loc_18001B215
0x18001b1ee  mov     rax, 0FFFFFFFF4D2FA200h
0x18001b1f8  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x18001b1fd  mov     r9d, 124F8h; msWindowLength
0x18001b203  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x18001b208  xor     r8d, r8d; msPeriod
0x18001b20b  call    cs:__imp_SetThreadpoolTimer
0x18001b211  mov     byte ptr [rdi+41h], 1
0x18001b215  mov     rbx, [rsp+38h+arg_8]
0x18001b21a  mov     rbp, [rsp+38h+arg_10]
0x18001b21f  add     rsp, 20h
0x18001b223  pop     r14
0x18001b225  pop     rdi
0x18001b226  pop     rsi
0x18001b227  retn
```
