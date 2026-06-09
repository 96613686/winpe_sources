# wil::details::FeatureStateManager::EnsureTimerUnderLock(void)

- ea: `0x180012d38`
- end: `0x180012e0c`
- name: `?EnsureTimerUnderLock@FeatureStateManager@details@wil@@AEAAXXZ`
- size: `212`
- prototype: `void __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800147d4`

## callees

- `0x180012d38`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012db7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012dc3`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012db7`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180012dc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d85`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180012d85`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180012d98`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180012def`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180012d98`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180012def`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180012da6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180012da6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180012d73`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180012d73`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180012daf`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180012daf`

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
0x180012d38  mov     [rsp+arg_8], rbx
0x180012d3d  mov     [rsp+arg_10], rbp
0x180012d42  push    rsi
0x180012d43  push    rdi
0x180012d44  push    r14
0x180012d46  sub     rsp, 20h
0x180012d4a  cmp     byte ptr [rcx+41h], 0
0x180012d4e  mov     rdi, rcx
0x180012d51  jnz     loc_180012DF9
0x180012d57  cmp     qword ptr [rcx+30h], 0
0x180012d5c  jnz     short loc_180012DC9
0x180012d5e  call    cs:__imp_GetLastError
0x180012d64  xor     r8d, r8d; pcbe
0x180012d67  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_d51448ba32f8ef42e59400edd4566183_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180012d6e  mov     rdx, rdi; pv
0x180012d71  mov     ebp, eax
0x180012d73  call    cs:__imp_CreateThreadpoolTimer
0x180012d79  mov     rsi, [rdi+30h]
0x180012d7d  mov     r14, rax
0x180012d80  test    rsi, rsi
0x180012d83  jz      short loc_180012DBD
0x180012d85  call    cs:__imp_GetLastError
0x180012d8b  xor     r9d, r9d; msWindowLength
0x180012d8e  xor     r8d, r8d; msPeriod
0x180012d91  xor     edx, edx; pftDueTime
0x180012d93  mov     rcx, rsi; pti
0x180012d96  mov     ebx, eax
0x180012d98  call    cs:__imp_SetThreadpoolTimer
0x180012d9e  mov     edx, 1; fCancelPendingCallbacks
0x180012da3  mov     rcx, rsi; pti
0x180012da6  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x180012dac  mov     rcx, rsi; pti
0x180012daf  call    cs:__imp_CloseThreadpoolTimer
0x180012db5  mov     ecx, ebx; dwErrCode
0x180012db7  call    cs:__imp_SetLastError
0x180012dbd  mov     ecx, ebp; dwErrCode
0x180012dbf  mov     [rdi+30h], r14
0x180012dc3  call    cs:__imp_SetLastError
0x180012dc9  mov     rcx, [rdi+30h]; pti
0x180012dcd  test    rcx, rcx
0x180012dd0  jz      short loc_180012DF9
0x180012dd2  mov     rax, 0FFFFFFFF4D2FA200h
0x180012ddc  lea     rdx, [rsp+38h+pftDueTime]; pftDueTime
0x180012de1  mov     r9d, 124F8h; msWindowLength
0x180012de7  mov     qword ptr [rsp+38h+pftDueTime.dwLowDateTime], rax
0x180012dec  xor     r8d, r8d; msPeriod
0x180012def  call    cs:__imp_SetThreadpoolTimer
0x180012df5  mov     byte ptr [rdi+41h], 1
0x180012df9  mov     rbx, [rsp+38h+arg_8]
0x180012dfe  mov     rbp, [rsp+38h+arg_10]
0x180012e03  add     rsp, 20h
0x180012e07  pop     r14
0x180012e09  pop     rdi
0x180012e0a  pop     rsi
0x180012e0b  retn
```
