# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x140011374`
- end: `0x140011448`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140012540`

## callees

- `0x140011374`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001139a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400113c1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14001139a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400113c1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400113f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400113ff`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400113f3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1400113ff`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400113af`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x1400113af`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400113eb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1400113eb`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400113e2`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1400113e2`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400113d4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14001142b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400113d4`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14001142b`

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
0x140011374  mov     [rsp+arg_8], rbx
0x140011379  mov     [rsp+arg_10], rbp
0x14001137e  push    rsi
0x14001137f  push    rdi
0x140011380  push    r14
0x140011382  sub     rsp, 20h
0x140011386  cmp     byte ptr [rcx+41h], 0
0x14001138a  mov     rdi, rcx
0x14001138d  jnz     loc_140011435
0x140011393  cmp     qword ptr [rcx+30h], 0
0x140011398  jnz     short loc_140011405
0x14001139a  call    cs:__imp_GetLastError
0x1400113a0  xor     r8d, r8d; pcbe
0x1400113a3  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x1400113aa  mov     rdx, rdi; pv
0x1400113ad  mov     ebp, eax
0x1400113af  call    cs:__imp_CreateThreadpoolTimer
0x1400113b5  mov     rsi, [rdi+30h]
0x1400113b9  mov     r14, rax
0x1400113bc  test    rsi, rsi
0x1400113bf  jz      short loc_1400113F9
0x1400113c1  call    cs:__imp_GetLastError
0x1400113c7  xor     r9d, r9d; msWindowLength
0x1400113ca  xor     r8d, r8d; msPeriod
0x1400113cd  xor     edx, edx; pftDueTime
0x1400113cf  mov     rcx, rsi; pti
0x1400113d2  mov     ebx, eax
0x1400113d4  call    cs:__imp_SetThreadpoolTimer
0x1400113da  mov     edx, 1; fCancelPendingCallbacks
0x1400113df  mov     rcx, rsi; pti
0x1400113e2  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1400113e8  mov     rcx, rsi; pti
0x1400113eb  call    cs:__imp_CloseThreadpoolTimer
0x1400113f1  mov     ecx, ebx; dwErrCode
0x1400113f3  call    cs:__imp_SetLastError
0x1400113f9  mov     ecx, ebp; dwErrCode
0x1400113fb  mov     [rdi+30h], r14
0x1400113ff  call    cs:__imp_SetLastError
0x140011405  mov     rcx, [rdi+30h]; pti
0x140011409  test    rcx, rcx
0x14001140c  jz      short loc_140011435
0x14001140e  mov     rax, 0FFFFFFFF4D2FA200h
0x140011418  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x14001141d  mov     r9d, 124F8h; msWindowLength
0x140011423  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x140011428  xor     r8d, r8d; msPeriod
0x14001142b  call    cs:__imp_SetThreadpoolTimer
0x140011431  mov     byte ptr [rdi+41h], 1
0x140011435  mov     rbx, [rsp+38h+arg_8]
0x14001143a  mov     rbp, [rsp+38h+arg_10]
0x14001143f  add     rsp, 20h
0x140011443  pop     r14
0x140011445  pop     rdi
0x140011446  pop     rsi
0x140011447  retn
```
