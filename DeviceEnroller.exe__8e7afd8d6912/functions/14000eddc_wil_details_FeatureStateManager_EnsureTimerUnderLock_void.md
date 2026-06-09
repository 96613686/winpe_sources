# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x14000eddc`
- end: `0x14000eeb0`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(struct _TP_TIMER **pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140015628`

## callees

- `0x14000eddc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ee02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ee29`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ee02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000ee29`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000ee5b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000ee67`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000ee5b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000ee67`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14000ee17`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x14000ee17`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000ee53`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x14000ee53`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000ee3c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000ee93`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000ee3c`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x14000ee93`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000ee4a`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x14000ee4a`

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
0x14000eddc  mov     [rsp+arg_8], rbx
0x14000ede1  mov     [rsp+arg_10], rbp
0x14000ede6  push    rsi
0x14000ede7  push    rdi
0x14000ede8  push    r14
0x14000edea  sub     rsp, 20h
0x14000edee  cmp     byte ptr [rcx+41h], 0
0x14000edf2  mov     rdi, rcx
0x14000edf5  jnz     loc_14000EE9D
0x14000edfb  cmp     qword ptr [rcx+30h], 0
0x14000ee00  jnz     short loc_14000EE6D
0x14000ee02  call    cs:__imp_GetLastError
0x14000ee08  xor     r8d, r8d; pcbe
0x14000ee0b  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x14000ee12  mov     rdx, rdi; pv
0x14000ee15  mov     ebp, eax
0x14000ee17  call    cs:__imp_CreateThreadpoolTimer
0x14000ee1d  mov     rsi, [rdi+30h]
0x14000ee21  mov     r14, rax
0x14000ee24  test    rsi, rsi
0x14000ee27  jz      short loc_14000EE61
0x14000ee29  call    cs:__imp_GetLastError
0x14000ee2f  xor     r9d, r9d; msWindowLength
0x14000ee32  xor     r8d, r8d; msPeriod
0x14000ee35  xor     edx, edx; pftDueTime
0x14000ee37  mov     rcx, rsi; pti
0x14000ee3a  mov     ebx, eax
0x14000ee3c  call    cs:__imp_SetThreadpoolTimer
0x14000ee42  mov     edx, 1; fCancelPendingCallbacks
0x14000ee47  mov     rcx, rsi; pti
0x14000ee4a  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x14000ee50  mov     rcx, rsi; pti
0x14000ee53  call    cs:__imp_CloseThreadpoolTimer
0x14000ee59  mov     ecx, ebx; dwErrCode
0x14000ee5b  call    cs:__imp_SetLastError
0x14000ee61  mov     ecx, ebp; dwErrCode
0x14000ee63  mov     [rdi+30h], r14
0x14000ee67  call    cs:__imp_SetLastError
0x14000ee6d  mov     rcx, [rdi+30h]; pti
0x14000ee71  test    rcx, rcx
0x14000ee74  jz      short loc_14000EE9D
0x14000ee76  mov     rax, 0FFFFFFFF4D2FA200h
0x14000ee80  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x14000ee85  mov     r9d, 124F8h; msWindowLength
0x14000ee8b  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x14000ee90  xor     r8d, r8d; msPeriod
0x14000ee93  call    cs:__imp_SetThreadpoolTimer
0x14000ee99  mov     byte ptr [rdi+41h], 1
0x14000ee9d  mov     rbx, [rsp+38h+arg_8]
0x14000eea2  mov     rbp, [rsp+38h+arg_10]
0x14000eea7  add     rsp, 20h
0x14000eeab  pop     r14
0x14000eead  pop     rdi
0x14000eeae  pop     rsi
0x14000eeaf  retn
```
