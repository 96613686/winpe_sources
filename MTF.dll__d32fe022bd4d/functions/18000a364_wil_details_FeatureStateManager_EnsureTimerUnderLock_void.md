# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x18000a364`
- end: `0x18000a438`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000b1bc`

## callees

- `0x18000a364`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a38a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a3b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a38a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a3b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a3e3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a3ef`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a3e3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000a3ef`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000a39f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000a39f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a3d2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000a3d2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a3c4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a41b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a3c4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000a41b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a3db`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000a3db`

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
0x18000a364  mov     [rsp+arg_8], rbx
0x18000a369  mov     [rsp+arg_10], rbp
0x18000a36e  push    rsi
0x18000a36f  push    rdi
0x18000a370  push    r14
0x18000a372  sub     rsp, 20h
0x18000a376  cmp     byte ptr [rcx+41h], 0
0x18000a37a  mov     rdi, rcx
0x18000a37d  jnz     loc_18000A425
0x18000a383  cmp     qword ptr [rcx+30h], 0
0x18000a388  jnz     short loc_18000A3F5
0x18000a38a  call    cs:__imp_GetLastError
0x18000a390  xor     r8d, r8d; pcbe
0x18000a393  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000a39a  mov     rdx, rdi; pv
0x18000a39d  mov     ebp, eax
0x18000a39f  call    cs:__imp_CreateThreadpoolTimer
0x18000a3a5  mov     rsi, [rdi+30h]
0x18000a3a9  mov     r14, rax
0x18000a3ac  test    rsi, rsi
0x18000a3af  jz      short loc_18000A3E9
0x18000a3b1  call    cs:__imp_GetLastError
0x18000a3b7  xor     r9d, r9d; msWindowLength
0x18000a3ba  xor     r8d, r8d; msPeriod
0x18000a3bd  xor     edx, edx; pftDueTime
0x18000a3bf  mov     rcx, rsi; pti
0x18000a3c2  mov     ebx, eax
0x18000a3c4  call    cs:__imp_SetThreadpoolTimer
0x18000a3ca  mov     edx, 1; fCancelPendingCallbacks
0x18000a3cf  mov     rcx, rsi; pti
0x18000a3d2  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000a3d8  mov     rcx, rsi; pti
0x18000a3db  call    cs:__imp_CloseThreadpoolTimer
0x18000a3e1  mov     ecx, ebx; dwErrCode
0x18000a3e3  call    cs:__imp_SetLastError
0x18000a3e9  mov     ecx, ebp; dwErrCode
0x18000a3eb  mov     [rdi+30h], r14
0x18000a3ef  call    cs:__imp_SetLastError
0x18000a3f5  mov     rcx, [rdi+30h]; pti
0x18000a3f9  test    rcx, rcx
0x18000a3fc  jz      short loc_18000A425
0x18000a3fe  mov     rax, 0FFFFFFFF4D2FA200h
0x18000a408  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x18000a40d  mov     r9d, 124F8h; msWindowLength
0x18000a413  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x18000a418  xor     r8d, r8d; msPeriod
0x18000a41b  call    cs:__imp_SetThreadpoolTimer
0x18000a421  mov     byte ptr [rdi+41h], 1
0x18000a425  mov     rbx, [rsp+38h+arg_8]
0x18000a42a  mov     rbp, [rsp+38h+arg_10]
0x18000a42f  add     rsp, 20h
0x18000a433  pop     r14
0x18000a435  pop     rdi
0x18000a436  pop     rsi
0x18000a437  retn
```
