# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180007918`
- end: `0x1800079ec`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000a7c4`

## callees

- `0x180007918`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007997`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800079a3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180007997`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800079a3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000793e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007965`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000793e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007965`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000798f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000798f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007978`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800079cf`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180007978`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800079cf`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180007953`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180007953`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007986`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180007986`

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
0x180007918  mov     [rsp+arg_8], rbx
0x18000791d  mov     [rsp+arg_10], rbp
0x180007922  push    rsi
0x180007923  push    rdi
0x180007924  push    r14
0x180007926  sub     rsp, 20h
0x18000792a  cmp     byte ptr [rcx+41h], 0
0x18000792e  mov     rdi, rcx
0x180007931  jnz     loc_1800079D9
0x180007937  cmp     qword ptr [rcx+30h], 0
0x18000793c  jnz     short loc_1800079A9
0x18000793e  call    cs:__imp_GetLastError
0x180007944  xor     r8d, r8d; pcbe
0x180007947  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000794e  mov     rdx, rdi; pv
0x180007951  mov     ebp, eax
0x180007953  call    cs:__imp_CreateThreadpoolTimer
0x180007959  mov     rsi, [rdi+30h]
0x18000795d  mov     r14, rax
0x180007960  test    rsi, rsi
0x180007963  jz      short loc_18000799D
0x180007965  call    cs:__imp_GetLastError
0x18000796b  xor     r9d, r9d; msWindowLength
0x18000796e  xor     r8d, r8d; msPeriod
0x180007971  xor     edx, edx; pftDueTime
0x180007973  mov     rcx, rsi; pti
0x180007976  mov     ebx, eax
0x180007978  call    cs:__imp_SetThreadpoolTimer
0x18000797e  mov     edx, 1; fCancelPendingCallbacks
0x180007983  mov     rcx, rsi; pti
0x180007986  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000798c  mov     rcx, rsi; pti
0x18000798f  call    cs:__imp_CloseThreadpoolTimer
0x180007995  mov     ecx, ebx; dwErrCode
0x180007997  call    cs:__imp_SetLastError
0x18000799d  mov     ecx, ebp; dwErrCode
0x18000799f  mov     [rdi+30h], r14
0x1800079a3  call    cs:__imp_SetLastError
0x1800079a9  mov     rcx, [rdi+30h]; pti
0x1800079ad  test    rcx, rcx
0x1800079b0  jz      short loc_1800079D9
0x1800079b2  mov     rax, 0FFFFFFFF4D2FA200h
0x1800079bc  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x1800079c1  mov     r9d, 124F8h; msWindowLength
0x1800079c7  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x1800079cc  xor     r8d, r8d; msPeriod
0x1800079cf  call    cs:__imp_SetThreadpoolTimer
0x1800079d5  mov     byte ptr [rdi+41h], 1
0x1800079d9  mov     rbx, [rsp+38h+arg_8]
0x1800079de  mov     rbp, [rsp+38h+arg_10]
0x1800079e3  add     rsp, 20h
0x1800079e7  pop     r14
0x1800079e9  pop     rdi
0x1800079ea  pop     rsi
0x1800079eb  retn
```
