# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180026438`
- end: `0x180026528`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `240`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18002e440`

## callees

- `0x180026438`
- `0x18008d9b0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800264c6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800264d2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800264c6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800264d2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002646d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026494`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002646d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180026494`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800264a7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800264fe`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800264a7`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800264fe`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800264be`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800264be`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800264b5`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800264b5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180026482`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180026482`

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
0x180026438  mov     [rsp+arg_8], rbx
0x18002643d  mov     [rsp+arg_10], rbp
0x180026442  push    rsi
0x180026443  push    rdi
0x180026444  push    r14
0x180026446  sub     rsp, 30h
0x18002644a  mov     rax, cs:__security_cookie
0x180026451  xor     rax, rsp
0x180026454  mov     [rsp+48h+var_20], rax
0x180026459  cmp     byte ptr [rcx+41h], 0
0x18002645d  mov     rdi, rcx
0x180026460  jnz     loc_180026508
0x180026466  cmp     qword ptr [rcx+30h], 0
0x18002646b  jnz     short loc_1800264D8
0x18002646d  call    cs:__imp_GetLastError
0x180026473  xor     r8d, r8d; pcbe
0x180026476  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18002647d  mov     rdx, rdi; pv
0x180026480  mov     ebp, eax
0x180026482  call    cs:__imp_CreateThreadpoolTimer
0x180026488  mov     rsi, [rdi+30h]
0x18002648c  mov     r14, rax
0x18002648f  test    rsi, rsi
0x180026492  jz      short loc_1800264CC
0x180026494  call    cs:__imp_GetLastError
0x18002649a  xor     r9d, r9d; msWindowLength
0x18002649d  xor     r8d, r8d; msPeriod
0x1800264a0  xor     edx, edx; pftDueTime
0x1800264a2  mov     rcx, rsi; pti
0x1800264a5  mov     ebx, eax
0x1800264a7  call    cs:__imp_SetThreadpoolTimer
0x1800264ad  mov     edx, 1; fCancelPendingCallbacks
0x1800264b2  mov     rcx, rsi; pti
0x1800264b5  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800264bb  mov     rcx, rsi; pti
0x1800264be  call    cs:__imp_CloseThreadpoolTimer
0x1800264c4  mov     ecx, ebx; dwErrCode
0x1800264c6  call    cs:__imp_SetLastError
0x1800264cc  mov     ecx, ebp; dwErrCode
0x1800264ce  mov     [rdi+30h], r14
0x1800264d2  call    cs:__imp_SetLastError
0x1800264d8  mov     rcx, [rdi+30h]; pti
0x1800264dc  test    rcx, rcx
0x1800264df  jz      short loc_180026508
0x1800264e1  mov     rax, 0FFFFFFFF4D2FA200h
0x1800264eb  lea     rdx, [rsp+48h+pftDueTime]; pftDueTime
0x1800264f0  mov     r9d, 124F8h; msWindowLength
0x1800264f6  mov     qword ptr [rsp+48h+pftDueTime.dwLowDateTime], rax
0x1800264fb  xor     r8d, r8d; msPeriod
0x1800264fe  call    cs:__imp_SetThreadpoolTimer
0x180026504  mov     byte ptr [rdi+41h], 1
0x180026508  mov     rcx, [rsp+48h+var_20]
0x18002650d  xor     rcx, rsp; StackCookie
0x180026510  call    __security_check_cookie
0x180026515  mov     rbx, [rsp+48h+arg_8]
0x18002651a  mov     rbp, [rsp+48h+arg_10]
0x18002651f  add     rsp, 30h
0x180026523  pop     r14
0x180026525  pop     rdi
0x180026526  pop     rsi
0x180026527  retn
```
