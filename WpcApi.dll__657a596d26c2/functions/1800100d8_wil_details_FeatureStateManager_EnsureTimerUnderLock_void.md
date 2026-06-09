# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x1800100d8`
- end: `0x1800101ac`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180011398`

## callees

- `0x1800100d8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010157`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010163`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010157`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180010163`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800100fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010125`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800100fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010125`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180010113`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180010113`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180010146`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180010146`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010138`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001018f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180010138`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001018f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001014f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18001014f`

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
0x1800100d8  mov     [rsp+arg_8], rbx
0x1800100dd  mov     [rsp+arg_10], rbp
0x1800100e2  push    rsi
0x1800100e3  push    rdi
0x1800100e4  push    r14
0x1800100e6  sub     rsp, 20h
0x1800100ea  cmp     byte ptr [rcx+41h], 0
0x1800100ee  mov     rdi, rcx
0x1800100f1  jnz     loc_180010199
0x1800100f7  cmp     qword ptr [rcx+30h], 0
0x1800100fc  jnz     short loc_180010169
0x1800100fe  call    cs:__imp_GetLastError
0x180010104  xor     r8d, r8d; pcbe
0x180010107  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001010e  mov     rdx, rdi; pv
0x180010111  mov     ebp, eax
0x180010113  call    cs:__imp_CreateThreadpoolTimer
0x180010119  mov     rsi, [rdi+30h]
0x18001011d  mov     r14, rax
0x180010120  test    rsi, rsi
0x180010123  jz      short loc_18001015D
0x180010125  call    cs:__imp_GetLastError
0x18001012b  xor     r9d, r9d; msWindowLength
0x18001012e  xor     r8d, r8d; msPeriod
0x180010131  xor     edx, edx; pftDueTime
0x180010133  mov     rcx, rsi; pti
0x180010136  mov     ebx, eax
0x180010138  call    cs:__imp_SetThreadpoolTimer
0x18001013e  mov     edx, 1; fCancelPendingCallbacks
0x180010143  mov     rcx, rsi; pti
0x180010146  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18001014c  mov     rcx, rsi; pti
0x18001014f  call    cs:__imp_CloseThreadpoolTimer
0x180010155  mov     ecx, ebx; dwErrCode
0x180010157  call    cs:__imp_SetLastError
0x18001015d  mov     ecx, ebp; dwErrCode
0x18001015f  mov     [rdi+30h], r14
0x180010163  call    cs:__imp_SetLastError
0x180010169  mov     rcx, [rdi+30h]; pti
0x18001016d  test    rcx, rcx
0x180010170  jz      short loc_180010199
0x180010172  mov     rax, 0FFFFFFFF4D2FA200h
0x18001017c  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180010181  mov     r9d, 124F8h; msWindowLength
0x180010187  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x18001018c  xor     r8d, r8d; msPeriod
0x18001018f  call    cs:__imp_SetThreadpoolTimer
0x180010195  mov     byte ptr [rdi+41h], 1
0x180010199  mov     rbx, [rsp+38h+arg_8]
0x18001019e  mov     rbp, [rsp+38h+arg_10]
0x1800101a3  add     rsp, 20h
0x1800101a7  pop     r14
0x1800101a9  pop     rdi
0x1800101aa  pop     rsi
0x1800101ab  retn
```
