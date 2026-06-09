# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x140006510`
- end: `0x1400065e4`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140006d90`

## callees

- `0x140006510`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006536`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000655d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006536`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000655d`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000658f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000659b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000658f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000659b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140006587`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x140006587`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14000654b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14000654b`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140006570`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400065c7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140006570`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1400065c7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000657e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000657e`

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
0x140006510  mov     [rsp+arg_8], rbx
0x140006515  mov     [rsp+arg_10], rbp
0x14000651a  push    rsi
0x14000651b  push    rdi
0x14000651c  push    r14
0x14000651e  sub     rsp, 20h
0x140006522  cmp     byte ptr [rcx+41h], 0
0x140006526  mov     rdi, rcx
0x140006529  jnz     loc_1400065D1
0x14000652f  cmp     qword ptr [rcx+30h], 0
0x140006534  jnz     short loc_1400065A1
0x140006536  call    cs:__imp_GetLastError
0x14000653c  xor     r8d, r8d; pcbe
0x14000653f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x140006546  mov     rdx, rdi; pv
0x140006549  mov     ebp, eax
0x14000654b  call    cs:__imp_CreateThreadpoolTimer
0x140006551  mov     rsi, [rdi+30h]
0x140006555  mov     r14, rax
0x140006558  test    rsi, rsi
0x14000655b  jz      short loc_140006595
0x14000655d  call    cs:__imp_GetLastError
0x140006563  xor     r9d, r9d; msWindowLength
0x140006566  xor     r8d, r8d; msPeriod
0x140006569  xor     edx, edx; pftDueTime
0x14000656b  mov     rcx, rsi; pti
0x14000656e  mov     ebx, eax
0x140006570  call    cs:__imp_SetThreadpoolTimer
0x140006576  mov     edx, 1; fCancelPendingCallbacks
0x14000657b  mov     rcx, rsi; pti
0x14000657e  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x140006584  mov     rcx, rsi; pti
0x140006587  call    cs:__imp_CloseThreadpoolTimer
0x14000658d  mov     ecx, ebx; dwErrCode
0x14000658f  call    cs:__imp_SetLastError
0x140006595  mov     ecx, ebp; dwErrCode
0x140006597  mov     [rdi+30h], r14
0x14000659b  call    cs:__imp_SetLastError
0x1400065a1  mov     rcx, [rdi+30h]; pti
0x1400065a5  test    rcx, rcx
0x1400065a8  jz      short loc_1400065D1
0x1400065aa  mov     rax, 0FFFFFFFF4D2FA200h
0x1400065b4  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x1400065b9  mov     r9d, 124F8h; msWindowLength
0x1400065bf  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x1400065c4  xor     r8d, r8d; msPeriod
0x1400065c7  call    cs:__imp_SetThreadpoolTimer
0x1400065cd  mov     byte ptr [rdi+41h], 1
0x1400065d1  mov     rbx, [rsp+38h+arg_8]
0x1400065d6  mov     rbp, [rsp+38h+arg_10]
0x1400065db  add     rsp, 20h
0x1400065df  pop     r14
0x1400065e1  pop     rdi
0x1400065e2  pop     rsi
0x1400065e3  retn
```
