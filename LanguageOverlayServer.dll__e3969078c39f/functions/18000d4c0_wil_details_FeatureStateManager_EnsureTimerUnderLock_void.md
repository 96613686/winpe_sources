# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x18000d4c0`
- end: `0x18000d5b0`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `240`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18000f0dc`

## callees

- `0x180003a00`
- `0x18000d4c0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d4f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d51c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d4f5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000d51c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d54e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d55a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d54e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000d55a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d52f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d586`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d52f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18000d586`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000d50a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18000d50a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d546`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x18000d546`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d53d`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x18000d53d`

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
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-28h] BYREF

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
0x18000d4c0  mov     [rsp+arg_8], rbx
0x18000d4c5  mov     [rsp+arg_10], rbp
0x18000d4ca  push    rsi
0x18000d4cb  push    rdi
0x18000d4cc  push    r14
0x18000d4ce  sub     rsp, 30h
0x18000d4d2  mov     rax, cs:__security_cookie
0x18000d4d9  xor     rax, rsp
0x18000d4dc  mov     [rsp+48h+var_20], rax
0x18000d4e1  cmp     byte ptr [rcx+41h], 0
0x18000d4e5  mov     rdi, rcx
0x18000d4e8  jnz     loc_18000D590
0x18000d4ee  cmp     qword ptr [rcx+30h], 0
0x18000d4f3  jnz     short loc_18000D560
0x18000d4f5  call    cs:__imp_GetLastError
0x18000d4fb  xor     r8d, r8d; pcbe
0x18000d4fe  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18000d505  mov     rdx, rdi; pv
0x18000d508  mov     ebp, eax
0x18000d50a  call    cs:__imp_CreateThreadpoolTimer
0x18000d510  mov     rsi, [rdi+30h]
0x18000d514  mov     r14, rax
0x18000d517  test    rsi, rsi
0x18000d51a  jz      short loc_18000D554
0x18000d51c  call    cs:__imp_GetLastError
0x18000d522  xor     r9d, r9d; msWindowLength
0x18000d525  xor     r8d, r8d; msPeriod
0x18000d528  xor     edx, edx; pftDueTime
0x18000d52a  mov     rcx, rsi; pti
0x18000d52d  mov     ebx, eax
0x18000d52f  call    cs:__imp_SetThreadpoolTimer
0x18000d535  mov     edx, 1; fCancelPendingCallbacks
0x18000d53a  mov     rcx, rsi; pti
0x18000d53d  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18000d543  mov     rcx, rsi; pti
0x18000d546  call    cs:__imp_CloseThreadpoolTimer
0x18000d54c  mov     ecx, ebx; dwErrCode
0x18000d54e  call    cs:__imp_SetLastError
0x18000d554  mov     ecx, ebp; dwErrCode
0x18000d556  mov     [rdi+30h], r14
0x18000d55a  call    cs:__imp_SetLastError
0x18000d560  mov     rcx, [rdi+30h]; pti
0x18000d564  test    rcx, rcx
0x18000d567  jz      short loc_18000D590
0x18000d569  mov     rax, 0FFFFFFFF4D2FA200h
0x18000d573  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x18000d578  mov     r9d, 124F8h; msWindowLength
0x18000d57e  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x18000d583  xor     r8d, r8d; msPeriod
0x18000d586  call    cs:__imp_SetThreadpoolTimer
0x18000d58c  mov     byte ptr [rdi+41h], 1
0x18000d590  mov     rcx, [rsp+48h+var_20]
0x18000d595  xor     rcx, rsp; StackCookie
0x18000d598  call    __security_check_cookie
0x18000d59d  mov     rbx, [rsp+48h+arg_8]
0x18000d5a2  mov     rbp, [rsp+48h+arg_10]
0x18000d5a7  add     rsp, 30h
0x18000d5ab  pop     r14
0x18000d5ad  pop     rdi
0x18000d5ae  pop     rsi
0x18000d5af  retn
```
