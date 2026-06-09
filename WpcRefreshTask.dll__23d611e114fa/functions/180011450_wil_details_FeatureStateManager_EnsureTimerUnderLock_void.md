# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180011450`
- end: `0x180011524`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180012208`

## callees

- `0x180011450`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800114cf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800114db`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800114cf`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800114db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011476`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001149d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180011476`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001149d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800114c7`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800114c7`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800114be`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800114be`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800114b0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011507`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800114b0`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180011507`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001148b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001148b`

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
0x180011450  mov     [rsp+arg_8], rbx
0x180011455  mov     [rsp+arg_10], rbp
0x18001145a  push    rsi
0x18001145b  push    rdi
0x18001145c  push    r14
0x18001145e  sub     rsp, 20h
0x180011462  cmp     byte ptr [rcx+41h], 0
0x180011466  mov     rdi, rcx
0x180011469  jnz     loc_180011511
0x18001146f  cmp     qword ptr [rcx+30h], 0
0x180011474  jnz     short loc_1800114E1
0x180011476  call    cs:__imp_GetLastError
0x18001147c  xor     r8d, r8d; pcbe
0x18001147f  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180011486  mov     rdx, rdi; pv
0x180011489  mov     ebp, eax
0x18001148b  call    cs:__imp_CreateThreadpoolTimer
0x180011491  mov     rsi, [rdi+30h]
0x180011495  mov     r14, rax
0x180011498  test    rsi, rsi
0x18001149b  jz      short loc_1800114D5
0x18001149d  call    cs:__imp_GetLastError
0x1800114a3  xor     r9d, r9d; msWindowLength
0x1800114a6  xor     r8d, r8d; msPeriod
0x1800114a9  xor     edx, edx; pftDueTime
0x1800114ab  mov     rcx, rsi; pti
0x1800114ae  mov     ebx, eax
0x1800114b0  call    cs:__imp_SetThreadpoolTimer
0x1800114b6  mov     edx, 1; fCancelPendingCallbacks
0x1800114bb  mov     rcx, rsi; pti
0x1800114be  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800114c4  mov     rcx, rsi; pti
0x1800114c7  call    cs:__imp_CloseThreadpoolTimer
0x1800114cd  mov     ecx, ebx; dwErrCode
0x1800114cf  call    cs:__imp_SetLastError
0x1800114d5  mov     ecx, ebp; dwErrCode
0x1800114d7  mov     [rdi+30h], r14
0x1800114db  call    cs:__imp_SetLastError
0x1800114e1  mov     rcx, [rdi+30h]; pti
0x1800114e5  test    rcx, rcx
0x1800114e8  jz      short loc_180011511
0x1800114ea  mov     rax, 0FFFFFFFF4D2FA200h
0x1800114f4  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x1800114f9  mov     r9d, 124F8h; msWindowLength
0x1800114ff  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180011504  xor     r8d, r8d; msPeriod
0x180011507  call    cs:__imp_SetThreadpoolTimer
0x18001150d  mov     byte ptr [rdi+41h], 1
0x180011511  mov     rbx, [rsp+38h+arg_8]
0x180011516  mov     rbp, [rsp+38h+arg_10]
0x18001151b  add     rsp, 20h
0x18001151f  pop     r14
0x180011521  pop     rdi
0x180011522  pop     rsi
0x180011523  retn
```
